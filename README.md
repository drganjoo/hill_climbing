# Hill Climbing

This repository shows the hill climbing algorithm using adaptive scaling on OpenAI Gym's CartPole-V0
## Agent

a) Create a simple policy: **weight * state = output**

OR

b) Create a neural network agent that maps states to output. Since the action space is discrete, **softmax** is used to make the output a probablity and then the action with maximum probability is chosen.


## Basic Algorithm

1. Initialize weights
2. For 1000 episodes do the following:
3. Run one episode using the given weights
4. Save overall score achieved in the episode and compute discounted reward
5. If discounted reward is **better or equal** than best ever episode, then remember the current weights as best_weights
6. For best episodes, adapt scale by reducing it by 2 (max of 1e-3)
7. For other epusodes, adapt scale by increasing it by 2 (min of 2)
8. Update weights by generating np.random weights * scale
9. Start again from 3
10. If the mean of scores from last 100 episodes exceeds 195, stop loop

