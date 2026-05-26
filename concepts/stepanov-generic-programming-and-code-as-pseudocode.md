---
id: stepanov-generic-programming-and-code-as-pseudocode
kind: concept
status: draft
source:
  - user-thesis: "C++ is the best starting place for code-as-pseudocode before considering other languages because its multi-paradigm support is exemplified by the STL."
  - user-request: "Trace the code-as-pseudocode lineage to Alex Stepanov and follow his observations and philosophy."
  - source-note: "Alexander Stepanov, STL and Its Design Principles"
  - source-note: "Alexander Stepanov and Matthew Austern, Fundamentals of Generic Programming"
  - source-note: "Alexander Stepanov and Paul McJones, Elements of Programming"
  - source-note: "Alexander Stepanov interview with Graziano Lo Russo"
  - source-note: "Bjarne Stroustrup, Speaking C++ As A Native"
  - source-note: "Bjarne Stroustrup IEEE Computer interview"
tags: [software-engineering, pseudocode, c-plus-plus, generic-programming, stl, concepts, algorithms, notation]
depends_on: [code-as-pseudocode-and-executable-specs]
related: [code-as-pseudocode-domain-language-map, code-as-pseudocode-translation-protocol, limits-of-language-and-formal-thought, soundness-validity-and-software-evidence, glossary]
used_by: [code-as-pseudocode-and-executable-specs, code-as-pseudocode-domain-language-map, glossary]
supersedes: []
---

# Stepanov, Generic Programming, And Code-As-Pseudocode

This note records a sourced refinement of the user's thesis: C++ is a strong starting place for code-as-pseudocode because it can express machine-near behavior, value semantics, data abstraction, object-oriented variation, and generic algorithms in one language. The STL is the central exhibit, not because every C++ program is good pseudocode, but because Stepanov's generic programming uses actual code to carry mathematical structure, requirements, algorithms, and performance obligations together.

The claim should stay qualified. C++ is not always the best pseudocode language. TLA+ is usually a better first artifact for distributed protocols; SQL or relational algebra is better for relational claims; Lean or Rocq is better for proof obligations. The Stepanov line matters when the hard idea is an efficient algorithm or data-structure family whose meaning depends on requirements, laws, representations, complexity, and interoperability.

## Core Claim

Stepanov supplies the missing C++ lineage for code-as-pseudocode:

- Dijkstra gives the derivational discipline: program text should remain a reasoning object.
- Lamport gives the precise model/specification lineage: ordinary pseudocode is too vague for concurrency and distributed algorithms.
- Stepanov gives the generic-programming lineage: start with algorithms, find the weakest useful requirements, organize those requirements as concepts, and implement them efficiently in a real language.

This makes C++ useful as disciplined pseudocode when the artifact is not just "some code that runs." It is useful when the code exposes the theory of the algorithm: the required operations, their laws, their complexity, the admissible models, and the representation boundary.

## Source Findings

