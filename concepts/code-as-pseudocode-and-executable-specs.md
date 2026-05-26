---
id: code-as-pseudocode-and-executable-specs
kind: concept
status: draft
source:
  - user-thesis: "Actual programming and formal languages should often replace LaTeX-style pseudocode because they are executable or checkable and have standard semantics."
  - source-note: "Leslie Lamport, The PlusCal Algorithm Language"
  - source-note: "Leslie Lamport, A High-Level View of TLA+"
  - source-note: "Donald Knuth, Literate Programming"
  - source-note: "Dafny Reference Manual"
  - source-note: "Alloy Analyzer FAQ"
  - source-note: "Rust Reference"
  - source-note: "Rust Book"
  - source-note: "Zig Language Reference"
  - source-note: "Erlang OTP documentation"
  - source-note: "Souffle Datalog Tutorial"
  - source-note: "ISO SQL and Prolog standards"
  - source-note: "Lean and Rocq documentation"
  - source-note: "Agda documentation"
  - source-note: "Stanford Encyclopedia of Philosophy on Godel and intuitionistic type theory"
  - source-note: "Homotopy Type Theory book"
  - source-note: "Cubical Type Theory paper"
  - source-note: "cppreference C behavior categories"
  - source-note: "WebAssembly Specifications"
  - source-note: "Alan Kay, The Early History of Smalltalk"
  - source-note: "Alan Kay and Adele Goldberg, Personal Dynamic Media"
  - source-note: "Edsger Dijkstra, Guarded Commands and Notes on Structured Programming"
  - source-note: "Edsger Dijkstra, On the Cruelty of Really Teaching Computing Science"
  - source-note: "Alexander Stepanov, STL and generic programming references"
  - source-note: "QuickCheck and property-based testing references"
  - source-note: "Translation validation, CompCert, Csmith, and LLM code translation references"
tags: [software-engineering, pseudocode, specification, formal-methods, programming-languages, executable-specification, notation]
depends_on: [code-simulacra-and-formal-shadows, english-as-programming-interface, soundness-validity-and-software-evidence]
related: [code-as-pseudocode-domain-language-map, code-as-pseudocode-translation-protocol, stepanov-generic-programming-and-code-as-pseudocode, limits-of-language-and-formal-thought, programming-hyperreality, symbolic-reasoning-and-meaning, causal-code-intelligence, glossary]
used_by: [code-as-pseudocode-translation-protocol]
supersedes: []
---

# Code As Pseudocode And Executable Specs

This note preserves and sharpens the user's thesis: when a concept is difficult to express precisely in English or LaTeX-style pseudocode, it is often better to express it in an actual programming, modeling, simulation, query, hardware-description, or proof language whose syntax, semantics, and checking tools are already shared.

The target is not mathematical notation itself. The target is informal algorithm blocks that look rigorous while leaving too much unspecified: data representation, evaluation order, atomicity, aliasing, nondeterminism, effects, ownership, concurrency, invariants, and proof obligations.

For the broader philosophical frame that treats natural language, notation, code, specifications, and proofs as thought instruments rather than passive containers, see [Limits Of Language And Formal Thought](limits-of-language-and-formal-thought.md).

For the practical workflow that translates a best-fit source artifact into a business-mandated implementation language, see [Code-As-Pseudocode Translation Protocol](code-as-pseudocode-translation-protocol.md).

## Cleaned Thesis

LaTeX-style pseudocode is often a weak medium for serious technical ideas. It can be readable, but it often lacks rigor, executable feedback, standard semantics, and enough expressive structure for the domain.

Free-form notation is not automatically more expressive. It can be more convenient, but it can also be less communicative because the reader has to infer which marks are conventional, which are invented for the paper, which are mechanically checkable, and which semantic obligations they carry. This is especially visible in type theory and other boundary-pushing fields, where new notation is sometimes necessary but often difficult to read until a community, formal system, and tool culture stabilize around it.

For many concepts, a real language is a better pseudocode:

