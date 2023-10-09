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
- 18.09: Basic declarative semantics of concurrency (Lecture)
- 21.09: Basic operational semantics of concurrency (Seminar)
- 25.09: Basic declarative semantics of concurrency (Seminar)
- 28.09: Simplified C/C++ memory model --- Release-Acquire fragment (Lecture)
- 02.10: Correspondence between declarative and operational semantics SC, part 1 (Lecture)
- 05.10: Correspondence between declarative and operational semantics SC, part 2 (Lecture)
- 09.10: Review of homework assignments (Seminar)
- 12.10: (Seminar)
- 16.10: Correspondence between declarative and operational semantics StrongCOH, RA (Lecture)
- **TBA**

### Grading System

Students earn points through a range of activities and assignments. 
You have the flexibility to select assignments from the list below that most align with your interests. 
Each activity has a set maximum point value. 
The course operates on a 100-point grading system. 
To achieve the highest possible grade, you should aim to accumulate a total of 100 points from the activities you choose.

#### Activities.

* Programming assignment **(50 points)**
  * single semester-long project
  * students can use programming language of their choice
  * solution should be submitted as a GitHub repository
  * assessment of this task includes demonstration of the tool to the lecturer

* Pen-and-paper proof assignments **(20 points)**
  * should be submitted as TeX documents using provided document template

* Mechanized proof assignments in the Coq **(50 points)**
  * for students familiar with interactive proof assistants, there is an option to mechanize the proofs in Coq

* Tooling assignments **(30 points)**
  * typical assignment in this category requires from student to utilize some software to achieve a goal
  * for example, one task is to verify a concurrent algorithm using given verification tool 

* Participation in the seminars **(10 points)**
  * solve challenges at seminar and explain your solution
  * explain solutions to homework assignements (after their deadline)

* Written exam **(30 points)**
  * held at the end of the course

### Homework assignments

#### Programming assignment

Please find the description on the [dedicated page]({{ site.url }}/wmm-constructor23/programming-assignment.html).

**Deadline:** 26.11.2023

#### Theory assignments

- Basic operational semantics of concurrency \
  [\[pdf\]]({{ site.url }}/wmm-constructor23/wmm-operational-semantics-theory.pdf)
  [\[classroom\]](https://classroom.github.com/a/6VNr9oC1) \
  **Deadline:** 05.10.2023

- Basic declarative semantics of concurrency \
  [\[pdf\]]({{ site.url }}/wmm-constructor23/wmm-declarative-semantics-theory.pdf)
  [\[classroom\]](https://classroom.github.com/a/u9fRd7S3) \
  **Deadline:** 23.10.2023

**TBA**