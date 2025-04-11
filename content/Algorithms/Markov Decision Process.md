The Markov Decision Process (MDP) is the mathematical framework of [[reinforcement learning]]. It is named so because it has the [[Markov property]].

An MDP has 3 components:

- **States**: $S_t \in \mathcal{S}$
- **Actions**: $A_t \in \mathcal{A}(s)$
- **Rewards**: $R_t \in \mathcal{R}$

These components interact in a loop as follows:

At time step $t$:
- The **environment** determines state transitions probabilities based on the current state and action:
$$P(S_{t+1}∣A_t,S_t)$$
- The reinforcement learning agent samples **rewards** according to a reward function given the current state and action:
$$P(R_{t+1} \mid A_t, S_t)$$
- The reinforcement learning agent chooses the next **action** based on a **policy**, $\pi(A_t \mid S_t)$.

#algorithm 