As opposed to [[Q-learning]], SARSA (State-Action-Reward-State-Action...) is a [[Model-free]],  **on-policy** [[reinforcement learning]] method.

The only difference between SARSA and Q-learning is that we use the update rule:
$$Q_{\text{new}}(S_t, A_t) = Q_{\text{old}}(S_t, A_t) + \alpha \Bigl(R_{t+1} + \gamma \bigl(\,Q\bigl(S_{t+1}, a\bigr) \;-\; Q_{\text{old}}(S_t, A_t)\bigr)\Bigr)$$
(vs. $\max_{a},Q\bigl(S_{t+1}, a\bigr)$ in Q-learning)

This makes SARSA an **on-policy** algorithm because instead of learning the next action with the highest Q-value regardless of the action taken by the RL agent as in Q-learning, SARSA learns the actual next action taken by the agent.

#algorithm