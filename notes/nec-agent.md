#Neural Episodic Control
[[arXiv](https://arxiv.org/abs/1703.01988v1)], [[pdf](https://arxiv.org/pdf/1703.01988v1.pdf)]

Alexander Pritzel, Benigno Uria, Sriram Srinivasan, Adria Puigdom, Oriol Vinyals, Demis Hassabis, Daan Wierstra, Charles Blundell


Neural Episodic Control: a deep reinforcement learning agent that is able to rapidly assimilate new experiences and act upon them. Significantly much more data efficient compared to other state-of-the-art general purpose RL agents (such as [DQN](https://arxiv.org/abs/1312.5602v1), [A3C](https://arxiv.org/abs/1602.01783v2), [Retrace](https://arxiv.org/abs/1606.02647v2), [Q-lambda](https://arxiv.org/abs/1602.04951v2))


##Current Deep RL speed limitations
  * Low SGD learning rate;
  * Sparse reward signal;
  * Slow reward propagation due to learning on uncorrelated transitions from past experience (off-policy approaches, such as DQN);
  * Slow reward propagation due to slowly updating target network (again, in DQN-like agents).

##Keypoints
Agent consists of three components: 
  * Convolutional neural network (DQN architecture) that processes pixel images `s`;
  * A set of memory modules (one per action);
  * Final network that converts read-outs from the action memories into `Q(s, a)` values.


**IN PROGRESS**
  
