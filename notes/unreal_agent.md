# Reinforcement Learning with unsupervised auxiliary tasks

[[arXiv, pdf]](https://arxiv.org/pdf/1611.05397.pdf)  
Max Jaderberg, Volodymyr Mnih, Wojciech Marian Czarnecki, Tom Schaul, Joel Z Leibo, David Silver & Koray Kavukcuoglu

**In progress.**


UNsupervised REinforcement and Auxiliary Learning (UNREAL) agent, described in Google DeepMind's paper, brings the A3C framework ([my A3C paper notes](./a3c.md)) together with auxiliary control and auxiliary reward tasks.  

## Keypoints
  - **Base agent**: A3C-based;
  - **Network architecture:** CNN-LSTM;
  - Base agent is trained **on-policy**;
  - **Auxiliary tasks:**
   - **CNN-LSTM weights are shared** with A3C base agent;
   - **Pixel changes (Control Task).** Learns separate policy for maximally changing pixels in each cell of n x n non-overlapping grid placed over the input image;
   - **Network features (Control Task).** Learns separate policy for maximally activating units in specific hidden layer.  
   - **Reward Prediction (Reward Task).** Processes a sequence of *N* (in paper *N = 3*) observations, learns to predict a reward for the next *N+1* observation. Reward Prediction task can be interpreted as a value learning on immidiate reward (without discountation, *gamma = 0*). Used only for shaping the features of the agent;
   -  **Value Function Replay** with randomly varying window for n-step returns computation. Used to increase the efficiency and stability of the auxiliary control tasks;  
   - Trained **off-policy** from replay buffer;
   - **Prioritized experience replay**: sample non-zero rewards and zero rewards with the same 0.5 probability; used to overcome reward sparsity;
   - **Update** performed every 20 environment steps.

## Experimental Setup

Base agent is trained on-policy with 20-step return.  
Auxiliary tasks are performed every 20 environment steps.  
**Auxiliary replay buffer size** = 20k of most recent observations.  
**Auxiliary Reward Prediction window length** = 3

