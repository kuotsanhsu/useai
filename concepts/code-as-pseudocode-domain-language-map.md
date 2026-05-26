---
id: code-as-pseudocode-domain-language-map
kind: concept
status: draft
source:
  - user-thesis: "Different domains need different formal languages as pseudocode because each language exposes different semantic distinctions."
  - source-note: "cppreference C behavior categories"
  - source-note: "C11 draft N1570"
  - source-note: "Alexander Stepanov and C++ generic programming references"
  - source-note: "Bjarne Stroustrup C++ multi-paradigm references"
  - source-note: "Rust Book"
  - source-note: "Zig Language Reference"
  - source-note: "VHDL execution model reference"
  - source-note: "Erlang OTP documentation"
  - source-note: "Leslie Lamport, TLA+ and PlusCal references"
  - source-note: "ISO Prolog, Souffle Datalog, and ISO SQL references"
  - source-note: "Dyalog APL, Haskell, OCaml, Lean, Rocq, and Agda documentation"
tags: [software-engineering, pseudocode, specification, formal-methods, programming-languages, notation]
depends_on: [code-as-pseudocode-and-executable-specs]
related: [code-as-pseudocode-translation-protocol, stepanov-generic-programming-and-code-as-pseudocode, limits-of-language-and-formal-thought, glossary]
used_by: [code-as-pseudocode-and-executable-specs]
supersedes: []
---

# Code-As-Pseudocode Domain Language Map

This note is the domain-language catalog for [Code As Pseudocode And Executable Specs](code-as-pseudocode-and-executable-specs.md).

The point is not that every real language is good pseudocode. The point is that a language becomes good pseudocode when its native distinctions match the thing being explained.

## Language Map

The user's examples mostly hold up, with important qualifications.

