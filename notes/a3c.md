#Asynchronous Methods for Deep Reinforcement Learning
[[arXiv, pdf]](https://arxiv.org/pdf/1602.01783v2.pdf)  
Volodymyr Mnih, Adrià Puigdomènech Badia, Mehdi Mirza, Alex Graves, Tim Harley, Timothy P. Lillicrap, David Silver, Koray Kavukcuoglu.  

Yet another awesome work by Google DeepMind's team. Proposed A3C framework succeeds both on discrete and continious control problems, as well as at 3D maze navigation task.


##Keypoints on A3C method
  - **Asynchronous** - trained on multi-core CPU, instead of GPU (almost at the same speed);
  - **Actor-Critic** method, trained on-policy;
  - They've used both CNN-LSTM and CNN-FF networks, however CNN-LSTM shows better overall data efficiency and performance;
  - **RMSProp optimizer** with shared statistics across threads;
  - **No experience replay**, cause asynchronous training does the same effect of breaking correlations between frames, as experience replay;
  - Each thread runs it's own local copy of network's both actor and critic weights (W_local), which updates global shared weigts (W_global) after each gradient update: W_global <- W_local;
  
  
##Experimental Setup
  - **Optimizer**: RMSProp with shared statistics across threads with decay factor 0.99;  
  - **Learning rate** sampled uniformly from [1e-2; 1e-4];  
  - **Network**: Deep Q-Network architecture;  
  - **Action repeat** = 4 (it means to choose action at every 5th frame, and than repeat it at the next 4 frames);
  - **Discount factor** = 0.99;
  - Network **gradient ascent update performes** every 5 frames (i.e. max batch size = 5; skipped frames doesn't count), or at the   - terminal observation;
  - **Exploration rate** samples for each thread randomly. Starting from 1 and linearly annealing to some random variable, sampled from distribution of [0.1, 0.01, 0.5] with probabilites {0.4, 0.3, 0.3} respectively.


Information about proposed in this paper value-based asynchronous methods you may find in by [blog post](https://dbobrenko.github.io/2016/11/03/async-deeprl.html). However, to get a full picture of their idea, I recommend you to read the original paper.
