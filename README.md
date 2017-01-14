# UNREAL agent

**Work in progress**

# Quick explanation

## Agent

UNREAL is an A3C CNN-LSTM agent trained on-policy, with auxiliary tasks and intrinsic rewards.
Auxiliary tasks share the same base A3C network with base agent and are trained off-policy from a short history of agent experience.

## Auxiliary tasks

**Control Task: Pixel changes.** 
**Control Task: Network features.** 
**Reward Task: Reward Prediction.** 
**Value Function Replay.** 

