A constantly evolving list of Reinforcement Learning papers, notes, books etc.

[atari]: ./icons/atari.png	"Atari 2600 games"
[doom]: ./icons/doom.png	"Doom game"
[sc]: ./icons/sc.png	"Starcraft game"
[go]: ./icons/go.png	"Go game"
[table]: ./icons/table.png	"Table games"
[nn]: ./icons/nn.png	"Neural Networks & Optimizers"
[robot]: ./icons/robot.png	"Real Robot Experiments"
[loco]: ./icons/loco.png	"Locomotion tasks"
[maze]: ./icons/maze.png	"Mazes & Labyrinths"
[model]: ./icons/model.png	"Model-based RL"
[marl]: ./icons/marl.png	"Multi-Agent RL"
[sp]: ./icons/sp.png	"Self-Play RL"
[evo]: ./icons/evo.png	"Evolutionary & Genetic Algorithms"
[gener]: ./icons/gener.png	"Generalization across environments"
[plan]: ./icons/plan.png	"Complex Planning Problems"
[transfer]: ./icons/transfer.png	"Transfer Learning"
[irl]: ./icons/irl.png	"Inverse Reinforcement Learning"
[meta]: ./icons/meta.png	"Meta-Learning"
[sparse]: ./icons/sparse.png	"Sparse Reward Problems"

**Glossary:**

- :rocket: - state-of-the-art method in current domain at the moment of paper publication.
- :star: - valuable paper.

<details>
  <summary><b><i>Click here to see Domain Tag icon descriptions.</i></b></summary>

- ![model] - Model-based RL (Model-based).
- ![marl] - Multi-Agent RL (MARL).
- ![sp] - Self-Play.
- ![evo] - Evolutionary & Genetic Algorithms (Evolution).
- ![gener] - Generalization across environments (Generalization).
- ![nn] - Neural Networks & Optimizers (NN).
- ![robot] - Manipulation tasks (Manipulator).
- ![loco] - Locomotion: MuJoCo, Roboschool, etc (Locomotion)
- ![maze] - Mazes and Labyrinths (Maze).
- ![plan] - Strategy Planning Problems (Planning).
- ![transfer] - Transfer learning (Transfer).
- ![irl] - Inverse Reinforcement Learning (IRL)
- ![meta] - Meta-Learning
- ![sparse] - Sparse Reward Problems and/or Montezuma's Revenge (Sparse)
- ![atari] - Atari game (Atari).
- ![table] - Table games (Table).
- ![doom] - Doom game (Doom).
- ![sc] - Starcraft game (Starcraft).
- ![go] - Go game (Go).

</details>

# Deep Reinforcement Learning

