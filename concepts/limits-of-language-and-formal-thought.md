---
id: limits-of-language-and-formal-thought
kind: concept
status: draft
source:
  - user-thesis: "Philosophical quotation and formal languages are ways to borrow expressive instruments when ordinary English is too vague or verbose for the thought."
  - source-note: "Dijkstra The Humble Programmer"
  - source-note: "Dijkstra Natural Language Programming"
  - source-note: "Dijkstra Programming as Mathematical Discipline"
  - source-note: "Dijkstra Interplay Between Mathematics and Programming"
  - source-note: "Dijkstra Foreword on Formal Methods"
  - source-note: "Lamport High-Level View of TLA+"
  - source-note: "Lamport Temporal Logic of Actions"
  - source-note: "Lamport Specifying Systems"
  - source-note: "Iverson Notation as a Tool of Thought"
  - source-note: "Frege Begriffsschrift"
  - source-note: "Wadler Propositions as Types"
  - source-note: "Altenkirch McBride McKinna Why Dependent Types Matter"
  - source-note: "HoTT Book"
  - source-note: "Agda Cubical Documentation"
  - source-note: "Naur Programming as Theory Building"
  - source-note: "Cognitive Dimensions of Notations"
tags: [language, notation, formal-methods, philosophy, programming-languages, specification, thought]
depends_on: [code-as-pseudocode-and-executable-specs]
related: [code-as-pseudocode-translation-protocol, english-as-programming-interface, symbolic-reasoning-and-meaning, soundness-validity-and-software-evidence, glossary]
used_by: [code-as-pseudocode-and-executable-specs]
supersedes: []
---

# Limits Of Language And Formal Thought

This note preserves and develops the user's thesis: mentioning philosophers, mathematicians, and formal systems is not ornamental obscurity. It is often an attempt to borrow a sharper expressive instrument when ordinary English cannot carry the thought without ambiguity, distortion, or excessive length.

The local stable term is "formal language as thought instrument."

The local use of "language" is broad. It includes ordinary natural language, mathematical notation, programming languages, specification languages, proof assistants, query languages, diagrams, and disciplined technical vocabularies. The terms language, notation, calculus, model, and medium are closely related in this note; the current usage keeps their contextual meanings rather than forcing premature boundary definitions.

This note is expected to grow. When a section becomes too long to scan, split that strand into a smaller linked note and preserve backlinks from this overview.

## Core Thesis

Communication is not just transmitting words. It is trying to cause a sufficiently similar thought to arise in another mind.

Natural language is powerful because it carries motivation, analogy, judgment, history, uncertainty, and intent. But it is not uniformly good at all kinds of thought. When the thing to be expressed is recursive, concurrent, contractual, type-indexed, equality-sensitive, or proof-relevant, ordinary English often becomes too ambiguous or too verbose.

The move is not:

- obscure name-dropping;
- replacing English with formalism;
- pretending that a formal language guarantees truth.

The move is:

- use English to orient intention, value, scope, and model-world fit;
- use specialized languages when their semantics make the relevant distinctions explicit;
- use writing, critique, checking, and translation validation to keep any chosen language from becoming a prison.

One compact formulation:

> Choose the language that makes the relevant distinctions cheap, visible, and checkable; then use prose and critique to keep that language honest.

## Why Philosophers And Formalisms Help

Philosophers and formalists often coined words or notations because ordinary language did not already give them a sufficient instrument. Borrowing their vocabulary can be a compression strategy: it imports a history of distinctions that would otherwise take pages to reconstruct.

This is useful only when the borrowed term is doing work. A philosopher's name should not be a prestige marker. It should mark a distinction that the current language otherwise fails to make.

Wittgenstein's famous line from the *Tractatus* is a useful anchor, but it must be used carefully. "The limits of my language mean the limits of my world" is a claim inside an early logical-philosophical project, not a blank check for saying every thought is trapped by vocabulary. The safer local use is weaker and more practical: available languages shape which distinctions are easy to make and which mistakes remain hidden.

