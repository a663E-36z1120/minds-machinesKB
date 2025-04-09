A **[[Model-free]]**, **off-policy** [[reinforcement learning]] method.

- In Q-learning, the **action-value function**, $Q(S_t, A_t)$, is updated after each transition using the rule:        $$Q_{\text{new}}(S_t, A_t) = Q_{\text{old}}(S_t, A_t) + \alpha \Bigl(R_{t+1} + \gamma \,\max_{a}\,Q\bigl(S_{t+1}, a\bigr) \;-\; Q_{\text{old}}(S_t, A_t)\Bigr)$$    where:
    - $S_t$ is the current state,
    - $A_t$ is the action taken (often governed by the [[Epsilon-greedy Decision Policy]]),
    - $R_{t+1}$ is the reward received,
    - $\alpha$ is the learning rate,
    - $\gamma$ is the discount factor,
    - $\max_{a},Q\bigl(S_{t+1}, a\bigr)$ estimates the best possible future value from the next state.
    
In the simplest form, the $Q$ function that the agent learns can just be a lookup table of actions and rewards.

- A Q-learner learns by doing the following:
	1. **Initialize**: The agent starts in state $s_1$ with a **randomly initialized table** of $Q$ values.
	2. **Action Selection** (epsilon-greedy): The agent chooses the action $a_1$ with the **highest-value** with probability $1 - \epsilon$, or it **picks a random action** with probability $\epsilon$.	    
	3. **Execute Action**: The agent **takes** that action $a_1$.
	4. **Observe Transition**: The environment **transitions** to a new state s2s_2 and provides a **reward** $r_1$.
	5. **Update Q-value**: The agent **updates only** the Q-value of $(s_1, a_1)$ using the Q-learning update rule.
	6. **Repeat**: The agent then **goes back** to step 2 for the next decision.

By repeatedly applying this update rule, a Q-learning agent gradually converges to an optimal value function $Q^*$, enabling it to select optimal actions without a model of the transition dynamics.

- Q-learning is **model-free** because it does not construct an internal model of the environment and learns directly the optimal actions instead. 
- Q-learning is an **off-policy** algorithm. This means that its update rule uses the maximum estimated value over all possible actions in the next state, regardless of the action actually taken by the behavior policy ($\max_{a},Q\bigl(S_{t+1}, a\bigr)$). Even if the agent is exploring with a non-optimal behavior policy, the update rule directs it toward learning the optimal policy.

#algorithm