---
id: code-as-pseudocode-translation-protocol
kind: concept
status: draft
source:
  - user-thesis: "AI-assisted translation is a modern deployment pattern built on top of code-as-pseudocode, not the definition of code-as-pseudocode itself."
  - source-note: "Dijkstra, Concern for Correctness as a Guiding Principle for Program Composition"
  - source-note: "Lamport, A High-Level View of TLA+"
  - source-note: "QuickCheck paper"
  - source-note: "Csmith paper"
  - source-note: "CompCert project"
  - source-note: "Translation validation literature"
  - source-note: "TransCoder paper"
tags: [software-engineering, formal-methods, executable-specification, translation-validation, property-based-testing, fuzzing, ai-assisted-programming]
depends_on: [code-as-pseudocode-and-executable-specs, soundness-validity-and-software-evidence]
related: [code-as-pseudocode-domain-language-map, english-as-programming-interface, code-simulacra-and-formal-shadows, causal-code-intelligence, glossary]
used_by: [code-as-pseudocode-and-executable-specs, glossary]
supersedes: []
---

# Code-As-Pseudocode Translation Protocol

This protocol is the practical deployment pattern built on top of `code-as-pseudocode`.

The core concept says: express the hard idea first in the weakest real formal artifact whose semantics fit the domain.

The protocol says: when business constraints force implementation in a less suitable language, keep the best-fit artifact as the semantic anchor, translate into the mandated language, and validate the translation rather than trusting it.

## Boundary

AI-assisted translation is not the definition of `code-as-pseudocode`.

It is a modern way to exploit it:

- the source artifact gives the AI something semantically sharper than prose;
- the target language satisfies deployment, hiring, integration, compliance, or legacy constraints;
- validation checks whether the target preserves the relevant source behavior.

This is not academically novel. It combines older traditions: refinement, executable specification, model-based testing, property-based testing, fuzzing, differential testing, translation validation, verified compilation, and code translation. What is newly practical is the lower cost of generating target implementations, adapters, tests, traces, and review scaffolding with AI.

## Inputs

Before translation, record these inputs.

- Source artifact: the best-fit code, model, proof, query, state machine, reference interpreter, grammar, or hardware-description artifact.
- Source semantics: what the source artifact means, including tool version and trusted base.
- Target language: the business-mandated implementation language.
- Mandate reason: why the target language is required.
- Preserved claims: the properties, observations, invariants, or equivalences that must survive translation.
- Omitted claims: what the source artifact intentionally does not cover.
- Validation budget: which evidence is feasible: proof, model checking, trace validation, property tests, fuzzing, differential tests, examples, review, or runtime monitoring.

## Workflow

1. Choose the source artifact.
   - Pick the language whose native concepts match the problem.
   - Avoid choosing a tool only because it is familiar or easy to run.

2. State the claim.
   - Write what the artifact proves, checks, generates, demonstrates, or merely illustrates.
   - State the abstraction level: model, executable spec, reference implementation, proof object, query, test oracle, or prototype.

3. Define the refinement or equivalence relation.
   - Say what it means for the target implementation to preserve the source.
   - Use observational equivalence, trace inclusion, invariant preservation, input/output equivalence, refinement, or bisimulation only when that relation is actually appropriate.

4. Translate.
   - Use AI or ordinary engineering to generate the target implementation.
   - Keep the source artifact, generated target, prompts, assumptions, and manual edits reviewable.

5. Validate.
   - Use examples for sanity.
   - Use property-based testing when properties can be generated and checked.
   - Use fuzzing when input spaces are large and parser/state-machine edges matter.
   - Use differential testing when source and target can both execute comparable observations.
   - Use model traces when a model checker can generate allowed or failing behaviors.
   - Use translation validation or proof when the claim requires stronger evidence.

6. Reconcile failures.
   - A failure may indicate a bad target implementation, a weak source artifact, an incorrect property, an adapter bug, or a mismatch between model and production reality.
   - Do not silently patch the target until the source, claim, and validation evidence are reconciled.

7. Preserve the evidence.
   - Keep links from source artifact to target implementation and validation suite.
   - Record which tests/proofs/traces support which claims.
   - Pin tool versions when semantics or generated behavior can drift.

## Evidence Ladder

Different checks license different claims.

