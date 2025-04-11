Named after [[Andrey Markov]], the **Markov property** states that:

> **The future is independent of the past, given the present.**

A system that has the Markov property is considered "memoryless", where future evolutions of the system depends on the current state, not its past history. 

Formally, in the context of a [[Markov Decision Process]]:
$$P(S_{t+1} \mid S_t, A_t; S_{t-1}, A_{t-1}; \dots, S_0, A_0) = P(S_{t+1} \mid S_t, A_t)$$
This means that the next state $S_{t+1}$ depends **only** on the current state $S_t$ and action $A_t$, **not** on the full history of previous states and actions.

#property 

