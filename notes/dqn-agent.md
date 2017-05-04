# Human-level control through deep reinforcement learning

Preceding work: [[arXiv, 2013](https://arxiv.org/abs/1312.5602)], [[pdf](https://arxiv.org/pdf/1312.5602.pdf)]  
Current work: [[Nature, 2015](http://www.nature.com/nature/journal/v518/n7540/full/nature14236.html)]


One of the most valuable paper in deep reinforcement learning field. Previously, it was used to be thought, that Q-Learning cannot guarantee a stable convergence with non-linear function approximator. Google DeepMind team have shown, that Q-Learning **can** stabilize convergence with deep neural networks, however, it requires a few tricks:
  1. Experience replay. The main idea is to break temporal correlations between consecutive updates;
  2. Off-policy learning with experience replay.
  
## Key points
  - **Model-free**: it solves the RL task using samples from environment, without explicit model reconstruction;
  - **Off-policy**: they used separate target network for predicting TD target; Target network follows greedy strategy, while behavior policy is epsilon-greedy; Learning performed using experience replay buffer;
  - The Q-Network learns to predict **expected accumulated discounted reward** `G` for any given state-action pair, so that `max_a Q(s,a; w) = G`; The main idea is to minimize the error between target reward and predicted one;
  - Clipping positive rewards at 1 and negative rewards at -1, leaving 0 rewards unchanged; Such hack limits error derivatives, and allows to use almost the same learning rate for different environments. However, the obvious limitation, the agent won't be able to differentiate between strong and weak reward signals;
  - To encode the input frame, they took the max value for each pixel over the current and previous frame (actually previous frame, not the previous "seen frame" after action repeat). Such hack removes flickering from game objects;
  - Works only with **discrete action spaces**.
  
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
  - Repeats last selected action 4 frames. Skipped frames doesn't counts as a **"seen frames"**;
  - Total amount of frames: 10kk;
  - Replay memory size: 1kk; Minimum Replay buffer size: 50k;
  - Target network update frequency: 10k;
  - Discount factor gamma: 0.99;
  - Exploration epsilon annealed from 1.0 to 0.1 over the first 1kk of frames;
  - Input Atari frame preprocessing: convert to gray-scale initial 210x160 frame, resize -> 110x84, crop -> 84x84;
  - Input frame history length: 4 last raw frames (not "seen frames") stacks by channel axis and feeds to the Q-Network;  
  - RMSProp optimizer: 
    - Learning rate = 0.00025;
    - Mini-batch size: 32;
    - Grad. momentum: 0.95;
    - Squared grad. momentum: 0.95;
    - Min squared grad.: 0.01.
    
