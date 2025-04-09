The **$\epsilon$-greedy decision policy** is a simple strategy used in [[reinforcement learning]] to balance **exploration VS exploitation**. Under this policy, at each decision point:

- With probability $\epsilon\in[0,1]$, the RL agent **explores** by selecting a random action.
- With probability $1 - \epsilon$, the agent **exploits** its current knowledge by choosing the action with the highest estimated value (i.e., the greedy action).
    
This approach allows the agent to occasionally try new actions (exploration), while mostly taking actions that are believed to yield the best outcome (exploitation).

#algorithm