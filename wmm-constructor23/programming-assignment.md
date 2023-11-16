# Programming Assignment

Write an interpreter for simple [ISA](https://en.wikipedia.org/wiki/Instruction_set_architecture) 
with shared weak memory.

You need to support the following instruction set: 

- `r = 1` put constant into register
- `r1 = r2 # r3` binary operation on two registers 
- `if r goto L` conditional jump on label `L` 
- `load m #r1 r2` load value from memory by address stored in `r1` into register `r2` 
- `store m #r1 r2` store value from register `r2` into memory by address stored in `r1` 
- `r1 := cas m #r2 r3 r4` compare-and-swap value in memory by address stored in `r2`, 
     expected value is stored in `r3`, desired value is stored in `r4`, 
	 shoud return the actually read value in register `r1`.  
- `r1 := fai m #r2 r3` fetch-and-increment value in memory by address stored in `r2`, 
     the value to increment by is stored in `r3`,
	 should return the read value prior increment in register `r1`.
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

6. Support Strong Release Acquire (SRA) model storage subsystem **(5 points)**. \
   Support memory accesses annotated with relaxed and release/acquire modes.

7. In addition to SRA, support Release Acquire (RA) model storage subsystem **(5 points)**.

8. For SRA (and RA), add support for release and acquire fences **(5 points)**.

9. For SRA (and RA), add support for full seq-cst fence **(5 points)**.

10. Generate execution graphs **(10 points)**. \
    Output graphs in `.dot` format and visualize them using [graphviz](https://graphviz.org/doc/info/lang.html).
