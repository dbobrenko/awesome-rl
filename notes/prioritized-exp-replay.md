#Prioritized Experience Replay

[arXiv, pdf](https://arxiv.org/pdf/1511.05952v4.pdf)  
Tom Schaul, John Quan, Ioannis Antonoglou and David Silver

The main idea of this paper is to increase data efficiency by training on hard examples from replay buffer more often. This idea is similar to popular in deep learning idea "Online Hard Example Mining" (OHEM). In this paper they introduce two approaches of prioritization, First one is based on temporal-difference error (TD), second one is rank-based.

##Keypoints
