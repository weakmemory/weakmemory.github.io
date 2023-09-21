# Programming Assignment

Write an interpreter for simple [ISA](https://en.wikipedia.org/wiki/Instruction_set_architecture) 
with shared weak memory.

You need to support the following instruction set: 

- `r = 1` put constant into register
- `r1 = r2 # r3` binary operation on two registers 
- `if r goto L` conditional jump on label `L` 
- `load m #r1 r2` load value from memory by address stored in `r1` into register `r2` 
- `store m #r1 r2` store value from register `r2` into memory by address stored in `r1` 
- `cas m #r1 r2 r3` compare-and-swap value in memory by address stored in `r1`, 
     expected value is stored in `r2`, desired value is stored in `r3` 
- `fai m #r1 r2` fetch-and-increment value in memory by address stored in `r1`, 
     increment value is stored in `r2` 
- `fence m` memory fence instruction 

Notes on ISA:

- all values are assumed to be (fixed-width) integers 
- binary operation `#` can be one of the following: `+`, `-`, `*`, `/`
- each instruction can be prefixed with label, e.g. `L: r = 1`
- `m` denotes access mode: `SEQ_CST`, `REL`, `ACQ`, `REL_ACQ`, `RLX`

### Tasks

1. Basics **(8 points)**. \
   Implement a non-deterministic interpreter for the given ISA — it should choose one random execution on each run. 
   Split thread and storage subsystems in your implementation. 
   Implement SC and TSO memory subsystems. 
   *Notes: this task is a pre-requisite for all other tasks.*

2. Add support for PSO memory subsystem **(2 points)**.

3. Support tracing mode **(5 points)**. \
   In this mode the interpreter should print interleaving of a given execution 
   and intermediate states of thread and storage subsystems. 
   *Notes: this task is a pre-requisite for task 4 (interactive mode).*

4. Support interactive mode **(2 points)**. \ 
   The user should be able to make a decision on what execution to explore at each choice point. 

5. Support model-checking mode **(3 points)**. \ 
   This mode should enumerate all possible executions of a given program.

**... TBA ...** 
