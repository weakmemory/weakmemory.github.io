# The Leaky Semicolon: Compositional Semantic Dependencies for Relaxed-Memory Concurrency

Program logics and semantics tell a pleasant story about sequential
composition: when executing `(S1; S2)`, we first execute `S1` then `S2`.  To
improve performance, however, processors execute instructions out of order,
and compilers reorder programs even more dramatically.  By design,
single-threaded systems cannot observe these reorderings; however,
multiple-threaded systems can, making the story considerably less pleasant.
A formal attempt to understand the resulting mess is known as a ``relaxed
memory model.''  Prior models either fail to address sequential composition
directly, or overly restrict processors and compilers, or permit nonsense
thin-air behaviors which are unobservable in practice.

To support sequential composition while targeting modern hardware, we enrich
the standard event-based approach with _preconditions_ and _families of
predicate transformers_.  When calculating the meaning of `(S1;S2)`, the
predicate transformer applied to the precondition of an event `e` from `S2`
is chosen based on the set of events in `S1` upon which `e` depends.  We
apply this approach to two existing memory models.

## Paper:

- Alan Jeffrey, James Riely, Mark Batty, Simon Cooksey, Ilya Kaysin, Anton Podkopaev.  
  **The Leaky Semicolon: Compositional Semantic Dependencies for Relaxed-Memory Concurrency**  
  Proc. ACM Program. Lang., 6(POPL), January 2022.  
  [[Paper](https://github.com/chicago-relaxed-memory/seqcomp/raw/master/paper/DRAFT.pdf) |
   [Paper with Draft Appendices](https://github.com/chicago-relaxed-memory/seqcomp/raw/master/paper/DRAFT-APPENDIX.pdf) |
   [Artifact @Zenodo](https://doi.org/10.5281/zenodo.5675056)]
   <!-- [Short Video](https://youtu.be/vpkl2gR_wsQ) | -->
   <!-- [Long Video](https://youtu.be/pj912bYJ0Do)] -->

## Talk (20min) and Teaser (5min):

  [![Presentation](http://img.youtube.com/vi/pj912bYJ0Do/0.jpg)](http://www.youtube.com/watch?v=pj912bYJ0Do "Presentation") 
  [![Teaser](http://img.youtube.com/vi/vpkl2gR_wsQ/0.jpg)](http://www.youtube.com/watch?v=vpkl2gR_wsQ "Teaser")

<!---  [Full conference feed (We are at hour 4 of 8)](https://t.co/GEjkrkhjnM) --->
  
## People:

- [Alan Jeffrey](https://asaj.org/), Roblox
- [James Riely](https://fpl.cs.depaul.edu/jriely/), DePaul University
- [Mark Batty](https://www.kent.ac.uk/computing/people/3126/batty-mark), University of Kent
- [Simon Cooksey](https://graymalk.in/), University of Kent
- [Ilya Kaysin](https://ilya.fun/), JetBrains Research and University of Cambridge
- [Anton Podkopaev](https://podkopaev.net/), HSE University
