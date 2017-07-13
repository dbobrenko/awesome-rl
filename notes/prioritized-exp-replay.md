# Prioritized Experience Replay

[[arXiv](https://arxiv.org/abs/1511.05952v4)], [[pdf](https://arxiv.org/pdf/1511.05952v4.pdf)]   
Tom Schaul, John Quan, Ioannis Antonoglou and David Silver

The authors proposed to increase data efficiency by training on transitions from replay buffer, that were "hard" (e.g. resulted in high TD-error) for the agent last time it observes them. For those, who are familiar with supervised learning, the idea of Prioritized Experience Replay is somewhat similar to the "Online Hard Example Mining" (OHEM).

## Proposed methods of prioritization
**Oracle prioritization.** Greedily select the transition that maximally reduces the global loss in its current state (in hindsight, after the parameter update).  

**Greedy Temporal-Difference (TD) error prioritization.** High TD error indicates how ‘surprising’ or unexpected the transition is for the agent. The main idea is to replay transition with the largest absolute TD error stored in memory. New transitions are stored with the maximal priority, in order to guarantee that all experience is seen at least once.  
Pros & Cons:  
   - **+** Suitable for incremental, online RL algorithms, such as SARSA or Q-learning;
   - **-** Sensitive to noisy (stochastic) rewards;
   - **-** TD errors are only updated for the transitions that are replayed.
   - **-** Transitions that have a low TD error on first visit can be never replayed.
   - **-** Prone to over-fitting.

**Stochastic TD prioritization.** This method samples transitions randomly, based on their TD error. The probability of sampling transition *i* as:  
![stochastic prioritization](/assets/prioritized-exp-replay-stochastic.png),  
where `p[i] = abs(delta[i]) + epsilon` - TD error of transition *i* + some positive constant, to prevent transitions with zero replay probabilities,  
`a` - exponent, determines how much prioritization is used.  


Pros & Cons:
   - **+** Guarantees a non-zero probabilities;
   - **+** Large speed-ups over the uniform-based sampling.

**Rank-based TD prioritization.** The second variant looks as: *p[i] = 1 / rank(i)*. Where rank(i) is the rank of transition *i* when the replay memory is sorted by TD-error.  
Pros & Cons:
   - **+** Guarantees a non-zero probabilities;
   - **+** Large speed-ups over the uniform-based sampling;
   - **+** Insensitive to outliers.   

## Prioritization Replay Bias
In order to reduce bias introduced by non-uniform sampling to the data distribution, they used **importance-sampling (IS)** weights:
```python
# N - replay buffer size
# P - list with TD-errors for each replayed transition
# w - IS weights
W = (1/N) * (1/P[i])
W_max = W if W > W_max else W_max
delta = W * delta / W_max # normalize weights + compensate delta
#... plug current delta into backprop
```
Such approach fully compensates for the non-uniform probabilities P(i).
Intuitively, current expression `W = (1/N) * (1/P[i])` says:
The smaller probability to sample current transition was, the higher we should weight it. And vice versa, the higher probability it was, the lesser we will take it into account.  
Also, they always normalize weights by `1 / W_max` so that the update is only scaled downwards.