## Year 2018
:rocket: **RUDDER: Return Decomposition for Delayed Rewards**
  - [[arXiv](https://arxiv.org/abs/1806.07857)] [[code](https://github.com/ml-jku/baselines-rudder)] Arjona-Medina et al.; Johannes Kepler University Linz
  - ![sparse] ![atari] Sparse, Atari
  
**Relational Deep Reinforcement Learning**
  - [[arXiv](https://arxiv.org/pdf/1806.01830.pdf)] Zambaldi et al.; DeepMind
  - ![plan] ![sc] Planning, Starcraft

**Deep Curiosity Search: Intra-Life Exploration Improves Performance on Challenging Deep Reinforcement Learning Problems**
  - [[arXiv](https://arxiv.org/abs/1806.00553)] Stanton and Clune; University of Wyoming
  - ![sparse] Sparse

**AutoAugment: Learning Augmentation Policies from Data**
  - [[arXiv](https://arxiv.org/abs/1805.09501)] Cubuk et al.; Google Brain
  - ![nn] NN

**Playing Atari with Six Neurons**
  - [[arXiv](https://arxiv.org/abs/1806.01363)] Cucci et al.; University of Fribourg, NYU
  - ![atari] Atari
  
:star: **World Models**
  - [[arXiv](https://arxiv.org/abs/1803.10122)] [[blog](https://worldmodels.github.io/)] Ha and Schmidhuber; IDSIA, Google Brain, NNAISENSE
  - ![model] ![doom] Model-based, Doom

**Back to Basics: Benchmarking Canonical Evolution Strategies for Playing Atari**
  - [[arXiv](https://arxiv.org/abs/1802.08842)] Chrabaszcz et al.; University of Freiburg
  - ![evo] ![atari] Evolution, Atari

:rocket: **IMPALA: Scalable Distributed Deep-RL with Importance Weighted Actor-Learner Architectures**
  - [[arXiv](https://arxiv.org/abs/1802.01561v2)] Such et al.; Uber AI Labs
  - ![atari] ![maze] Atari, Maze

**One-Shot Imitation from Observing Humans via Domain-Adaptive Meta-Learning**
  - [[arXiv](https://arxiv.org/abs/1802.01557v1)] Finn et al.; UC Berkeley
  - ![irl] ![robot] IRL, Manipulator

:rocket: **Regularized Evolution for Image Classifier Architecture Search**
  - [[arXiv](https://arxiv.org/abs/1802.01548v2)] Real et al.; Google Brain
  - ![evo] ![nn] Evo, NN


## Year 2017
:star: **Deep Neuroevolution: Genetic Algorithms Are a Competitive Alternative for Training Deep Neural Networks for Reinforcement Learning**
  - [[arXiv](https://arxiv.org/abs/1712.06567)] Such et al.; Uber AI Labs
  - ![loco] ![atari] Locomotion, Atari

:star: **Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm**
- [[arxiv](https://arxiv.org/abs/1712.01815)] Silver et al.; DeepMind
- ![sp] ![plan] ![table] Self-Play, Planning, Table

:star: **Rainbow: Combining Improvements in Deep Reinforcement Learning** (DQN improvements combined)
- [[arXiv](https://arxiv.org/abs/1710.02298)] Hessel et al.; Deepmind
- ![atari] Atari

:star: **Meta Learning Shared Hierarchies**
- [[arXiv](https://arxiv.org/abs/1710.09767)] [[blog](https://blog.openai.com/learning-a-hierarchy/)] Frans et al.; OpenAI, Berkeley.
- ![meta] ![loco] Locomotion, Meta-Learning

**One-Shot Visual Imitation Learning via Meta-Learning**
- [[arXiv](https://arxiv.org/abs/1709.04905)] [[pdf](https://arxiv.org/pdf/1709.04905.pdf)] Finn et al.; UC Berkeley, OpenAI
- ![irl] ![meta] ![robot] IRL, Meta-Learning, Manipulator

**Learning with Opponent-Learning Awareness** (LOLA)
- [[arXiv](https://arxiv.org/abs/1709.04326)] [[blog](https://blog.openai.com/learning-to-model-other-minds/)] Foerster et al.; OpenAI, Oxford, Berkeley, CMU
- ![marl] MARL

:rocket: **Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation** (ACKTR, A2C)
- [[arXiv](https://arxiv.org/abs/1708.05144)] Wu et al.; University of Toronto, New York University
- ![loco] ![atari] Locomotion, Atari

**Neural Network Dynamics for Model-Based Deep Reinforcement Learning with Model-Free Fine-Tuning**
- [[arXiv](https://arxiv.org/abs/1708.02596)] [[blog](http://bair.berkeley.edu/blog/2017/11/30/model-based-rl/)] [[code](https://github.com/nagaban2/nn_dynamics)] Nagabandi et al.; Berkeley
- ![loco] Locomotion

:rocket: **Proximal Policy Optimization Algorithms** (PPO)
- [[arXiv](https://arxiv.org/abs/1707.06347)] [[blog](https://blog.openai.com/openai-baselines-ppo/)] Schulman et al.; OpenAI
- ![atari] ![loco] Locomotion, Atari

:rocket: **Learning Transferable Architectures for Scalable Image Recognition**
- [[arXiv](https://arxiv.org/abs/1707.07012)] Zoph et al.; Google Brain
- ![nn] NN

**Hybrid Reward Architecture for Reinforcement Learning** (HRA)
- [[arXiv](https://arxiv.org/abs/1706.04208v1)] van Seijen et al.; Microsoft Maluuba, McGill University
- ![meta] ![atari] Meta-Learning, Atari

**Parameter Space Noise for Exploration**
- [[arXiv](https://arxiv.org/abs/1706.01905)] Plappert et al.; OpenAI, Karlsruhe Institute of Technology
- ![loco] ![atari] Locomotion, Atari

:rocket: **Mastering the Game of Go without Human Knowledge** (AlphaGo Zero)
- [[pdf](https://deepmind.com/documents/119/agz_unformatted_nature.pdf)], [[blog](https://deepmind.com/blog/alphago-zero-learning-scratch/)] Silver et al.; Deepmind
- ![sp] ![plan] ![go] ![table] Self-Play, Planning, Go, Table

**Neural Optimizer Search with Reinforcement Learning**
- [[pdf](http://proceedings.mlr.press/v70/bello17a/bello17a.pdf)] Bello et al.; Google Brain
- ![nn] NN

**Asymmetric Actor Critic for Image-Based Robot Learning**
- [[arXiv](https://arxiv.org/abs/1710.06542)], [[official blog post](https://blog.openai.com/generalizing-from-simulation/)] Pinto et al.; OpenAI, CMU
- ![gener] ![robot] Generalization, Manipulator

**Sim-to-Real Transfer of Robotic Control with Dynamics Randomization**
- [[arXiv](https://arxiv.org/abs/1710.06537)], [[blog](https://blog.openai.com/generalizing-from-simulation/)] Peng et al.; OpenAI, Berkeley
- ![gener] ![robot] Generalization, Manipulator

**A Deep Reinforcement Learning Chatbot**
- [[arXiv](https://arxiv.org/abs/1709.02349)] Serban et al.; MILA

**Learning model-based planning from scratch**
- [[arXiv](https://arxiv.org/abs/1707.06170)], [[blog](https://deepmind.com/blog/agents-imagine-and-plan/)] Pascanu et al.; Google DeepMind
- ![model] ![loco] Model-based, Locomotion

:star: **Imagination-Augmented Agents for Deep Reinforcement Learning** (I2As)
- [[arXiv](https://arxiv.org/abs/1707.06203)] [[blog](https://deepmind.com/blog/agents-imagine-and-plan/)] Weber et al.; DeepMind
- ![plan] ![transfer] ![atari] Planning, Transfer, Atari

**Distral: Robust Multitask Reinforcement Learning**
- [[arXiv](https://arxiv.org/abs/1707.04175)] Teh et al.; DeepMind
- ![transfer] ![maze] Transfer, Maze

**Emergence of Locomotion Behaviours in Rich Environments**
- [[arXiv](https://arxiv.org/abs/1707.02286)] [[blog](https://deepmind.com/blog/producing-flexible-behaviours-simulated-environments/)] Heess et al.; DeepMind
- ![loco] Locomotion

**Programmable Agents**
- [[arXiv](https://arxiv.org/abs/1706.06383v1)] Denil et al.; DeepMind
- ![loco] Locomotion

:star: **Evolution Strategies as a Scalable Alternative to Reinforcement Learning**
- [[arXiv](https://arxiv.org/abs/1703.03864v1)] Salimans et al.; OpenAI
- ![atari] Atari

**Neural Episodic Control**
- [[arXiv](https://arxiv.org/abs/1703.01988v1)] Pritzel et al.; DeepMind
- ![atari] Atari


## Year 2016
**The Predictron: End-To-End Learning and Planning**
- [[arXiv](https://arxiv.org/abs/1612.08810v2)] Silver et al.; DeepMind
- ![model] ![plan] ![maze] Model-based, Planning, Maze

**RL<sup>2</sup>: Fast Reinforcement Learning via Slow Reinforcement Learning**
- [[arXiv](https://arxiv.org/abs/1611.02779)] Duan et al.; Berkeley, OpenAI
- ![meta] ![maze] Meta-Learning, Maze

**Neural Architecture Search with Reinforcement Learning**
- [[arXiv](https://arxiv.org/abs/1611.01578)] B. Zoph and Quoc V. Le; Google Brain; ICLR.
- ![nn] NN

**Reinforcement Learning with unsupervised auxiliary tasks** (UNREAL)
- [[arXiv](https://arxiv.org/abs/1611.05397)] Jaderberg et al.; Google DeepMind
- :pencil: [**Notes**](./notes/unreal-agent.md)
- ![loco] ![atari] ![maze] Locomotion, Atari, Maze

:rocket: **Learning to act by predicting the future** (VizDoom 2016 Full DM Winner)
- [[arXiv](https://arxiv.org/abs/1611.01779)] Dosovitskiy, Koltun; Intel Labs
- ![maze] ![doom] Maze, Doom

**Multiagent Bidirectionally-Coordinated Nets for Learning to Play StarCraft Combat Games**
- [[arXiv](https://arxiv.org/abs/1609.02993)] Peng et al.; Alibaba Group, University College London
- ![marl] ![sc] MARL, Starcraft

**Playing FPS Games with Deep Reinforcement Learning** (VizDoom 2016 Limited DM 2nd place)
- [[arXiv](https://arxiv.org/abs/1609.05521)] Lample, Chaplot; Carnegie Mellon University
- ![maze] ![doom] Maze, Doom

[RTS:SC] **Episodic Exploration for Deep Deterministic Policies: An Application to StarCraft Micromanagement Tasks**
- [[arXiv](https://arxiv.org/abs/1609.02993)] Usunier et al.; Facebook AI Research
- ![sc] Starcraft

:rocket: **Asynchronous Methods for Deep Reinforcement Learning** (A3C)
- [[arXiv](https://arxiv.org/abs/1602.01783v2)] Mnih et al.; DeepMind
- :pencil: [**Notes**](./notes/a3c-agent.md)
- ![loco] ![atari] ![maze] Locomotion, Atari, Maze

## Year 2015

:star: **Dueling Network Architectures for Deep Reinforcement Learning** (Dueling DQN)
- [[arXiv](https://arxiv.org/abs/1511.06581)] Wang et al.; DeepMind
- ![atari] Atari

**Prioritized Experience Replay**
- [[arXiv](https://arxiv.org/abs/1511.05952v4)] Schaul et al.; DeepMind
- :pencil: [**Notes**](./notes/prioritized-exp-replay.md)
- ![atari] Atari

:star: **Deep Reinforcement Learning with Double Q-learning** (Double DQN)
- [[arXiv](https://arxiv.org/abs/1509.06461)] Hasselt et al.; DeepMind
- ![atari] Atari

**High-dimensional continuous control using generalized advantage estimation**
- [[arXiv](https://arxiv.org/abs/1506.02438)] Schulman et al.; Berkeley
- ![loco] Locomotion

:star: **Trust Region Policy Optimization** (TRPO)
- [[arXiv](https://arxiv.org/abs/1502.05477)] Schulman et al.; UC Berkeley
- ![atari] ![maze] ![loco] Atari, Maze, Locomotion

:rocket: **Human-level control through deep reinforcement learning** (DQN)

- [[Nature](http://www.nature.com/nature/journal/v518/n7540/full/nature14236.html)] [[pdf](hhttp://www.readcube.com/articles/10.1038/nature14236?shared_access_token=Lo_2hFdW4MuqEcF3CVBZm9RgN0jAjWel9jnR3ZoTv0P5kedCCNjz3FJ2FhQCgXkApOr3ZSsJAldp-tw3IWgTseRnLpAc9xQq-vTA2Z5Ji9lg16_WvCy4SaOgpK5XXA6ecqo8d8J7l4EJsdjwai53GqKt-7JuioG0r3iV67MQIro74l6IxvmcVNKBgOwiMGi8U0izJStLpmQp6Vmi_8Lw_A%3D%3D)] Mnih et al.; Google Deepmind
- :pencil: [**Notes**](./notes/dqn-agent.md)
- ![atari] Atari

**Mastering the game of Go with deep neural networks and tree search** (AlphaGo Master)

- [[Nature](https://www.nature.com/nature/journal/v529/n7587/full/nature16961.html)], [[reddit](https://www.reddit.com/r/MachineLearning/comments/42ytdx/pdf_mastering_the_game_of_go_with_deep_neural/)] Silver et al.; Deepmind, Google
- ![sp] ![plan] ![go] ![table] Self-Play, Planning, Go, Table

## Year 2013

:rocket: **Playing Atari with Deep Reinforcement Learning** (DQN)
- [[arXiv](https://arxiv.org/abs/1312.5602)] Mnih et al.; DeepMind Technologies
- ![atari] Atari

**Evolving Large-Scale Neural Networks for Vision-Based Reinforcement Learning**
- [[pdf](http://people.idsia.ch/~juergen/gecco2013torcs.pdf)] Koutnik et al.; IDSIA, USI-SUPSI
- ![evo] Evolution

## 2012 and earlier

**Horde: A Scalable Real-time Architecture for Learning Knowledge from Unsupervised Sensorimotor Interaction**
- [[pdf](https://www.cs.swarthmore.edu/~meeden/DevelopmentalRobotics/horde1.pdf)] Sutton et al. (2011);  University of Alberta, McGill University
- ![robot] ![loco] Manipulator, Locomotion

:star: **Policy Gradient Reinforcement Learning for Fast Quadrupedal Locomotion** 
- [[pdf](http://www.cs.utexas.edu/~ai-lab/pubs/icra04.pdf)] Kohl and Stone (2004); The University of Texas at Austin
- ![robot] ![loco] Manipulator, Locomotion

:star: **Autonomous helicopter flight via reinforcement learning**
- [[pdf](https://people.eecs.berkeley.edu/~jordan/papers/ng-etal03.pdf)] Ng et al. (2004); Stanford, Berkeley
- ![robot] Manipulator

:star: **Actor-Critic Algorithms**
- [[pdf](https://papers.nips.cc/paper/1786-actor-critic-algorithms.pdf)] Konda and Tsitsiklis (2003)

:star: **Temporal Difference Learning and TD-Gammon**
- [[pdf](http://cling.csd.uwo.ca/cs346a/extra/tdgammon.pdf)] Gerald Tesauro (1995)
- ![table] Table

:star: **Simple Statistical Gradient-Following Algorithms for Connectionist Reinforcement Learning** (REINFORCE)
- [[pdf](http://www-anw.cs.umass.edu/~barto/courses/cs687/williams92simple.pdf)] Ronald J. Williams (1992); Northeastern University

## Surveys
**A Brief Survey of Deep Reinforcement Learning**
  - [[arXiv](https://arxiv.org/abs/1708.05866)] Arulkumaran et al (2017).

## Books
:star: **Reinforcement Learning: An Introduction** (Complete Draft)
- [[pdf](http://incompleteideas.net/book/bookdraft2018jan1.pdf)] Richard S. Sutton and Andrew G. Barto (2018)

## Miscellaneous

**How to Read a Paper**
- [[pdf](http://ccr.sigcomm.org/online/files/p83-keshavA.pdf)] S. Keshav (2007); University of Waterloo

**ArXiv Sanity Preserver**: A recommender system for searching papers that are published on arXiv.
  - [http://www.arxiv-sanity.com/](http://www.arxiv-sanity.com/)
  
**GitXiv**: A recommender system for searching papers and their supplementary materials (if available).
  - [http://www.gitxiv.com/](http://www.gitxiv.com/)
  
  
