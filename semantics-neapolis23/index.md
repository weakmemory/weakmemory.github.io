# Semantics of Programming Languages (Neapolis, Spring'23)

- [Instructions for setting up environment](INSTALL)
- [Previous class lecture videos (in Russian)](https://www.youtube.com/watch?v=sEiTqZmqY08&list=PLlb7e2G7aSpTA0aT2M1CvIWof3Osslo7Z)

<!-- Задания для знакомых с Coq: -->
<!-- 1. Доказать существование отсортированной перестановки списка так, -->
<!-- чтобы при экстракции получался Mergesort. -->
<!-- 2. Доказать полноту исчисления резолюций. -->

<!-- Задания для знакомых с Coq и семантиками: -->
<!-- 1. Реализовать операционную модель x86+FPGA из статьи [Iorga-al:OOPSLA21](https://doi.org/10.1145/3485497). -->

### Topics and Lectures
TBA

### Grading Schema
TBA

### Homework assignments

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

#### Coq introductory problems

Clone the [repository](https://classroom.github.com/a/PDdEEN9_) with the problems.

1. `b1.v` --- functional programming in Coq: implement dictionary abstract datatype in Coq via partial function and list of pairs.  

2. `b2.v` --- tactics essentials: prove basic properties of dictionaries.

3. `b3.v` --- tactics practice: prove more properties of dictionaries. 

#### Semantics problems

Clone the [repository](https://classroom.github.com/a/0MM1mmgs) with the problems.

4. `Id.v` and `State.v` --- prove properties of identifiers and states.

5. `Expr.v` --- prove properties of expression language.

6. `Stmt.v` --- prove properties of big step semantics.

7. `Euclid.v` --- prove termination of the Euclid's algoritm.  

8. `SmallStep.v` --- prove properties of small step semantics.

9. `Hoare.v` --- prove soundness of the Hoare logic rules.

### Recommended Textbooks and Resources
- Glynn Winskel. The Formal Semantics of Programming Languages;
- Coq tactics cheatsheets:
[Link 1](http://www.inf.ed.ac.uk/teaching/courses/tspl/cheatsheet.pdf),
[Link 2](https://www.cs.cornell.edu/courses/cs3110/2018sp/a5/coq-tactics-cheatsheet.html)
- [Coq Reference Manual](https://coq.inria.fr/distrib/current/refman/);
- Classical introductory course to logic via Coq, [Software Foundations. Logical Foundations](https://softwarefoundations.cis.upenn.edu/lf-current/index.html).

### Requirements
- Basic knowledge of functional programming will be a plus:
-- algebraic data types, lists, etc.
- Essential understanding and knowledge of propositional logic is expected:
-- conjunction, disjunction, logical implication, etc.
