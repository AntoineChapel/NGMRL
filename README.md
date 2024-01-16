# The Neoclassical Growth Model

This is a basic macroeconomic model in discrete time, infinite horizon. An agent maximizes its lifetime utility under budget constraint. The specification of the model presented here assumes complete depreciation of capital, but this is inconsequential.

\begin{align*}
\max_{\{c_t\}_0^\infty} &\sum_{t=0}^\infty \beta^t u(c_t)\\
\text{s.t } &c_t + k_{t+1} = f(k_t)\\
& k_0 \text{ given }
\end{align*}

Given the functional form chosen for our utility and production functions, this becomes:

\begin{align*}
\max_{\{c_t\}_0^\infty} &\sum_{t=0}^\infty \beta^t \log(c_t)\\
\text{s.t } &c_t + k_{t+1} = Ak_t^\alpha\\
&k_0 \text{ given }
\end{align*}

Which we can rewrite under unconstrained form:

\begin{align*}
\max_{\{k_{t+1}\}_{t=0}^\infty} \sum_{t=0}^\infty \beta^t \log(Ak_t^\alpha - k_{t+1}) \hspace{24pt} k_0 \text{ given }\\
\end{align*}


In this notebook, we will solve the problem using three different methods. The first one is classical value function iteration (VFI), which relies on the contraction mapping theorem to guarantee convergence.

The second one is one-agent Q-learning, in which an agent experiments with its environment following an $\epsilon$-greedy policy and determines the value of being in each state, based on the optimal action to take in each state. We note the similarity between VFI and Q-learning in that the "value_array" object constructed in VFI is identical to the $Q$ table constructed through Q-learning.

Finally, we experiment with neural networks by solving the problem through deep reinforcement learning. Instead of constructing an explicit $Q$ table, the deep Q-network (DQN) determines a linear approximation of the function $Q(s, a)$, which determines, after convergence, the optimal action to take in any state $s$.
