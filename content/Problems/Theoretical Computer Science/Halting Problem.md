The halting problem is the question of whether a computer program ([[Turing machine]]) will eventually stop (halt) or run forever on a given input. 

#problem

[[Alan Turing]] proved in 1936 that there is no general algorithm that can solve this problem for all possible programs and inputs — meaning it's not [[decidable]]. Turing's proof of the **undecidability of the halting problem** uses a **diagonalization** argument by contradiction:

1. **Assume** there exists a program `H(P, I)` that correctly determines whether any program `P` halts on input `I`.

2. Construct a new program `D(x)` that:
   - Uses `H(x, x)` to check if program `x` halts when run on itself.
   - If `H(x, x)` says it **halts**, then `D(x)` **loops forever**.
   - If `H(x, x)` says it **doesn't halt**, then `D(x)` **halts**.

3. Now ask: What happens if we run `D` on itself, i.e., `D(D)`?
   - If `H(D, D)` says it halts → `D(D)` loops forever.
   - If `H(D, D)` says it doesn't halt → `D(D)` halts.

This contradiction shows that `H` cannot exist. Therefore, **no algorithm can universally decide whether programs halt**.

#idea