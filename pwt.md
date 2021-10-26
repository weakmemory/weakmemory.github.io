# The Leaky Semicolon: Compositional Semantic Dependencies for Relaxed-Memory Concurrency

Program logics and semantics tell a pleasant story about sequential
composition: when executing `(S_1; S_2)`, we first execute `S_1` then `S_2`.
To improve performance, however, processors execute instructions out of
order, and compilers reorder programs even more dramatically.  By design,
single-threaded systems cannot observe these reorderings; however,
multiple-threaded systems can, making the story considerably less pleasant.
A formal attempt to understand the resulting mess is known as a ``relaxed
memory model.''  Prior models either fail to address sequential composition
directly, or overly restrict processors and compilers, or permit nonsense
thin-air behaviors which are unobservable in practice.

To support sequential composition while targeting modern hardware, we enrich
the standard event-based approach with _preconditions_ and
_families of predicate transformers_.
When calculating `[[S_1;S_2]]`, the predicate transformer applied to the
precondition of an event `e` from `[[S_2]]` is chosen based on the set of
events in `[[S_1]]` upon which `e` depends.  We apply this approach to two
existing memory models.

*TODO*: Links