Bjarne Stroustrup describes C++ as a multi-paradigm language supporting C-style programming, data abstraction, object-oriented programming, and generic programming, with generic programming using type parameterization over both data types and algorithms: [Speaking C++ As A Native](https://www.stroustrup.com/Speaking_2000.pdf).

Stroustrup also describes the STL as the most novel part of the C++ standard library's container-and-algorithm framework and says it was primarily Alex Stepanov's work: [IEEE Computer interview](https://www.stroustrup.com/ieee_interview.html). In the same interview, he emphasizes that the STL criteria included efficiency, type safety, generality, and extensibility.

Stepanov's own interview with Graziano Lo Russo is the most direct philosophical source. He says he was not merely trying to program in C++; he was looking for the right way to deal with software, and C++ was the best language he had found for saying what he wanted to say: [STLport interview](https://www.stepanovpapers.com/LoRusso_Interview.htm). He defines generic programming as beginning with an algorithm and finding the most general requirements that let it perform efficiently. The mathematical analogy is explicit: many theorems depend on the same axioms, and many models can satisfy those axioms.

That interview also gives the anti-ceremonial lesson. Stepanov says programming should start with interesting algorithms, not with classes. Axioms are not the starting point; they are what you derive after studying related proofs and algorithms. In repo terms: do not begin with a fashionable abstraction. Begin with the operation that must be understood.

The Stepanov and Austern paper [Fundamentals of Generic Programming](https://www.stepanovpapers.com/DeSt98.pdf) gives the technical bridge. It defines a concept as axioms satisfied by a data type and operations, argues that reusable components should assume a minimal collection of concepts, and presents STL as the first extensive instance of that paradigm in wide use. It also frames the progression from generalized machine architecture, through C as a generalized machine language, to C++ and then generic programming.

Stepanov's [STL and Its Design Principles](https://www.stepanovpapers.com/stl.pdf) makes the working method compact: find algorithms and data structures, implement them, create a taxonomy, specify correct interfaces, validate, measure, and document. It also states the original intuition as associating algorithms with mathematical theories.

In [Elements of Programming](https://elementsofprogramming.com/eop.pdf), Stepanov and McJones make the code-as-pseudocode connection explicit without using that phrase. They apply the deductive method to programming by presenting mathematical theories, algorithms, lemmas, and code together. They chose C++ because it combines abstraction facilities with faithful representation of the underlying machine, and they use a small subset of the language with structured comments for requirements.

## Why C++ Is A Strong First Lab

C++ can serve as a first laboratory for code-as-pseudocode because it keeps several semantic layers close together:

- machine representation and cost are visible enough to keep performance honest;
- user-defined types can be made to behave like built-in types;
- operator overloading can extend not only syntax but intended semantics;
- templates allow algorithms to be written against requirements rather than concrete types;
- value semantics, iterators, ranges, and algorithms can separate representation from operation;
- the standard library supplies shared examples of this style.

The important point is not "C++ is best because it is powerful." The better point is: C++ can express the whole chain from low-level representation to high-level reusable algorithm without forcing a different notation at each layer.

This is why C++ is a good starting place before considering other languages. It exposes the tradeoffs that many other languages hide or choose on the programmer's behalf: abstraction versus representation, genericity versus runtime dispatch, value semantics versus identity, efficiency versus interface generality, and algorithm requirements versus concrete data structures.

## Stepanov Method For Code-As-Pseudocode

Use this method when developing or analyzing code-as-pseudocode in the Stepanov line:

1. Start with an interesting algorithm, not a class hierarchy.
2. Identify the real operations the algorithm uses.
3. Derive the weakest requirements that make the algorithm correct and efficient.
4. Name those requirements as concepts.
5. State semantic laws and complexity requirements, not only function signatures.
6. Find multiple concrete models of the same concepts.
7. Separate algorithms from data structures through the smallest useful interface, such as iterators or ranges.
8. Implement in a small, readable C++ subset when C++ is the source artifact.
9. Validate, measure, and document which claims the code licenses.
10. Translate to other languages only after the semantic anchor is explicit.

The practical form for this repo:

- semantic anchor: C++ generic algorithm or reference implementation;
- concept requirements: operations, laws, associated types, complexity, iterator/range category, value semantics;
- target implementation: production code in C++, Python, Rust, TypeScript, SQL, or another mandated language;
- preservation relation: same observable behavior under stated requirements, same law set, same complexity class where relevant;
- validation: examples, property tests, differential tests against the C++ anchor, benchmarks when complexity is part of the claim.

## How This Refines Code-As-Pseudocode

Lamport warns against treating ordinary programming languages as algorithm languages when the right artifact is an abstract model. Stepanov shows the complementary case: for algorithmic libraries, actual programming-language constructs can express the abstract theory better than loose pseudocode if the requirements and laws are made explicit.

So the refined rule is:

> Use C++ as pseudocode when the concept is an efficient family of algorithms and data structures whose meaning depends on requirements, laws, value semantics, representation boundaries, and complexity.

This does not override the broader rule from [Code As Pseudocode And Executable Specs](code-as-pseudocode-and-executable-specs.md): choose the weakest real formal artifact whose semantics match the domain. It adds a concrete preference ordering for algorithmic and library-design work: try the Stepanov/C++ formulation first, then translate or replace it only when another language exposes the relevant structure better.

## Cautions

C++ can become bad pseudocode when it exposes the wrong details:

- undefined, unspecified, or implementation-defined behavior can make the artifact less portable than it looks;
- template machinery can obscure the algorithmic idea;
- clever overload sets can hide semantic obligations;
- performance hacks can become mistaken for requirements;
- object-oriented ceremony can bury the algorithm under class structure;
- too much of the language can exclude readers.

The Stepanov answer is not maximal C++. It is disciplined C++: a small subset, explicit requirements, precise concepts, value semantics where possible, measured performance, and code that remains close to the mathematical structure.

## Practical Reading Path

Use this order when studying Stepanov for this repo:

1. [STLport interview with Stepanov](https://www.stepanovpapers.com/LoRusso_Interview.htm) for the philosophy.
2. [STL and Its Design Principles](https://www.stepanovpapers.com/stl.pdf) for the design workflow.
3. [Fundamentals of Generic Programming](https://www.stepanovpapers.com/DeSt98.pdf) for concepts, requirements, and STL as the paradigm instance.
4. [Elements of Programming](https://elementsofprogramming.com/eop.pdf) for the mature deductive method.
5. Stroustrup's [Speaking C++ As A Native](https://www.stroustrup.com/Speaking_2000.pdf) and [IEEE Computer interview](https://www.stroustrup.com/ieee_interview.html) for the multi-paradigm and standard-library context.

## Open Questions

- How much of Stepanov's style should be made executable in a local C++ reference-template directory for future examples?
- Should the code-as-pseudocode plugin skill ask explicitly whether C++ is the right first semantic anchor for algorithmic work?
- Which target languages preserve Stepanov-style concepts naturally, and which need additional tests or documentation to avoid semantic loss?
