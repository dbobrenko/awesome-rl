# Human-level control through deep reinforcement learning

Preceding work: [[arXiv, 2013](https://arxiv.org/abs/1312.5602)], [[pdf](https://arxiv.org/pdf/1312.5602.pdf)]  
Current work: [[Nature, 2015](http://www.nature.com/nature/journal/v518/n7540/full/nature14236.html)]


One of the most valuable paper in deep reinforcement learning field. Previously, it was used to be thought, that Q-Learning cannot guarantee a stable convergence with non-linear function approximator. But the recent breakthrough from Google DeepMind team shown, that Q-Learning **can** stabilize convergence with deep neural networks, however, it requires few tricks:
  1. Experience replay. The main idea is to break temporal correlations between consecutive updates;
  2. Off-policy learning. So that they have a separate **target policy network**, for computing TD target, that synchronize it's weights with behaviour policy network (that makes decisions during play) only after some amount of thousands of steps.
  
## Keypoints
  - Model-free: it solves the RL task using samples from environment, without explicit model reconstruction;
  - Off-policy: first, it uses "delayed" target network; secondly this target network follows greedy strategy, while behaviour policy is epsilon-greedy;
  - Learning from experience replay buffer;
  - The Q-Network learns to predict **expected accumulated discounted reward** `G` for any given state-action pair, so that `max_a Q(s,a; w) = G`;
  - The main idea is to minimize during learning the error between target reward and predicted one;
  - Reward clipping into the [-1.0; 1.0] range; Such hack limits error derivates, and allowes to use almost the same learning rate for different environments. However, the obvious limitation - agent can differentiate between "stong" or "weak" reward signals;

## Deep Q-Network Architecture
  - Input: 84x84x4 (4 last frames are stacked as channels);
  - Convolution 2D layer with 16 feature maps, filter 8x8, and stride 4;
  - ReLU activation;
  - Convolution 2D layer with 32 feature maps, filter 4x4, and stride 2;
  - ReLU activation;
  - Fully-connected that consists of 256 units;
  - ReLU activation;
  - Fully-connected that consists of A units, where A - number of actions in current environment;
  
## Experimental Setup
  - Action repeat on 4 frames. Skipped frames doesn't count by the algorithms as a "frames";
  - Total amount of frames: 10kk;
  - Replay memory size: 1kk;
  - Minibatch size: 32;
  - Epsilon annealed from 1.0 to 0.1 over the 1kk of frames;
  - Input Atari frame preprocessing: convert to grayscale initial 210x160 frame, resize -> 110x84, crop -> 84x84.
