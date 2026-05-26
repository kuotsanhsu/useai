---
name: code-as-pseudocode-analysis
description: Analyze codebases using the useai code-as-pseudocode and translation-validation frame. Use when Codex should identify semantic anchors, source artifacts, target implementation claims, preservation relations, validation methods, examples, property tests, differential tests, model traces, or residual risks for an implementation.
---

# Code-As-Pseudocode Analysis

Use this skill to analyze implementation work through semantic anchors and validation.

## Core Rule

Express the hard idea first in the weakest real formal artifact whose semantics fit the domain. Treat implementation in a required production language as a target candidate, not as automatic truth.

For algorithmic and library-design work, consider the Stepanov/C++ line first: C++ can be a strong semantic anchor when the important meaning is carried by algorithms, concepts, laws, value semantics, representation boundaries, and complexity requirements.

## Workflow

1. Identify the semantic anchor:
   - spec, model, reference interpreter, grammar, theorem, query, state machine, proof, trace set, existing implementation, or C++ generic algorithm.
2. State what the anchor claims:
   - proves, checks, demonstrates, generates, illustrates, or leaves open.
3. Identify the target implementation path.
4. Define the preservation relation:
   - input/output equivalence, trace inclusion, invariant preservation, refinement, observational equivalence, law preservation, complexity preservation, or another appropriate relation.
5. Validate with the strongest feasible evidence:
   - examples;
   - property tests;
   - fuzzing;
   - differential tests;
   - model traces;
   - translation validation;
   - proof;
   - benchmarks;
   - runtime monitoring.
6. Reconcile failures before patching:
   - source artifact may be weak;
   - target implementation may be wrong;
   - property may be wrong;
   - adapter may compare the wrong observation;
   - production reality may not match the model.
7. Preserve evidence in the target project.

## Output Shape

Use this compact structure:

- Semantic anchor:
- Target implementation:
- Preservation relation:
- Confirmed evidence:
- Validation gaps:
- Known omissions:
- Residual risks:
- Next tests or checks:

## References

Read these repo-relative references when needed:

- `../../concepts/code-as-pseudocode-and-executable-specs.md`
- `../../concepts/code-as-pseudocode-translation-protocol.md`
- `../../concepts/code-as-pseudocode-domain-language-map.md`
- `../../concepts/stepanov-generic-programming-and-code-as-pseudocode.md`
- `../../concepts/soundness-validity-and-software-evidence.md`
