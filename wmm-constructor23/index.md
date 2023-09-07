# Weak Memory Models (Constructor University, Bremen, Fall'23)

Due to compiler and hardware optimizations, modern programming languages do not provide sequential consistent memory model, 
which guarantees that all concurrent behaviors of a program could be explained as a sequential execution of some interleaving of program's threads. 
Instead, they have weak memory models which allow more behaviors.

Such memory models have to balance between performance and guarantees provided to software developers, or, 
as one may say, the balance is actually between performance and sanity. 
That is, performance forces a memory model to allow more optimizations and, therefore, more program behaviors, 
whereas sanity forces a memory model to provide guarantees like data-race-freedom (DRF) 
that a program without races has only sequentially consistent executions which restricts the set of allowed executions.

In this course, we introduce weak memory concurrency, study modern formalisms for expressing memory models of programming languages and CPU architectures, 
and discuss open problems in the research area.

### Topics and Lectures

- 11.09: Introduction to weak memory (Lecture)
- 14.09: Basic operational semantics of concurrency (Lecture)
- 18.90: Basic operational semantics of concurrency (Seminar)
- **TBA**

### Grading System

Students earn points through a range of activities and assignments. 
You have the flexibility to select assignments from the list below that most align with your interests. 
Each activity has a set maximum point value. 
The course operates on a 100-point grading system. 
To achieve the highest possible grade, you should aim to accumulate a total of 100 points from the activities you choose.

#### Activities.

* Programming assignment **(50 points)**
** single semester-long customizable project

* Pen-and-paper proof assignments **(20 points)**

* Mechanized proof assignments in the Coq **(50 points)**

* Tooling assignments **(30 points)**
** typical assignment in this category requires a student to utilize some software to achieve a goal
** for example, one task is to verify a concurrent algorithm using given verification tool 

* Participation in seminars **(10 points)**
** solve challenges at seminar and explain your solution
** explain solutions to homework assignements (after their deadline)

* Written exam **(30 points)**

### Homework assignments

**TBA**