- C for the C abstract machine and bit-level interfaces; assembly or ISA notation for explicit instruction semantics;
- C++ for STL-style generic algorithms, value semantics, type requirements, and efficient abstraction when algorithmic concepts are the point;
- Rust for ownership, borrowing, lifetimes, and aliasing discipline;
- Zig for explicit memory and allocation choices;
- SystemVerilog or VHDL for event-based programming and discrete-event simulation, with hardware as the central industrial domain;
- Erlang, PlusCal, or TLA+ for concurrent and distributed algorithms;
- Prolog or Datalog for rule-based inference;
- SQL or relational algebra for relational information management;
- APL, K, or array languages for array computation;
- Haskell, OCaml, or ML-family languages for functional structure;
- Rocq, Lean, Agda, or related proof assistants for dependent types, Curry-Howard reasoning, induction, and coinduction.

The benefit is that the artifact can often be run, typechecked, model checked, mechanically proved, debugged, observed, or compiled. It can serve as a proof of concept, minimum viable product or model, executable explanation, or specification artifact. It also fills gaps that English leaves open.

The strongest corrected form:

- Use real formal languages as disciplined pseudocode when their semantics match the domain.
- Treat code-like artifacts as specifications only when their level of abstraction and checking obligations are explicit.
- Keep natural language for motivation, scope, interpretation, tradeoffs, and model-world fit.
- Treat AI-assisted translation into a mandated implementation language as a modern deployment pattern built on top of code-as-pseudocode, not as the definition of code-as-pseudocode itself.

## Why The Thesis Is Strong

Pseudocode is attractive because it hides irrelevant implementation detail. Its weakness is that it can also hide relevant detail.

Lamport's [PlusCal paper](https://lamport.org/pubs/pluscal.pdf) states the problem almost directly: ordinary pseudocode lacks precise meaning and can only be checked by hand. PlusCal was designed as an algorithm language that can replace pseudocode, translate to TLA+, and be checked with TLC. The same paper also says algorithms are different from programs, which is the needed guardrail: actual executable code is not automatically the right abstraction.

Lamport's [high-level TLA+ overview](https://lamport.azurewebsites.net/tla/high-level-view.html) gives the broader model frame. TLA+ models software above the code level; PlusCal is meant to replace pseudocode with precise, testable code; and no model is a complete description of a real system. This supports the thesis but blocks the overstatement that a runnable artifact simply is the system's truth.

Knuth's [literate programming](https://cs.stanford.edu/~knuth/lp.html) is a nearby tradition: combine programming language and documentation language, treating a program as literature for human readers. This is not the same as executable pseudocode, but it supports the underlying idea that readable exposition and actual code should not be separated more than necessary.

