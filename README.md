# The Neoclassical Growth Model

This is a basic macroeconomic model in discrete time, infinite horizon. An agent maximizes its lifetime utility under budget constraint. Solving the model requires finding a policy function that maps every possible value for $k_t$ to the optimal $k_{t+1}$.

In this notebook, I will solve the Neoclassical Growth Model using three different methods. The first one is classical value function iteration (VFI), which relies on the contraction mapping theorem to guarantee convergence.

The second one is one-agent Q-learning, in which an agent experiments with its environment following an $\epsilon$-greedy policy and determines the value of being in each state, based on the optimal action to take in each state. We note the similarity between VFI and Q-learning in that the "value_array" object constructed in VFI is identical to the $Q$ table constructed through Q-learning.

Finally, we experiment with neural networks by solving the problem through deep reinforcement learning. Instead of constructing an explicit $Q$ table, the deep Q-network (DQN) determines a linear approximation of the function $Q(s, a)$, which determines, after convergence, the optimal action to take in any state $s$.
