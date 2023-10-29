# Awesome Reinforcement Learning

<details>
  <summary><b><i>Click here to see icon descriptions.</i></b></summary>
  
- :rocket: - state-of-the-art agent/technique at the moment of paper publication.
- :star: - valuable paper.
- ![model-based] - Model-based RL.
- ![multi-agent-rl] - Multi-Agent RL.
- ![self-play] - Self-Play.
- ![evolution] - Evolutionary & Genetic Algorithms.
- ![generalization] - Generalization on unseen environments.
- ![auto-ml] - Auto ML - Architecture search.
- ![manipulation] - Manipulation tasks.
- ![locomotion] - Locomotion: MuJoCo, Roboschool, etc.
- ![navigation] - Navigation tasks.
- ![plan] - Strategy Planning Problems.
- ![transfer] - Transfer learning.
- ![inverse-rl] - Inverse Reinforcement Learning.
- ![meta-learning] - Meta-Learning.
- ![exploration] - Curiosity Learning, Advanced Exploration.
- ![table] - Table games (Table).
- ![atari] - Atari game (Atari).
- ![doom] - Doom game (Doom).
- ![sc] - Starcraft game (Starcraft).
- ![go] - Go game (Go).

</details>

## Table of Contents
  - [Frameworks](#frameworks)
  - [Benchmarks](#benchmarks)
  - [Policy-Based Generic Agents](#policy-agents)
  - [Value-Based Generic Agents](#value-agents)
  - [![model-based] Model-Based Generic Agents](#model-based)
  - [![evolution] Evolutionary & Genetic Algorithms](#evolution)
  - [![exploration] Exploration](#exploration)
  - [![self-play] Self-Play](#self-play)
  - [![meta-learning] Meta-Learning](#meta-learning)
  - [![multi-agent-rl] Multi-Agent RL](#multi-agent-rl)
  - [![inverse-rl] Inverse RL](#inverse-rl)
  - [![navigation] Navigation](#navigation)
  - [![manipulation] Manipulation](#manipulation)
  - [![locomotion] Locomotion](#locomotion)
  - [![auto-ml] Auto ML](#auto-ml)
  - [Other Domains](#other-domains)
  - [Books](#books)
  - [Search for new Papers](#search-for-new-papers)
  - [Misc](#misc)


## RL Frameworks & Implementations <a name="frameworks"></a>
[[Stable Baselines3](https://stable-baselines3.readthedocs.io/en/master/)] PyTorch: MaskablePPO, PPO, A2C, DQN, etc

[[Baselines @ OpenAI](https://github.com/openai/baselines)] TensorFlow: PPO, A2C, DQN, TRPO, ACKTR, DDPG, HER, GAIL, etc

[[Baselines @ DLR-RM](https://github.com/DLR-RM/stable-baselines3)] Pytorch: Custom envs, custom policies
  
[[RLlib @ Ray](https://github.com/ray-project/ray/tree/master/rllib) Pytorch / TensorFlow]
  
[[Dopamine @ Google](https://github.com/google/dopamine)] TensorFlow: Rainbow, c51, IQN, DQN, etc
 
[[TensorForce](https://github.com/reinforceio/tensorforce)] TensorFlow: A3C, PPO, TRPO, DQN, etc

[[pytorch-a2c-ppo-acktr](https://github.com/ikostrikov/pytorch-a2c-ppo-acktr-gail)] PyTorch: A2C, ACKTR, PPO, GAIL, etc

## RL Benchmarks <a name="benchmarks"></a>
[[OpenAI Benchmarks for PPO, A2C, ACKTR, ACER](https://github.com/openai/baselines-results/blob/master/acktr_ppo_acer_a2c_atari.ipynb)]
 
[[OpenAI Benchmarks for DQN, Double DQN, Dueling DQN, Prioritized DQN](https://github.com/openai/baselines-results/blob/master/dqn_results.ipynb)]

[[Google Benchmarks for Rainbow, c51, IQN, DQN](https://google.github.io/dopamine/baselines/plots.html)]

## Policy-Based Generic Agents <a name="policy-agents"></a>
:rocket: [[Soft Actor Critic](https://arxiv.org/abs/1812.05905)] [[blog](https://ai.googleblog.com/2019/01/soft-actor-critic-deep-reinforcement.html)] [[code](https://github.com/rail-berkeley/softlearning/)] 2018 @ Google Brain, UC Berkeley

:rocket: [[IMPALA](https://arxiv.org/abs/1802.01561v2)] 2018 @ Uber AI Labs
  
:rocket: [[Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation (ACKTR, A2C)](https://arxiv.org/abs/1708.05144)] 2018; Univ. of Toronto, New York Univ.

:rocket: [[Proximal Policy Optimization Algorithms (PPO)](https://arxiv.org/abs/1707.06347)] [[blog](https://blog.openai.com/openai-baselines-ppo/)] 2017 @ OpenAI

:rocket: [:pencil: Notes](./notes/a3c-agent.md) [[Asynchronous Methods for Deep Reinforcement Learning (A3C)](https://arxiv.org/abs/1602.01783v2)] 2016 @ Google Deepmind 

[[High-dimensional continuous control using generalized advantage estimation (GAE)](https://arxiv.org/abs/1506.02438)] 2015 @ Berkeley

:star: [[Trust Region Policy Optimization (TRPO)](https://arxiv.org/abs/1502.05477)] 2015 @ UC Berkeley

:star: [[Actor-Critic Algorithms, pdf](https://papers.nips.cc/paper/1786-actor-critic-algorithms.pdf)] Konda and Tsitsiklis, 2003

:star: [[Simple Statistical Gradient-Following Algorithms for Connectionist Reinforcement Learning (REINFORCE), pdf](http://www-anw.cs.umass.edu/~barto/courses/cs687/williams92simple.pdf)] Ronald J. Williams, 1992 @ Northeastern Univ.

## Value-Based Generic Agents <a name="value-agents"></a>
:rocket: [[Implicit Quantile Networks for Distributional Reinforcement Learning (IQN)](https://arxiv.org/abs/1806.06923)] Dabney et al., 2018 @ Google Deepmind

:rocket: [[A Distributional Perspective on Reinforcement Learning (c51)](https://arxiv.org/abs/1707.06887)] Bellemare et al., 2018 @ Google Deepmind

:rocket: [[Rainbow: Combining Improvements in Deep Reinforcement Learning](https://arxiv.org/abs/1710.02298)] Hessel et al., 2017 @ Google Deepmind

:rocket: [[Dueling Network Architectures for Deep Reinforcement Learning (Dueling DQN)](https://arxiv.org/abs/1511.06581)] Wang et al., 2015 @ Google Deepmind

:rocket: [:pencil: Notes](./notes/prioritized-exp-replay.md) [[Prioritized Experience Replay](https://arxiv.org/abs/1511.05952v4)] Schaul et al., 2015 @ Google Deepmind

:rocket: [[Deep Reinforcement Learning with Double Q-learning (Double DQN)](https://arxiv.org/abs/1509.06461)] Hasselt et al., 2015 @ Google Deepmind

:rocket: [:pencil: Notes](./notes/dqn-agent.md) [[Human-level control through deep reinforcement learning (DQN)](http://www.nature.com/nature/journal/v518/n7540/full/nature14236.html)]
[[pdf](hhttp://www.readcube.com/articles/10.1038/nature14236?shared_access_token=Lo_2hFdW4MuqEcF3CVBZm9RgN0jAjWel9jnR3ZoTv0P5kedCCNjz3FJ2FhQCgXkApOr3ZSsJAldp-tw3IWgTseRnLpAc9xQq-vTA2Z5Ji9lg16_WvCy4SaOgpK5XXA6ecqo8d8J7l4EJsdjwai53GqKt-7JuioG0r3iV67MQIro74l6IxvmcVNKBgOwiMGi8U0izJStLpmQp6Vmi_8Lw_A%3D%3D)]
Mnih et al., 2015 @ Google Deepmind

:rocket: [[Playing Atari with Deep Reinforcement Learning** (DQN)](https://arxiv.org/abs/1312.5602)] Mnih et al., 2013 @ DeepMind Technologies

:star: [[Temporal Difference Learning and TD-Gammon, pdf](http://cling.csd.uwo.ca/cs346a/extra/tdgammon.pdf)] Gerald Tesauro, 1995


## ![model-based] Model-Based Generic Agents  <a name="model-based"></a>
[[Model-Based Reinforcement Learning for Atari](https://arxiv.org/abs/1903.00374)] 2019 @ Google Brain, etc

:star: ![navigation] [[World Models](https://arxiv.org/abs/1803.10122)] [[blog](https://worldmodels.github.io/)] 2018 @ IDSIA, Google Brain, NNAISENSE

![locomotion] [[Neural Network Dynamics for Model-Based Deep Reinforcement Learning with Model-Free Fine-Tuning](https://arxiv.org/abs/1708.02596)] [[blog](http://bair.berkeley.edu/blog/2017/11/30/model-based-rl/)] [[code](https://github.com/nagaban2/nn_dynamics)] 2017 @ Berkeley

![locomotion] [[Learning model-based planning from scratch](https://arxiv.org/abs/1707.06170)], [[blog](https://deepmind.com/blog/agents-imagine-and-plan/)] 2017 @ Google DeepMind

![navigation] [[The Predictron: End-To-End Learning and Planning](https://arxiv.org/abs/1612.08810v2)] 2016 @ Google Deepmind


## ![evolution] Evolutionary Algorithms <a name="evolution"></a>
[[Back to Basics: Benchmarking Canonical Evolution Strategies for Playing Atari](https://arxiv.org/abs/1802.08842)] 2018 @ Univ. of Freiburg

:star: ![locomotion] [[Deep Neuroevolution](https://arxiv.org/abs/1712.06567)] 2017 @ Uber AI Labs

:star: [[Evolution Strategies as a Scalable Alternative to Reinforcement Learning](https://arxiv.org/abs/1703.03864v1)] 2017 @ OpenAI

[[Evolving Large-Scale Neural Networks for Vision-Based Reinforcement Learning, pdf](http://people.idsia.ch/~juergen/gecco2013torcs.pdf)] 2013 @ IDSIA, USI-SUPSI


## ![exploration] Exploration <a name="exploration"></a>
:rocket: [[Go-Explore](https://arxiv.org/abs/1901.10995)] 2019 @ Uber AI Labs

[[Exploration by Random Network Distillation (RND)](https://arxiv.org/abs/1810.12894)] [[blog](https://blog.openai.com/reinforcement-learning-with-prediction-based-rewards/)] [[code](https://github.com/openai/random-network-distillation)] 2018 @ OpenAI

![navigation] [[Large-Scale Study of Curiosity-Driven Learning](https://arxiv.org/abs/1808.04355)] [[blog](https://pathak22.github.io/large-scale-curiosity/)] 2018 @ OpenAI, Berkeley, Univ. of Edinburgh

:star: [[RUDDER: Return Decomposition for Delayed Rewards](https://arxiv.org/abs/1806.07857)] [[code](https://github.com/ml-jku/baselines-rudder)] 2018 @ Johannes Kepler Univ. Linz

[[Deep Curiosity Search](https://arxiv.org/abs/1806.00553)] 2018 @ Univ. of Wyoming

![locomotion] [[Parameter Space Noise for Exploration](https://arxiv.org/abs/1706.01905)] 2017 @ OpenAI, Karlsruhe Inst. of Tech.

:star: ![transfer] [[Imagination-Augmented Agents for Deep Reinforcement Learning (I2As)](https://arxiv.org/abs/1707.06203)] [[blog](https://deepmind.com/blog/agents-imagine-and-plan/)] 2017 @ DeepMind


## ![self-play] Self-Play <a name="self-play"></a>
:star: ![table] [[Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm](https://arxiv.org/abs/1712.01815)] Silver et al., 2017 @ Google Deepmind

:star: ![table] [[Mastering the Game of Go without Human Knowledge (AlphaGo Zero), pdf](https://deepmind.com/documents/119/agz_unformatted_nature.pdf)], [[blog](https://deepmind.com/blog/alphago-zero-learning-scratch/)] Silver et al., 2017 @ Deepmind

![table] [[Mastering the game of Go with deep neural networks and tree search (AlphaGo Master)](https://www.nature.com/nature/journal/v529/n7587/full/nature16961.html)], [[reddit](https://www.reddit.com/r/MachineLearning/comments/42ytdx/pdf_mastering_the_game_of_go_with_deep_neural/)] Silver et al., 2017 @ Deepmind, Google


## ![meta-learning] Meta-Learning
![locomotion] [[Meta Learning Shared Hierarchies](https://arxiv.org/abs/1710.09767)] [[blog](https://blog.openai.com/learning-a-hierarchy/)] Frans et al., 2017 @ OpenAI, Berkeley.

[[Hybrid Reward Architecture for Reinforcement Learning (HRA)](https://arxiv.org/abs/1706.04208v1)] van Seijen et al., 2017 @ Microsoft Maluuba, McGill Univ.


## ![multi-agent-rl] Multi-Agent RL
[[Learning with Opponent-Learning Awareness (LOLA)](https://arxiv.org/abs/1709.04326)] [[blog](https://blog.openai.com/learning-to-model-other-minds/)] Foerster et al., 2017 @ OpenAI, Oxford, Berkeley, CMU


## ![inverse-rl] Inverse RL <a name="inverse-rl"></a>
![manipulation] [[SFV: Reinforcement Learning of Physical Skills from Videos](https://arxiv.org/abs/1810.03599)] [[blog](https://bair.berkeley.edu/blog/2018/10/09/sfv/)] Peng et al., 2018; Berkeley

![manipulation] [[One-Shot Imitation from Observing Humans via Domain-Adaptive Meta-Learning](https://arxiv.org/abs/1802.01557v1)] Finn et al., 2018 @ UC Berkeley
  
![manipulation] [[One-Shot Visual Imitation Learning via Meta-Learning](https://arxiv.org/abs/1709.04905)] Finn et al., 2017 @ UC Berkeley, OpenAI


## ![navigation] Navigation <a name="navigation"></a>
[[Learning to Navigate in Cities Without a Map](https://arxiv.org/abs/1804.00168)] Mirowski et al, 2019 @ Deepmind

[[Human-level performance in first-person multiplayer games with population-based deep reinforcement learning](https://arxiv.org/abs/1807.01281)] [[blog](https://deepmind.com/blog/capture-the-flag/)] Jaderberg et al, 2018 @ DeepMind

![generalization] [[Building Generalizable Agents with a Realistic and Rich 3D Environment](https://arxiv.org/abs/1801.02209)] Wu et al, 2018 @ Berkeley, FAIR

:rocket: [[Learning to Navigate in Complex Environments](https://arxiv.org/abs/1611.03673)] Mirowski et al., 2017 @ Deepmind

![transfer] [Distral: Robust Multitask Reinforcement Learning](https://arxiv.org/abs/1707.04175)] Teh et al, 2017 @ Deepmind

![meta-learning] [[RL<sup>2</sup>: Fast Reinforcement Learning via Slow Reinforcement Learning](https://arxiv.org/abs/1611.02779)] Duan et al., 2016 @ Berkeley, OpenAI

:star: [:pencil: Notes](./notes/unreal-agent.md) ![locomotion] [[Reinforcement Learning with unsupervised auxiliary tasks (UNREAL)](https://arxiv.org/abs/1611.05397)] Jaderberg et al., 2016 @ Google DeepMind

:rocket: [[Learning to act by predicting the future (VizDoom 2016 Full DM Winner)](https://arxiv.org/abs/1611.01779)] Dosovitskiy, Koltun, 2016 @ Intel Labs

[[Playing FPS Games with Deep Reinforcement Learning (VizDoom 2016 Limited DM 2nd place)](https://arxiv.org/abs/1609.05521)] Lample, Chaplot, 2016 @ CMU


## ![manipulation] Manipulation <a name="manipulation"></a>
![generalization] [[Learning Dexterous In-Hand Manipulation](https://arxiv.org/abs/1808.00177)] [[blog](https://blog.openai.com/learning-dexterity/)] Andrychowicz et al., 2018 @ OpenAI

![generalization] [[Asymmetric Actor Critic for Image-Based Robot Learning](https://arxiv.org/abs/1710.06542)] [[blog](https://blog.openai.com/generalizing-from-simulation/)] Pinto et al., 2017 @ OpenAI, CMU

![generalization] [[Sim-to-Real Transfer of Robotic Control with Dynamics Randomization](https://arxiv.org/abs/1710.06537)], [[blog](https://blog.openai.com/generalizing-from-simulation/)] Peng et al., 2017 @ OpenAI, Berkeley

## ![locomotion] Locomotion <a name="locomotion"></a>
[[Emergence of Locomotion Behaviours in Rich Environments](https://arxiv.org/abs/1707.02286)] [[blog](https://deepmind.com/blog/producing-flexible-behaviours-simulated-environments/)] Heess et al., 2017 @ DeepMind

[[Programmable Agents](https://arxiv.org/abs/1706.06383v1)] Denil et al., 2017 @ Google Deepmind

## ![auto-ml] Auto ML <a name="auto-ml"></a>
[[AutoAugment: Learning Augmentation Policies from Data](https://arxiv.org/abs/1805.09501)] Cubuk et al., 2018 @ Google Brain

:star: ![evolution] [[Regularized Evolution for Image Classifier Architecture Search](https://arxiv.org/abs/1802.01548v2)] Real et al., 2018 @ Google Brain

:star: [[Learning Transferable Architectures for Scalable Image Recognition](https://arxiv.org/abs/1707.07012)] Zoph et al., 2017 @ Google Brain

[[Neural Optimizer Search with Reinforcement Learning, pdf](http://proceedings.mlr.press/v70/bello17a/bello17a.pdf)] Bello et al., 2017 @ Google Brain

[[Neural Architecture Search with Reinforcement Learning](https://arxiv.org/abs/1611.01578)] B. Zoph and Quoc V. Le, 2016 @ Google Brain


## Other Domains  <a name="other-domains"></a>
[[A Deep Reinforcement Learning Chatbot](https://arxiv.org/abs/1709.02349)] Serban et al., 2017 @ MILA


## Books
:star: [[Reinforcement Learning: An Introduction, pdf](http://incompleteideas.net/book/bookdraft2018jan1.pdf)] Richard S. Sutton and Andrew G. Barto, 2018


## Search for new Papers
[[A Brief Survey of Deep Reinforcement Learning](https://arxiv.org/abs/1708.05866)] Arulkumaran et al., 2017

Another Awesome Deep RL list: https://github.com/tigerneil/awesome-deep-rl

Awesome Offline RL: https://github.com/hanjuku-kaso/awesome-offline-rl

ArXiv Sanity Preserver: http://www.arxiv-sanity.com/
  
GitXiv: http://www.gitxiv.com/


## Misc
[[How to Read a Paper](http://ccr.sigcomm.org/online/files/p83-keshavA.pdf)] S. Keshav, 2007 @ Univ. of Waterloo

[Transfromers: [Attention is all you need](https://arxiv.org/abs/1706.03762)] Vaswani et al. 2017 @ Google Brain/Research


[atari]: ./icons/atari.png	"Atari 2600 games"
[doom]: ./icons/doom.png	"Doom game"
[sc]: ./icons/sc.png	"Starcraft game"
[go]: ./icons/go.png	"Go game"
[table]: ./icons/table.png	"Table games"
[auto-ml]: ./icons/nn.png	"Neural Networks & Optimizers"
[manipulation]: ./icons/robot.png	"Robotic hand manipuation"
[locomotion]: ./icons/loco.png	"Locomotion tasks"
[navigation]: ./icons/maze.png	"Navigation tasks"
[model-based]: ./icons/model.png	"Model-based RL"
[multi-agent-rl]: ./icons/marl.png	"Multi-Agent RL"
[self-play]: ./icons/sp.png	"Self-Play RL"
[evolution]: ./icons/evo.png	"Evolutionary & Genetic Algorithms"
[generalization]: ./icons/gener.png	"Generalization across environments"
[plan]: ./icons/plan.png	"Complex Planning Problems"
[transfer]: ./icons/transfer.png	"Transfer Learning"
[inverse-rl]: ./icons/irl.png	"Inverse Reinforcement Learning"
[meta-learning]: ./icons/meta.png	"Meta-Learning"
[exploration]: ./icons/sparse.png	"Curiosity learning, Exploration"
