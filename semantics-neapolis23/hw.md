# Homework assignments
All homework assignments are provided via [GitHub Classroom](https://classroom.github.com/classrooms).
Each individual assignment should be submitted for review as a separate pull request (to some branch in your fork).
Pull request names should start with "HWn" where "n" is the number of the corresponding homework assignment.
E.g., the one about "functional programming in Coq" should start with "HW1", and
the one about "termination of the Euclid's algorithm"--"HW7".
The diff of each pull request should contain only the files relevant to the submitted assignment,
i.e., you may create a new branch for each new assignment and make a pull request from it to the previous one.
When the pull request is ready for review, add the [instructor](https://github.com/eupp/) as an assignee.

All assignments are given as Coq proof script files with `.v` extension.
You supposed to provide all missing definitions and prove admitted lemmas and theorems.
It is forbidden to modify provided definitions or lemma statements, 
however you are free to add your own new definitions or auxiliary lemmas.
Submitted solutions should not contain `admit` or `Admitted`.

All homework assignments are splitted into two parts: 
coq introductory problems and semantics related problems.

| HW       | 1      | 2      | 3      | 4  | 5  | 6  | 7  | 8  | 9  |
|----------|--------|--------|--------|----|----|----|----|----|----|
| Deadline | Feb 2  | Feb 2  | Feb 5  | -- | -- | -- | -- | -- | -- |
| Points   | 2      | 2      | 2      | -- | -- | -- | -- | -- | -- |

### Building Homework Projects ##

All repositories with homeworks are equipped with a `Makefile` 
that builds all the source files with the assignments. 
It is sufficient to run `make` command. 

Besides that, `make` command also creates `_CoqProject`. 
This file is required by the IDE in order to import the project files properly. 
Thus you might need to run `make` command before you open the homework files in your IDE.

**Important Note.**
Some assignments depend on files from previous assignments. 
For example, file `b2.v` imports `b1.v`.
In order for this import to work (both in batch and interactive mode)
you need to first build `b1.v` file. 
Thus, you should perform the following steps: 
1. complete `b1.v` assignments, check that everything compiles in interactive mode in your IDE;
2. run `make` to build `b1.v`;
3. open `b2.v` in your IDE --- now the import of `b1.v` should work. 

## Coq introductory problems

Clone the [repository](https://classroom.github.com/a/PDdEEN9_) with the problems.

1. `b1.v` --- functional programming in Coq: implement dictionary abstract datatype in Coq via partial function and list of pairs.  

2. `b2.v` --- tactics essentials: prove basic properties of dictionaries.

3. `b3.v` --- tactics practice: prove more properties of dictionaries. 

## Semantics problems

Clone the [repository](https://classroom.github.com/a/0MM1mmgs) with the problems.

4. `Id.v` and `State.v` --- prove properties of identifiers and states.

5. `Expr.v` --- prove properties of expression language.

6. `Stmt.v` --- prove properties of big step semantics.

7. `Euclid.v` --- prove termination of the Euclid's algoritm.  

8. `SmallStep.v` --- prove properties of small step semantics.

9. `Hoare.v` --- prove soundness of the Hoare logic rules.