Frege gives a more directly relevant notation example. His *Begriffsschrift* was a "concept script", a notation for the logically relevant content of thought. The Internet Encyclopedia of Philosophy summarizes Frege's aim as creating a notational system for arithmetic that was as transparent as possible to the logical structure of thought, representing the part of natural-language content significant for inference: [Frege on language](https://iep.utm.edu/freg-lan/).

Iverson gives the computing version almost directly. In his Turing Award lecture, [Notation as a Tool of Thought](https://www.sigapl.org/Articles/Notation%20as%20a%20Tool%20of%20Thought_a1979-iverson.pdf), he frames notation and language as tools of thought, not merely containers for thought. He also identifies the special advantage of programming languages for this role: they can be executable and unambiguous, while also warning that most programming languages remain inferior to mathematical notation in important respects.

## Dijkstra's Contribution

Dijkstra strongly supports the thesis that language choice changes thought.

In [The Humble Programmer](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html), Dijkstra argues that the tools and notations used to record thought are major factors in what can be thought or expressed at all. His point is not merely that some languages are convenient. It is that languages train habits of thought.

In [On the foolishness of natural language programming](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD667.html), he rejects the idea that programming's difficulty comes mainly from having to use formal symbols. He treats formal symbolism as a privilege because legitimate manipulation can be governed by relatively simple rules, while natural language easily permits nonsense to pass unnoticed.

In [Foreword](https://www.cs.utexas.edu/~EWD/transcriptions/EWD12xx/EWD1238.html), he makes the same point more aggressively: natural language is useful for many human purposes but inadequate for unambiguous treatment of intricate situations such as legislation, mathematics, and programming. Purpose-built formal languages have greater potential, but they demand training and become socially controversial.

In [On the Interplay Between Mathematics and Programming](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD641.html), Dijkstra adds a subtle point: the convenience of proof depends on representation. The program designer has freedom to choose representations that make the relevant predicates simpler. That supports the user's language-choice thesis at the level of proof engineering, not just prose style.

The antithesis inside Dijkstra is just as important. In [Programming as a discipline of mathematical nature](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD361.html), he says a programmer must express himself well both in natural language and in formal systems. He explicitly rejects the claim that English is inherently inadequate, while condemning sloppy English. He also says formalization is, in a sense, after the fact, and that natural language is indispensable when new concepts must be introduced.

The Dijkstra lesson:

- natural language is not automatically clearer;
- formal notation is not a burden when the task requires precision;
- the wrong language can damage the habits needed for the task;
- language design should be judged partly by the intellectual discipline it makes possible.

The limit of Dijkstra for this note is also important. He would not endorse "formal-looking" output merely because it is code. He would ask whether the artifact is under intellectual control, whether the chosen representation keeps the argument manageable, and whether correctness concerns are guiding the construction rather than being patched on later.

## Lamport's Contribution

Lamport supplies the bridge from writing to specification.

In [A High-Level View of TLA+](https://lamport.azurewebsites.net/tla/high-level-view.html), Lamport describes TLA+ as a language for modeling software above the code level and hardware above the circuit level. He says PlusCal is meant to replace pseudocode with precise, testable code that translates to TLA+. He also adds the guardrail: no model completely describes a real system.

In [The Temporal Logic of Actions](https://www.microsoft.com/en-us/research/publication/the-temporal-logic-of-actions/), Lamport makes a sharper point: if you are not writing a program, do not use a programming language. Programming languages carry compiler-oriented complexity; algorithms can often be described more directly in mathematics. This is an antithesis to naive code-as-pseudocode, but not a refutation. It says the best "code" for pseudocode may be a model, algorithm language, mathematical specification, or state-machine formula rather than production code.

In [Specifying Systems](https://lamport.org/tla/book.html), Lamport frames specification-writing as a discipline in its own right. The much repeated "writing exposes sloppy thinking" line should be treated as Lamport's adopted epigraph and teaching point, not as his original coinage; in the book he uses the line from Richard Guindon to introduce the discipline of specification. The downloadable draft also includes concrete limitations of TLC: model checking does not execute arbitrary TLA+ semantics without restriction. That matters because it blocks the overclaim that formal tools remove interpretation.

Lamport's [High-Level Specifications](https://lamport.org/pubs/high-level.pdf) makes the engineering caveat explicit. TLA+ specifications are abstractions of actual systems; checking them can find only errors present in that abstraction. Model checking validates restricted state spaces and is best treated in engineering as a powerful bug-finding and validation tool, not as metaphysical certainty.

The Lamport lesson:

- writing is not packaging after thought;
- writing exposes what has not yet been thought clearly;
- specification is a medium for design, not just documentation;
- the right level of abstraction is above code but still precise enough to check.

## Formal Languages As Thought Instruments

The user's examples mostly hold up when phrased as "languages that make specific distinctions cheap and checkable."

Programming languages and lambda calculi make recursion and computation expressible as objects with operational behavior. Church's [An Unsolvable Problem of Elementary Number Theory](https://www.cis.upenn.edu/~cis5110/Church-UnsolvableProblemElementary-1936.pdf) proposes formal definitions of effective calculability through lambda-definability and recursiveness. McCarthy's [Recursive Functions of Symbolic Expressions](https://www-formal.stanford.edu/jmc/recursive.html) makes recursive symbolic computation executable in Lisp. These are not merely prose descriptions; they are formal media in which computation can be manipulated.

Curry-Howard makes contracts and propositions computational. Wadler's [Propositions as Types](https://cacm.acm.org/research/propositions-as-types/) summarizes the correspondence: propositions correspond to types, proofs to programs, and proof simplification to program evaluation. Dependent type systems extend this by allowing types to express properties indexed by values, which is why Lean, Rocq, Agda, and related systems can carry specifications inside the language of programs and proofs.

For the "contracts" example, "contract" should mean machine-checkable logical obligation, not merely a runtime assertion. Altenkirch, McBride, and McKinna's [Why Dependent Types Matter](https://plv.mpi-sws.org/plerg/papers/why-dependent-types-2up.pdf) states the relevant point directly: dependent types are types expressed in terms of data, letting programs express more of what matters about that data, from ordinary assertions up to complete behavioral specifications.

TLA+ makes concurrent and distributed behavior visible because it talks in states, next-state relations, traces, invariants, and temporal properties. This is exactly the kind of structure ordinary sequential pseudocode hides. Lamport's [TLA+ overview](https://lamport.azurewebsites.net/tla/high-level-view.html) explicitly presents it as modeling above the code level, especially for concurrent and distributed systems.

HoTT and Cubical Agda make identity, equivalence, paths, and higher structure first-class. The [HoTT Book](https://homotopytypetheory.org/book/) presents univalent foundations with Voevodsky's univalence axiom and higher inductive types as central. The [Cubical Agda documentation](https://agda.readthedocs.io/en/latest/language/cubical.html) says Cubical mode adds computational univalence and higher inductive types, giving computational meaning to HoTT and univalent foundations.

The practical rule:

- To express recursion, use a computational language.
- To express contracts as proof obligations, use types and propositions.
- To express concurrency, use state-machine and temporal languages.
- To express higher equivalence and identity, use HoTT or cubical type theory.
- To express intent, limits, and why the formalization matters, still use prose.

## Newton And Verbosity

The Newton example should be softened rather than discarded.

The issue is not simply that Latin is verbose. Newton's *Principia* is hard for modern readers because it is in Latin, uses a geometric-propositional style, and does not present mechanics in the later calculus notation most readers now learn. Britannica notes that Newton set aside the analytic method of fluxions in the *Principia* and used a geometric theory of limits instead: [Newton and Leibniz](https://www.britannica.com/science/mathematics/Newton-and-Leibniz). Project Gutenberg preserves the Latin text as a historical artifact: [Philosophiae Naturalis Principia Mathematica](https://www.gutenberg.org/ebooks/28233?msg=welcome_stranger).

The useful point remains: notational choice affects transmissibility. Later calculus and vector notation made many Newtonian ideas cheaper to state and teach. A more modern notation can preserve a thought while changing the cost of grasping it.

## Strong Antitheses

### Formalism Can Encode The Wrong Thought

A formal language can make a bad model precise. A TLA+ model can verify the wrong abstraction. A dependent type can certify the wrong contract. A program can run while implementing the wrong concept.

Precision is not truth. It is a way to make commitments visible.

### Executability Is Not Specification

Running code shows behavior under some conditions. It does not by itself say which behaviors are normative, accidental, forbidden, or irrelevant.

Executable artifacts become specification-like only when the intended level of abstraction and checking obligations are explicit.

### Every Language Has An Ontology

Each language makes some things primitive and others awkward.

Rust makes ownership and borrowing visible, but not necessarily business intent. SQL makes relations visible, but not causality. TLA+ makes state transitions visible, but not implementation cost. HoTT makes equivalence precise, but can make computation and usability hard for non-experts.

The danger is forgetting what the language hides.

### Natural Language Remains Necessary

Formal systems are strong at consequence. They are weaker at purpose.

English remains necessary for:

- why this problem matters;
- which model omissions are intentional;
- what risks are outside the formal system;
- which audience must understand the result;
- when a proof, test, model, or implementation is enough.

Dijkstra's own antithesis belongs here: new concepts often have to be introduced before they can be formalized. Natural language and examples can carry the exploratory phase in which the right formal vocabulary is still being invented.

### Shared Fluency Is Part Of Expressiveness

A notation is expressive only relative to a community that can read it. APL, HoTT, TLA+, and dependent type theory can be concise and exact, but they can also become opaque when the reader lacks the training.

This is not an argument against specialized language. It is a reason to pair specialized artifacts with prose bridges and examples.

The [Cognitive Dimensions of Notations](https://researchprofiles.herts.ac.uk/en/publications/cognitive-dimensions-of-notations-design-tools-for-cognitive-tech/) literature gives a more systematic version of this warning: notations are cognitive technologies with design tradeoffs, not transparent containers for meaning.

### Program Text Is Not The Whole Theory

Naur's [Programming as Theory Building](https://gwern.net/doc/cs/algorithm/1985-naur.pdf) is a strong antithesis to treating artifacts as if they contain the whole thought. The programmer's theory of how the program maps to the world can transcend program text, documentation, and even specifications. A formal artifact helps preserve and test thought, but it may not transmit the whole theory by itself.

### Formalization Can Freeze Premature Structure

Some ideas need to remain plastic. Formalizing too early can turn exploratory guesses into false requirements. The discipline should be staged:

- prose for orientation;
- examples for intuition;
- formal models for pressure-testing;
- code for executable behavior;
- proofs, model checking, tests, and traces for evidence.

## Synthesis

The synthesis is not "English bad, formal language good."

It is:

1. English starts the thought by carrying motive, context, ambiguity, and direction.
2. Writing sharpens the thought by exposing gaps and forcing sequence.
3. Specialized formal languages discipline the thought by making certain distinctions checkable.
4. Critique prevents the chosen language from hiding the world.
5. Translation validation protects meaning when the artifact moves into another language.

This is why the idea fits code-as-pseudocode. Code-as-pseudocode is one instance of a broader pattern: when a thought exceeds ordinary language, move it into a language whose semantics match the pressure of the idea, then keep the original intention visible so the formal artifact does not become a simulacrum detached from purpose.

## Working Rule

Use a language as a thought instrument when it satisfies three conditions:

- It makes the important distinction cheaper than prose.
- It has stable enough semantics for others to check the claim.
- Its blind spots are named in prose.

Do not use a language as a thought instrument when:

- it is chosen for prestige rather than fit;
- the audience cannot read it and no bridge is provided;
- the model is still too unstable;
- the tool's output will be mistaken for truth rather than evidence.
