# Asynchronous Methods for Deep Reinforcement Learning
[[arXiv](https://arxiv.org/abs/1602.01783v2)], [[pdf](https://arxiv.org/pdf/1602.01783v2.pdf)]  
Volodymyr Mnih, Adrià Puigdomènech Badia, Mehdi Mirza, Alex Graves, Tim Harley, Timothy P. Lillicrap, David Silver, Koray Kavukcuoglu.  

Yet another awesome work by Google DeepMind's team. Proposed A3C framework succeeds both on discrete and continuous control problems, as well as at 3D maze navigation task.


## Key points on A3C method
  - **Asynchronous** - trained on multi-core CPU, instead of GPU (almost at the same speed);
  - They've used both CNN-LSTM and CNN-FF networks, however CNN-LSTM shows better overall data efficiency and performance;
  - **RMSProp optimizer** with shared statistics across all threads;
  - **No experience replay**, due to asynchronous training, which does the same effect of breaking correlations between frames, as experience replay;
  - Each thread runs it's own local copy of network's both actor and critic weights (`W_local`), which updates global shared weights (`W_global`) after every 40k frames: `W_global` <- `W_local`;
  
  
## Experimental Setup
  - **1 Frame** means 4 actual game frames, since skipped frames doesn't count; frames are counted across all threads;
  - **1 Epoch:** 4kk frames (used as convention in paper);
  - **Total iterations:** 80kk frames (or 20 epochs);
  - **Optimizer**: RMSProp with shared statistics across threads with decay factor 0.99;  
  - **Learning rate** ranges in [1e-2; 1e-4] interval;  
  - **Network**: Deep Q-Network architecture;  
  - **Action repeat:** 4;
  - **Discount factor:** 0.99;
  - **Gradient ascent update** every 5 frames or at the terminal observation (i.e. max batch size = 5);
  - **Exploration rate** starts from 1.0 and linearly anneals to epsilon_min variable, where `epsilson_min` is sampled from distribution  taken three values: {0.1, 0.01, 0.5} with probabilities {0.4, 0.3, 0.3} respectively, separately for each learner thread;
  - **Exploration annealing period:** first 4kk frames (or 1 epoch);
  - **Target network update interval:** every 40k frames;


Implementation and some intuition of the proposed in this paper value-based asynchronous methods you can check in my [blog post](https://dbobrenko.github.io/2016/11/03/async-deeprl.html). However, to get the full picture of their idea, I recommend you to read the original paper.
