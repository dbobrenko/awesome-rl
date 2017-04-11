# Neural Episodic Control
[[arXiv](https://arxiv.org/abs/1703.01988v1)], [[pdf](https://arxiv.org/pdf/1703.01988v1.pdf)]

Alexander Pritzel, Benigno Uria, Sriram Srinivasan, Adria Puigdom, Oriol Vinyals, Demis Hassabis, Daan Wierstra, Charles Blundell


Neural Episodic Control (NEC): a deep reinforcement learning agent that is able to rapidly assimilate new experiences and act upon them. Significantly much more data efficient compared to other state-of-the-art general purpose RL agents (such as [DQN](https://arxiv.org/abs/1312.5602v1), [A3C](https://arxiv.org/abs/1602.01783v2), [Retrace](https://arxiv.org/abs/1606.02647v2), [Q-lambda](https://arxiv.org/abs/1602.04951v2)). In small data regime (< 20kk frames) NEC significantly outperforms other state-of-the-art RL agents. More precise, DQN with Prioritized Replay can reach NEC performance at 5 millions of frames, only after 40 millions of frames.


## Current Deep RL speed limitations
  * Low SGD learning rate;
  * Sparse reward signal;
  * Slow reward propagation due to learning on uncorrelated transitions from past experience (off-policy approaches, such as DQN);
  * Slow reward propagation due to slowly updating target network (again, in DQN-like agents).

## Key points
Agent consists of three components: 
  * Convolutional neural network (DQN architecture) that processes pixel images `s`;
  * A set of DND memory modules (one per action);
  * Final network that converts read-outs from the action memories into `Q(s, a)` values.

Differentiable Neural Dictionary:
  * For each action the action space NEC has a memory module kd-tree, called Differentiable Neural Dictionary (DND). It has two operation available: write and lookup;
  * Convolutional feature map is shares among each separate DND.

When it's time for agent to decide what action to take:
  1. ConvNet produces key `h` from current observation;
  2. The key `h` is then used to lookup for the nearest state-action value `Q` from DND;
  3. Take an action, using epsilon-greedy policy, based on received state-action value;
  4. Append new key-value pair to the DND;
  5. When the exact same key already exists in DND, the state-action value Q is updated the same way as the classic tabular Q-learning algorithm: `Q <- Q + alpha*(Q_new - Q)`;
  6. When memory's maximum capacity exceeds, they overwrite current `h` key as a nearest neighbor key in the kd-tree.

## Experimental Setup
  * No need in reward clipping!
  * Same preprocessing as in Nature DQN, Mnih et al., 2015;
  * NEC is trained on uniformly sampled batches from experience replay;
  * Replay buffer size: 100k
  * DND memory size from each action: 100k key-value pairs
  * Discount factor gamma: 0.99;
  * Replay update every 16 observed frames;
  * Minibatch size: 32;
  * KD-Tree number of nearest neighbors `p`: 50;
  * KD-Tree kernel function: `k(h, h_i) = 1 / (L2(h - h_i) + 0.001)`, where L2 - L2 euclidean distance `||.||^2`;

  
