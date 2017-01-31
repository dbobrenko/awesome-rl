#Prioritized Experience Replay

[arXiv, pdf](https://arxiv.org/pdf/1511.05952v4.pdf)  
Tom Schaul, John Quan, Ioannis Antonoglou and David Silver

**In progress.**

The main idea of this paper is that an RL agent can learn more effectively from some transitions than from others. More precise, they increase data efficiency by training on transitions from replay buffer, that are currently "hard" for agent, more often, than in usual experience replay case. For those, who are familiar with supervised learning, the idea of Prioritized Experience Replay is somewhat similar to the "Online Hard Example Mining" (OHEM).

##Proposed methods of prioritization
**Oracle** - greedily select the transition that maximally reduces the global loss in its current state (in hindsight, after the parameter update).  

**Temporal-Difference (TD)-error prioritization.** High TD error indicates how ‘surprising’ or unexpected the transition is for the agent. Pros & Cons:  
   - **+** Suitable for incremental, online RL algorithms, such as SARSA or Q-learning;
   - **-** Sensitive to noisy (stochastic) rewards;
   - **-** TD errors are only updated for the transitions that are replayed.
   - **-** Transitions that have a low TD error on first visit can be never replayed.
   - **-** Prone to over-fitting.

**Stochastic prioritization.** Current method guarantees a non-zero probabilities. The probability of sampling transition *i* as:  
![stochastic prioritization](/assets/prioritized-exp-replay-stochastic.png),  
where `p[i] = abs(delta[i]) + epsilon` - priority of transition *i* + some positive constant, to prevent transitions with zero replay probabilities,  
`a` - exponent, determines how much prioritization is used.  

**Rank-based prioritization.** The second variant looks as: *p[i] = 1 / rank(i)*. Where rank(i) is the rank of transition *i* when the replay memory is sorted by TD-error. In constast to stochastic prioritization, current approach is insensetive to outliers.  
