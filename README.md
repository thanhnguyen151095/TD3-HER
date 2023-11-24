# TD3+HER  for Fetch Robot Tasks

# TD3 (Twin Delayed DDPG): 

TD3 is an algorithm used in reinforcement learning. It's an extension of the Deep Deterministic Policy Gradients (DDPG) algorithm, designed to improve stability and sample efficiency in training deep reinforcement learning agents.

While DDPG can demonstrate impressive performance on occasions, it often proves to be fragile when it comes to hyperparameters and various tuning aspects. A common pitfall of DDPG is the significant overestimation of Q-values by the learned Q-function, leading to policy breakdowns as it capitalizes on errors within the Q-function. Twin Delayed DDPG (TD3) addresses this challenge through the incorporation of three crucial techniques:

* Clipped Double-Q Learning (Trick One): TD3 adopts a twin-Q approach, training two Q-functions instead of one. The smaller of the two Q-values is utilized to construct targets in the Bellman error loss functions.

* "Delayed" Policy Updates (Trick Two): TD3 implements less frequent updates to the policy (and target networks) compared to the Q-function. The suggested ratio is one policy update for every two Q-function updates.

* Target Policy Smoothing (Trick Three): TD3 introduces noise to the target action, making it more challenging for the policy to exploit Q-function errors by smoothing out Q-values along changes in action.

Collectively, these three strategies contribute significantly to enhancing performance compared to the baseline DDPG.

# HER (Hindsight Experience Replay): 
HER is a technique used in reinforcement learning to address the sparse reward problem. In many cases, an agent may receive a sparse reward signal, making it challenging to learn a good policy. HER addresses this by allowing the agent to learn from failures by considering alternative goals. It replays and learns from past experiences, even if the achieved outcome was not the original goal.

# TD3+HER

This combination aims to enhance the learning efficiency and robustness of the agents, especially in scenarios where the reward signals are sparse or challenging to define.

# Tasks

- FetchReach-v2: Fetch has to move its end-effector to the desired goal position.

- FetchPush-v2: Fetch has to move a box by pushing it until it reaches a desired goal position.

- FetchSlide-v2: Fetch has to hit a puck across a long table such that it slides and comes to rest on the desired goal.

- FetchPickAndPlace-v2: Fetch has to pick up a box from a table using its gripper and move it to a desired goal above the table.

# Results
|_|_|
|:---:|:---:|
![](Figures/Reach.png)| ![](Figures/Push.png)|
![](Figures/PickAndPlace.png)| ![](Figures/Slide.png)|

# Comparison of Results
|_|_|
|:---:|:---:|
![](Figures/Reach_comparison.png)| ![](Figures/Push_comparison.png)|
![](Figures/PickAndPlace_comparison.png)| ![](Figures/Slide_comparison.png)|

# Demo

Reach| Push|
-----------------------|-----------------------|
![](Videos/Reach.gif)| ![](Videos/Push.gif)|


Pick And Place | Slide|
-----------------------|-----------------------|
![](Videos/PickAndPlace.gif)|![](Videos/Slide.gif)


# Reference
- TD3: https://arxiv.org/abs/1802.09477
  
- Open AI: https://doi.org/10.48550/arXiv.1707.01495
  
- Environment: https://robotics.farama.org/envs/fetch/