- C and assembly
  - Good for: bit layouts, integer operations, ABI boundaries, memory representation, and instruction-near examples.
  - Caution: C is not portable assembly. It has an abstract machine and undefined, unspecified, and implementation-defined behavior; exact CPU semantics need fixed compiler, flags, target, ABI, and often assembly or ISA notation. The C behavior categories are summarized by [cppreference](https://docs.cppreference.com/w/c/language/behavior.html), and the C11 draft is available as [N1570](https://www.sigbus.info/n1570).

- C++ and STL-style generic programming
  - Good for: efficient algorithms, data-structure families, value semantics, iterator/range boundaries, type requirements, concept laws, complexity requirements, and multi-paradigm examples where representation and abstraction must stay in contact. C++ is especially useful when a code-as-pseudocode artifact should carry both the mathematical shape of an algorithm and the implementation costs that make it industrially meaningful.
  - Caution: C++ is useful pseudocode only under discipline: state the language subset, standard version, concept requirements, complexity obligations, ownership assumptions, and undefined-behavior boundaries. Do not let template machinery, overload cleverness, or object-oriented ceremony hide the algorithm. See [Stepanov, Generic Programming, And Code-As-Pseudocode](stepanov-generic-programming-and-code-as-pseudocode.md).

- Rust
  - Good for: ownership, borrowing, lifetimes, aliasing discipline, move semantics, and resource protocols checked by the compiler. The Rust Book's ownership and borrowing chapters are the right entry point: [ownership](https://doc.rust-lang.org/book/ch04-01-what-is-ownership.html) and [references and borrowing](https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html).
  - Caution: the borrow checker is conservative, and `unsafe` moves obligations back to the programmer. Unsafe Rust is useful pseudocode only when the extra invariants are explicitly stated.

- Zig
  - Good for: explicit allocation, allocator-passing, failure-aware systems code, C interop, and reasoning about where memory comes from and when it is released. The [Zig language reference](https://ziglang.org/documentation/master/) shows allocator-centered patterns rather than hidden memory management.
  - Caution: Zig does not provide Rust-style lifetime or alias proofs. Ownership conventions remain partly protocol and documentation.

- SystemVerilog and VHDL
  - Good for: event-based programming, discrete-event simulation, hardware structure, clocks, signal assignment, delta cycles, assertions, and scheduler-visible concurrency. Hardware is the central industrial domain, but the conceptual contribution is broader: these languages make event scheduling and process interaction first-class enough to expose distinctions that ordinary imperative pseudocode tends to hide. VHDL simulation is explicitly event/process driven; see this VHDL reference on [execution of a model](https://www.vhdl-online.de/vhdl_reference_93/execution_of_a_model).
  - Caution: simulation code and synthesizable hardware are not identical. A hardware-description language can be exact about simulation semantics while still misleading about real synthesized circuits if the subset and tool assumptions are unstated.

- Erlang, PlusCal, and TLA+
  - Good for: actor processes, message passing, supervision patterns, interleavings, invariants, liveness, and distributed-system design. Erlang/OTP documents built-in support for [concurrency, distribution, and fault tolerance](https://www.erlang.org/). TLA+ is a high-level language for modeling programs and systems, especially concurrent and distributed ones, with TLC and TLAPS as checking tools: [TLA+ home page](https://lamport.org/tla/tla.html). PlusCal is specifically a pseudocode-like algorithm language translated into TLA+: [PlusCal paper](https://lamport.org/pubs/pluscal.pdf).
  - Caution: Erlang execution explores one concrete run; TLA+/PlusCal explores a model. The abstraction boundary is part of the artifact.

- Prolog and Datalog
  - Good for: relations, unification, inference, recursive queries, reachability, graph facts, static analysis, and rule-based explanations. ISO Prolog standardizes syntax and semantic rules for the Prolog core: [ISO/IEC 13211-1](https://www.iso.org/standard/21413.html). Souffle describes Datalog as a declarative logic-based query language with recursive queries and uses in program analysis, security, graph databases, and declarative networking: [Souffle tutorial](https://souffle-lang.github.io/tutorial).
  - Caution: Prolog's search order, cut, negation, and operational control can diverge from the clean logical reading. Datalog is more restricted and often implementation-specific in syntax and performance.

- SQL and relational algebra
  - Good for: schemas, joins, projection, aggregation, constraints, keys, dependencies, and retrieval over relations. SQL is standardized through the ISO/IEC 9075 series; the 2023 framework page describes SQL as a database language standard: [ISO/IEC 9075-1:2023](https://www.iso.org/standard/76583.html).
  - Caution: SQL dialects differ, and NULL, bag semantics, transaction isolation, and optimizer behavior can make a query less mathematically transparent than relational algebra.

- APL, K, and array languages
  - Good for: whole-array transformations, rank and shape reasoning, compact numerical transformations, and columnar/time-series thought. Dyalog describes an ISO/IEC 13751-compliant APL engine with nested arrays and modern extensions: [Dyalog language engine](https://www.dyalog.com/dyalog/index.htm).
  - Caution: density is only expressive when the reader shares the notation. Without shared fluency, array code can become less communicative than longer functional or relational code.

- Haskell, OCaml, and ML-family languages
  - Good for: algebraic data types, pattern matching, higher-order functions, interpreters, type-directed design, denotational models, and effect-structured algorithms. The Haskell report frames Haskell as a general-purpose purely functional, non-strict language: [Haskell 98 introduction](https://www.haskell.org/onlinereport/intro.html). OCaml's module and functor system makes interface and implementation boundaries precise: [OCaml modules](https://ocaml.org/manual/5.4/modules.html).
  - Caution: Haskell laziness can hide cost and space behavior; OCaml permits effects and mutation. Neither is automatically a proof assistant.

- Rocq, Lean, Agda, and dependent type systems
  - Good for: dependent types, Curry-Howard reasoning, inductive and coinductive definitions, certified algorithms, proof-carrying specifications, and machine-checked mathematical claims. Lean presents itself as both a functional programming language and theorem prover: [Lean 4](https://lean4.dev/). Rocq, formerly Coq, describes itself as an interactive theorem prover and dependently typed programming language for mechanized reasoning: [Rocq](https://rocq-prover.org/). Agda is a dependently typed programming language and can be used as a constructive proof assistant: [Agda documentation](https://agda.readthedocs.io/en/latest/getting-started/what-is-agda.html).
  - Caution: proof burden, termination, positivity, productivity, trusted kernels, imports, and extraction behavior matter. A checked theorem is only as strong as the formal statement and assumptions.

## Use

Use this map when choosing the source artifact for code-as-pseudocode work. The map should stay concrete: each language family should say what it makes visible, where it misleads, and which assumptions must be named.
