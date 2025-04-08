Proposed by [[Alan Turing]] in *'On computable numbers, with an application to the [[Entscheidungsproblem]]'* (1936), a Turing machine is a theoretical model of computation that manipulates symbols on an infinite tape of boolean values ({0, 1}) with a read/write head according to some internally stored state and a set of instructions. 

We can program a Turing machine with the following simplified instruction set:

$S, R, W, M, U$, 

which executes as follows on a Turing machine:

**if:**
- $S$ (int): currently in state $S$
- $R$ (bool): reading $R$ from the tape

**then:**
- $W$ (bool): write $W$
- $M$ ({left, right, stay}): move $M$
- $U$ (int $\cup$ {halt}): update state to $U$


#machine
