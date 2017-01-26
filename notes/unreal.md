# Reinforcement Learning with unsupervised auxiliary tasks

Paper: [arXiv, pdf](https://arxiv.org/pdf/1611.05397.pdf)

UNsupervised REinforcement and Auxiliary Learning (UNREAL) agent is an A3C-based CNN-LSTM agent trained on-policy, with auxiliary tasks and intrinsic rewards.  
Auxiliary tasks trained off-policy from a short history of agent experience and share the same base A3C network.  

## Auxiliary tasks

**Control Task: Pixel changes.** Learns separate policy for maximally changing pixels in each cell of n x n non-overlapping grid placed over the input image.  
**Control Task: Network features.** Learns separate policy for maximally activating units in specific hidden layer.  
**Reward Task: Reward Prediction.** Processes a sequence of *N* (in paper *N = 3*) observations, learns to predict a reward for the next *N+1* observation. To overcome reward sparsity - sample non-zero rewards with 0.5 probability. Reward Prediction task can be interpreted as a value learning on immidiate reward (without discountation, *gamma = 0*). Used only for shaping the features of the agent.  
**Value Function Replay** with randomly varying window for n-step returns computation. Used to increase the efficiency and stability of the auxiliary control tasks.  

## Experimental Setup

Base agent is trained on-policy with 20-step return.  
Auxiliary tasks are performed every 20 environment steps.  
Replay buffer size = 20k most recent observations.  

