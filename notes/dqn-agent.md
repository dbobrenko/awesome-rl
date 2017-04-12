# Human-level control through deep reinforcement learning

Preceding work: [[arXiv, 2013](https://arxiv.org/abs/1312.5602)], [[pdf](https://arxiv.org/pdf/1312.5602.pdf)]  
Current work: [[Nature, 2015](http://www.nature.com/nature/journal/v518/n7540/full/nature14236.html)]


One of the most valuable paper in deep reinforcement learning field. Previously, it was used to be thought, that Q-Learning cannot guarantee a stable convergence with non-linear function approximator. But the recent breakthrough from Google DeepMind team shown, that Q-Learning **can** stabilize convergence with deep neural networks, however, it requires few tricks:
  1. Experience replay. The main idea is to break temporal correlations between consecutive updates;
  2. Off-policy learning. So that they have a separate **target policy network**, for computing TD target, that synchronize it's weights with behavior policy network (that makes decisions during play), only after some amount of thousands of steps.
  
## Key points
  - Model-free: it solves the RL task using samples from environment, without explicit model reconstruction;
  - Off-policy: first, they use separate target network; secondly, the target network follows greedy strategy, while behavior policy is epsilon-greedy;
  - Learning from experience replay buffer;
  - The Q-Network learns to predict **expected accumulated discounted reward** `G` for any given state-action pair, so that `max_a Q(s,a; w) = G`; The main idea is to minimize the error between target reward and predicted one;
  - Clipping positive rewards at 1 and all negative rewards at -1, leaving 0 rewards unchanged; Such hack limits error derivatives, and allows to use almost the same learning rate for different environments. However, the obvious limitation - the agent isn't able to differentiate between strong or weak reward signals;
  - To encode the input frame, they take the max value for each pixel over the current and previous frame (actually previous frame, not the previous "seen frame"). Such hack removes flickering from game objects.

## Deep Q-Network Architecture (Nature, 2015)
  - Input: 84x84x4 (4 last frames are stacked as channels);
  - Conv2D layer with 32 feature maps, filter 8x8, and stride 4;
  - ReLU activation;
  - Conv2D layer with 64 feature maps, filter 4x4, and stride 2;
  - ReLU activation;
  - Conv2D layer with 64 feature maps, filter 3x3, and stride 1;
  - ReLU activation;
  - Fully-connected that consists of 512 units;
  - ReLU activation;
  - Fully-connected that consists of A units, where A - number of actions in current environment;
  
## Experimental Setup
  - Action repeat on 4 frames. Repeats last selected action this many times. Skipped frames doesn't count by the algorithm as a **"seen frames"**;
  - Total amount of frames: 10kk;
  - Replay memory size: 1kk; Minimum Replay buffer size: 50k;
  - Target network update frequency: 10k;
  - Discount factor gamma: 0.99;
  - Exploration epsilon annealed from 1.0 to 0.1 over the first 1kk of frames;
  - Input Atari frame preprocessing: convert to gray-scale initial 210x160 frame, resize -> 110x84, crop -> 84x84.
  - Input frame history length: 4 (just last raw frames, not "seen frames"; this amount of last frames stacks into one blob and feeds to the Q-Network);  
  - RMSProp optimizer: 
    - Learning rate = 0.00025;
    - Mini-batch size: 32;
    - Grad. momentum: 0.95;
    - Squared grad. momentum: 0.95;
    - Min squared grad.: 0.01.
    