Dafny shows the hybrid case. Its [reference manual](https://dafny.org/dafny/DafnyRef/DafnyRef) describes a programming language with built-in specification constructs, verification, and compilation. It also notes that specifications and ghost constructs are used only for verification and omitted from executable code. That distinction is central: the best "code as pseudocode" may be code plus non-runtime logical material.

Alloy is another useful counterexample to naive executability. The [Alloy Analyzer FAQ](https://alloytools.org/faq/how_does_the_alloy_analyzer_differ_from_model_checkers.html) says Alloy is a model finder, not a conventional model checker, and supports partial declarative models. This is exactly the kind of artifact that can be more rigorous than pseudocode without being executable in the ordinary program-running sense.

## Brief Lineage

The idea is not academically novel. Its components are old and serious. What is newly interesting is the industrial pattern: use a best-fit formal artifact as the semantic anchor, then use AI-assisted translation and validation to satisfy business constraints that force an unsuitable production language.

Alan Kay supports the thesis indirectly. In [The Early History of Smalltalk](https://worrydream.com/EarlyHistoryOfSmalltalk/), Kay frames Smalltalk and personal computing as a qualitative shift in medium, not just a better way to do older mainframe work. In [Personal Dynamic Media](https://tinlizzie.org/VPRIPapers/m1977001_dynamedia.pdf), Kay and Adele Goldberg frame the Dynabook as a personal dynamic medium rather than a passive document. Smalltalk's emphasis on protected cells communicating through messages, late binding, live systems, and the computer as a medium for thought supports the claim that language and environment shape what can be thought and built. But Kay is not primarily a specification theorist. He would more naturally support code-as-pseudocode as a live medium for powerful ideas, not as a narrow verification workflow.

Dijkstra supports the thesis through discipline, derivation, and semantic control. In [Concern for Correctness as a Guiding Principle for Program Composition](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD288.html), he describes a rough sketch as an abstract version of the final program, or even as the program for a hypothetical machine whose assumed primitives are refined later. In [Structured Programming](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD268.html), he argues that correctness depends on reasoning from the static program text, not sampling executions. In [Guarded Commands](https://www.cs.utexas.edu/~EWD/transcriptions/EWD04xx/EWD472.html), he gives predicate-transformer machinery for program derivation. But Dijkstra would likely resist a loose "AI will translate it" framing. For him, the translation must preserve derivable meaning, not merely plausible behavior.

Lamport is the direct specification lineage. His [PlusCal paper](https://lamport.org/pubs/pluscal.pdf) explicitly says algorithms are different from programs, that ordinary pseudocode has no precise meaning and can only be checked by hand, and that PlusCal can replace pseudocode by translating to TLA+ for model checking and formal reasoning. His [high-level TLA+ overview](https://lamport.azurewebsites.net/tla/high-level-view.html) also gives the key guardrail: model above the code level, because coding skill cannot repair a bad high-level design.

The important tension is that Lamport also cautions against ordinary programming languages as algorithm languages. This does not refute code-as-pseudocode. It refines it: the right artifact may be executable code, but it may also be a model, proof, query, abstract machine, hardware-description fragment, relational schema, or purpose-built algorithm language like PlusCal.

Stepanov is the direct C++ and generic-programming lineage. His STL work shows how actual C++ can encode efficient algorithmic theories when concepts, laws, complexity requirements, and value semantics are made explicit. For the focused treatment, see [Stepanov, Generic Programming, And Code-As-Pseudocode](stepanov-generic-programming-and-code-as-pseudocode.md).

## Core Distinctions

### Executable Code Versus Specification

Executable code says how one artifact behaves under one language implementation, runtime, environment, and set of inputs.

A specification says what behavior is allowed, required, forbidden, or abstractly intended.

The overlap is real but not total. Code can function as a specification when:

- it is written at the right abstraction level;
- irrelevant operational detail is factored away;
- preconditions, postconditions, invariants, traces, or properties are explicit;
- the checker can reject relevant mistakes;
- readers know which behavior is normative and which is accidental.

Code fails as specification when:

- accidental implementation choices are mistaken for requirements;
- optimization details obscure the invariant;
- undefined, unspecified, or implementation-defined behavior enters the example;
- the artifact demonstrates one execution but claims all executions;
- the domain model is hidden inside control flow.

### Implementation Versus Model

An implementation must run in the world.

A model must expose the structure relevant to a question.

The model may omit memory layout, scheduling, latency, allocation, serialization, retry behavior, hardware, security boundaries, UI state, or failure recovery. That omission can be good if it removes noise. It becomes dangerous when the omission is forgotten.

The practical question is not "is it real code?" but "what claim does this artifact license?"

- A Python script may license "this transformation is concrete and reproducible."
- A TLA+ spec may license "this invariant held in the explored state space."
- A Dafny file may license "this method satisfies these annotations, assuming the verifier and trusted base."
- A Lean theorem may license "this proposition follows from these definitions, axioms, and imported theorems."
- A benchmark may license "this implementation behaved this way under this setup."

None of these automatically licenses "the production system is correct."

### Semantics Versus Compiler Behavior

"It compiles" is not the same as "its meaning is clear."

Some languages have intentionally underspecified or evolving areas. The [Rust Reference](https://doc.rust-lang.org/stable/reference/behavior-considered-undefined.html) says the list of undefined behavior is not exhaustive and that there is not yet a complete formal model of unsafe Rust semantics. C and C++ have well-known categories such as [undefined, unspecified, and implementation-defined behavior](https://docs.cppreference.com/w/c/language/behavior.html). So even actual code may fail as pseudocode if the example depends on corners where the language does not provide a portable, stable meaning.

By contrast, the [WebAssembly specifications](https://webassembly.org/specs/) explicitly define module semantics independent of a concrete embedding. That kind of standard is closer to the ideal behind code-as-pseudocode: a notation whose meaning is not merely what today's compiler happened to do.

The rule:

- Use language semantics for exposition, not accidental compiler behavior.
- If compiler behavior matters, say which compiler, target, flags, runtime, ABI, and platform are part of the example.

### Domain Notation Versus General Notation

The best pseudocode language is often not the most popular language. It is the language whose primitives match the conceptual pressure.

Concurrency needs atomicity, interleavings, fairness, nondeterminism, and traces. That makes TLA+, PlusCal, Erlang, Promela, or process calculi more natural than a loop in Python.

Memory safety needs ownership, aliasing, borrowing, allocation, lifetime, provenance, and deallocation. Rust, C, Zig, separation logic, or verifier-oriented languages expose different parts of that space.

Relational work needs joins, constraints, keys, dependencies, and query plans. SQL, relational algebra, Datalog, or Alloy may say more in less space than imperative pseudocode.

Proof work needs propositions, terms, induction principles, recursive definitions, equality, rewriting, and trusted checking. Lean, Rocq, Agda, Isabelle, or Dafny are often better than prose plus displayed formulas.

The guiding principle:

- Choose the notation whose native operations are the domain's important distinctions.

## Domain Language Findings

The user's examples mostly hold up, with important qualifications. The full catalog now lives in [Code-As-Pseudocode Domain Language Map](code-as-pseudocode-domain-language-map.md), so this note can stay focused on the thesis and framework.

The short form:

- use C, assembly, or ISA notation when representation and machine-near behavior are the point;
- use Rust or Zig when resource protocols, ownership conventions, allocation, and low-level systems boundaries are the point;
- use SystemVerilog or VHDL when event scheduling, process interaction, clocks, signals, and discrete-event simulation are the point;
- use Erlang, PlusCal, TLA+, Promela, or process calculi when concurrency and distributed behavior are the point;
- use Prolog, Datalog, SQL, relational algebra, Alloy, APL, K, Haskell, OCaml, Lean, Rocq, Agda, Isabelle, Dafny, or nearby languages when their native primitives expose the structure being specified.

The recurring caution is claim hygiene: a real language is useful pseudocode only when the artifact says which semantics, tool version, subset, abstraction level, and obligations are in force.

## Useful Framework

Use four layers.

### Layer 1: Intent

Natural language explains why the artifact exists, what problem it addresses, what is intentionally omitted, and how to read it.

This layer should not pretend to be the formal semantics.

### Layer 2: Formal Artifact

This is the code, spec, model, proof, query, circuit description, or rule base.

It should be as small as possible while preserving the important structure.

### Layer 3: Checker Or Observer

This is the compiler, typechecker, verifier, model checker, interpreter, proof kernel, test runner, simulator, or database engine.

Its authority must be named. "Executable" is too vague; running one sample, checking all bounded states, proving a theorem, and compiling to production code are different evidential acts.

### Layer 4: Claim

This says what the artifact now entitles us to believe.

Good claims are narrow:

- "The parser accepts these examples."
- "The invariant holds for this bounded model."
- "The theorem checks under these imports."
- "The ownership relation is rejected by Rust's borrow checker."
- "The SQL query expresses this relational shape."

Bad claims jump levels:

- "The model checked, therefore production is correct."
- "The code compiles, therefore the algorithm is clear."
- "The theorem checks, therefore the requirement is the right one."
- "The pseudocode is readable, therefore the hard parts are specified."

## Failure Modes

### Accidental Detail Capture

Actual code can force choices that are not part of the concept: data layout, iteration order, evaluation strategy, error handling, library calls, concrete integers, concurrency primitives, and performance hacks.

This can make the example more misleading than clean pseudocode. It teaches the reader an implementation before the idea.

### False Executability

The artifact runs, but the execution is not the relevant evidence.

One run of a concurrent program does not explain the interleavings. One successful query does not establish the relational invariant. One compiled Rust example does not prove the unsafe abstraction is sound. One proof assistant file does not prove the English theorem if the formal statement is weaker than the intended claim.

### Tool-Driven Distortion

A language may be selected because its tool is convenient, not because its semantics fit the domain.

Then the model bends toward what the checker can handle. Bounded search becomes mistaken for proof; executable subset becomes mistaken for full specification; a test harness becomes mistaken for a semantics.

### Reader Exclusion

Actual code can exclude readers who know the concept but not the language. This matters in papers and teaching.

The answer is not to retreat to vague pseudocode. The answer is to keep examples minimal, use conventional syntax when possible, explain the semantic obligations, and choose languages whose notation pays for the learning cost.

### Semantics Drift

Languages, compilers, libraries, proof assistants, and solvers evolve. A checked artifact has versioned meaning.

This is especially important for proof assistants and verifier-oriented languages, where dependencies and trusted bases matter; and for systems languages, where target architecture, optimizer assumptions, and undefined behavior matter.

### The Wrong Level Of Abstraction

Sometimes actual implementation code is too low-level, and LaTeX-style pseudocode is too loose. The right answer is a model, DSL, verifier language, or mathematical definition.

PlusCal is the archetype: it looks code-like, but it is deliberately not an ordinary programming language.

## When Informal Pseudocode Is Still Useful

Informal pseudocode remains useful when:

- the goal is orientation, not verification;
- the algorithmic idea is simple and the audience is broad;
- exact data representation would distract from the invariant;
- the point is a proof sketch rather than an implementation plan;
- the relevant semantics are already standard in the audience's background;
- a real language would impose misleading choices;
- the artifact is an early exploratory sketch whose uncertainty must stay visible.

The problem is not pseudocode as such. The problem is pseudocode presented as if it had resolved questions it merely skipped.

## Historical Claim Boundary

Use the historical examples as notation-pressure lineage, not as interchangeable artifacts. Leibniz's Characteristica Universalis was a vision of formal symbolic expression and calculation, not a working programming language: [universally characteristic language](https://www.britannica.com/topic/universally-characteristic-language). Newton's fluxions were specialized notation for rates of change, not executable semantics: [fluxion](https://www.britannica.com/science/fluxion). Frege's Begriffsschrift was foundational formal notation, not modern standard syntax: [Frege's logic](https://plato.stanford.edu/entries/frege-logic/). Martin-Lof type theory, Girard's linear logic, HoTT, and cubical type theories are stronger examples of formal systems whose notations expanded what could be stated and checked: [intuitionistic type theory](https://plato.stanford.edu/entries/type-theory-intuitionistic/), [linear logic](https://www.sciencedirect.com/science/article/pii/0304397587900454), [HoTT book](https://homotopytypetheory.org/book/), [cubical type theory](https://arxiv.org/abs/1611.02108).

The Godel/von Neumann example should be corrected. Godel's work does show why exact formalization of syntax, proof, primitive recursion, and arithmetization mattered for metamathematics. The SEP account explains Godel numbering as an effective arithmetization of syntax and proof: [Godel's incompleteness theorems](https://plato.stanford.edu/archives/fall2020/entries/goedel-incompleteness/). But von Neumann was not a case of failure to understand; the SEP reception history says he immediately understood the importance of the result and wrote to Godel on 1930-11-20 about the unprovability of consistency: [reception history](https://plato.stanford.edu/archives/sum2018/entries/goedel-incompleteness/). The better claim is: informal mathematical language was inadequate for the exact metatheory, and formal arithmetization made the claim transmissible and checkable.

## Practical Protocol

For translation into a mandated implementation language, use [Code-As-Pseudocode Translation Protocol](code-as-pseudocode-translation-protocol.md).

Compact rule:

- Use the best language to think and specify.
- Use the required language to ship.
- Use validation to connect them.

## Synthesis

The mature thesis is not "replace pseudocode with production code."

It is:

> Replace informal pseudocode with the weakest real formal artifact that preserves the important semantics and can be checked by the right tool.

Sometimes that artifact is executable code. Sometimes it is a model, proof, relational query, type signature, grammar, state machine, hardware description, theorem, Datalog program, or literate program.

The key is claim hygiene. Every artifact should say what it proves, checks, demonstrates, or merely illustrates. Actual code is powerful as pseudocode because it can become an attention-saving formal shadow. It becomes dangerous when readers forget which shadow it is casting.