- Example tests show that named cases work.
- Property-based tests, as in the QuickCheck tradition, generate many cases from executable properties; the original QuickCheck paper describes properties as Haskell functions automatically tested on random input: [QuickCheck paper](https://dl.acm.org/doi/10.1145/351240.351266).
- Fuzzing explores large input spaces and often finds parser, compiler, and boundary bugs; AFL is a practical reference point for coverage-guided fuzzing: [AFL technical details](https://lcamtuf.coredump.cx/afl/technical_details.txt).
- Differential testing compares multiple implementations or source/target observations; Csmith used randomized valid C programs to find hundreds of compiler bugs: [Csmith paper](https://users.cs.utah.edu/~regehr/papers/pldi11-preprint.pdf).
- Model checking explores a model's state space and checks properties in that model; Lamport describes TLA+ as modeling systems above the code level and PlusCal as precise, testable replacement for pseudocode: [High-Level View of TLA+](https://lamport.azurewebsites.net/tla/high-level-view.html).
- Translation validation checks a particular translation result rather than proving the translator correct; Pnueli, Shtrichman, and Siegel describe this pattern for SIGNAL-to-C translation: [Translation validation from SIGNAL to C](https://weizmann.elsevierpure.com/en/publications/translation-validation-from-signal-to-c).
- Verified compilation proves a compiler or compiler path preserves semantics; CompCert describes generated executable behavior as matching the source semantics by machine-checked proof: [CompCert](https://compcert.org/).

The ladder matters because "the translation passed tests" is much weaker than "the target refines the source under a stated semantic relation."

## AI-Assisted Translation

AI can lower the cost of producing target-language candidates, test harnesses, adapters, trace checkers, and property generators. It does not remove the need for a semantic anchor.

Relevant modern signals:

- TransCoder showed neural source-to-source translation among C++, Java, and Python, using tests to check translated functions: [TransCoder paper](https://arxiv.org/abs/2006.03511).
- Recent validated code-translation work explicitly combines LLM translation with cross-language validation, including dependency/API issues: [Validated Code Translation for Projects with External Libraries](https://arxiv.org/abs/2602.18534).

The protocol should therefore treat AI output as a candidate translation. It becomes useful only after the preservation relation and evidence suite make clear what has survived translation.

## Intellectual Lineage

Dijkstra gives the protocol its strictest discipline. In EWD288, he describes a program sketch as an abstract version of the final program, or even as the program for a hypothetical machine whose primitives are later refined: [EWD288](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD288.html). This supports source artifacts as real design objects, not disposable sketches. His testing warning in EWD268 limits what tests can claim: [EWD268](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD268.html).

Lamport gives the strongest direct support for precise pseudocode and models above code. His TLA+ overview says PlusCal is meant to replace pseudocode with precise, testable code, while TLA+ models software above the code level: [High-Level View of TLA+](https://lamport.azurewebsites.net/tla/high-level-view.html).

Alan Kay contributes a different pressure: language and environment shape how people think. In "The Early History of Smalltalk," Kay describes Smalltalk as a new paradigm around protected cells interacting through messages and emphasizes personal computing as a medium, not just implementation machinery: [Early History of Smalltalk](https://worrydream.com/EarlyHistoryOfSmalltalk/). This supports choosing a design medium that fits the idea, while also warning that a language is a thinking environment, not just syntax.

## Failure Modes

- No stated equivalence relation: nobody knows what "faithful translation" means.
- Source artifact too concrete: accidental implementation detail becomes normative.
- Source artifact too abstract: target behavior cannot be validated against it.
- Target-language traps: undefined behavior, integer differences, concurrency models, memory models, library semantics, or exception behavior change the claim.
- AI hallucination: the translator invents APIs, weakens conditions, drops cases, or silently changes representation.
- Adapter error: the validation harness compares the wrong observations.
- Bounded-model overclaiming: a checked finite model is treated as full proof.
- Test overclaiming: random or fuzz tests are treated as absence-of-bugs evidence.
- Spec overclaiming: a theorem or model proves the formal claim, but the formal claim is weaker than the user's actual requirement.

## Minimal Checklist

For each translation project, write:

- Source artifact:
- Target language:
- Mandate reason:
- Source semantics and tool version:
- Preservation relation:
- Required properties:
- Known omissions:
- Translation method:
- Validation methods:
- Evidence produced:
- Residual risks:

## Compact Rule

Use the best language to think and specify.

Use the required language to ship.

Use validation to connect them.
