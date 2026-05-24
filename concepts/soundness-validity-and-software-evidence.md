---
id: soundness-validity-and-software-evidence
kind: concept
status: draft
source:
  - user-statement: "Reframe software test vs proof as soundness vs validity."
  - user-clarification: "By economy, mean the economy of understanding and verification: mathematical proofs can be cheaper than experiments."
  - user-clarification: "The test versus proof framing is meant to critique the overuse of tests and overreaching claims made from tests."
  - user-clarification: "Tests remain necessary even where proofs are prevalent, because mapping formal concepts into reality requires empirical checks."
  - user-clarification: "More proofs and fewer assumptions improve the economy of attention by reducing repeated experiments and localizing breakage."
  - user-clarification: "Proofs free attention for other things; otherwise doubt keeps producing more tests."
  - source-note: "E. W. Dijkstra, Structured Programming"
  - source-note: "C. A. R. Hoare, How Did Software Get So Reliable Without Proof?"
  - source-access-note: "Detailed Hoare passages were checked through full-text mirrors when the canonical record exposed only metadata."
  - source-note: "V. I. Arnold, On Teaching Mathematics"
  - source-note: "Jackson and Zave, requirements engineering"
  - source-note: "NASA IV&V overview"
  - source-note: "National Academies, Software for Dependable Systems"
  - source-note: "Lean 4 documentation, kernel checking and Lake builds"
  - source-note: "DeMillo, Lipton, and Perlis, Social Processes and Proofs of Theorems and Programs"
  - source-note: "Leslie Lamport, Letter to the Editor on DeMillo, Lipton, and Perlis"
tags: [software-engineering, formal-methods, testing, proof, soundness, validity, verification, validation, requirements]
depends_on: [programming-hyperreality]
related: [attention-management, programming-hyperreality, code-simulacra-and-formal-shadows, causal-code-intelligence]
used_by: [concepts/programming-hyperreality.md, concepts/glossary.md]
supersedes: []
---

# Soundness, Validity, And Software Evidence

This note records a local reframing: the familiar software-engineering opposition between testing and proof can be made clearer by treating it as a distinction between validity and soundness.

The main target is not testing itself. The target is the overuse of tests as a substitute for understanding, and the habit of making claims from tests that the tests do not actually warrant.

The phrase is not being used here as a settled software-engineering term. In the sources checked so far, the nearby standard vocabulary is verification and validation, requirements and specification, assurance cases, model validation, and soundness of formal tools. The exact framing "test vs proof as soundness vs validity" should therefore be treated as a local adaptation unless later literature review finds a canonical source.

## Local Claim

Proof and testing answer different kinds of questions.

Proof is validity-oriented. It asks whether a conclusion follows from a specification, model, semantics, axioms, and inference rules. In software terms, it can show that an implementation satisfies a formal specification, that an invariant is preserved, or that a state is unreachable, relative to the formal frame.

Testing is soundness-oriented in the broader argument-level sense. It asks whether the premises, specification, model, environment assumptions, hardware behavior, user needs, and operational conditions actually fit the world. Tests, experiments, simulations, traces, incidents, and end-to-end checks do not merely compensate for lack of proof. They test whether the formal frame deserves to be trusted.

The compact version:

- Proof checks whether the derivation is valid inside the frame.
- Testing and observation check whether the frame is sound enough for the world.

## Why Tests Remain Necessary

The critique of overusing tests should not become the opposite mistake: treating proof as if it removed the need for tests.

Even in proof-rich domains, there is a boundary where formal concepts are mapped onto reality. At that boundary, tests, experiments, examples, measurements, simulations, and observations remain necessary. A proof can show what follows from axioms, definitions, semantics, and model assumptions. It cannot by itself show that those axioms, definitions, semantics, or assumptions are the right abstraction of the physical system, user need, workload, hardware, organization, or environment.

The mathematical analogy needs precision. In pure mathematics, axioms are not normally tested by physical experiments as if they were scientific hypotheses. They are stipulated and then explored for consistency, consequence, fertility, elegance, and relation to other structures. But when mathematics is used as a model of the world, the chosen axioms and idealizations function as assumptions about reality. Those assumptions must be tested against experience.

Arnold's point is useful here: mathematics has proof at its center, but mathematical modelling can become self-deception when the deductive model is treated as if it automatically coincided with reality. Proof supplies internal force. Experiment checks whether the formal frame deserves the external interpretation being placed on it.

Software has the same shape. A proof can establish that an implementation satisfies a specification under a semantics. Tests are still needed to check whether the specification captures the real requirement, whether the environment satisfies the assumptions, whether the implementation chain is the one proved, whether the hardware and runtime behave as modelled, whether users interact with the system as expected, and whether the system remains observable and recoverable in operation.

So the position is two-sided:

- Tests should not make proof-like claims without proof-like warrant.
- Proofs should not make world-like claims without reality-facing tests.

## Target Of The Critique

The test-versus-proof framing is meant to discipline claims.

A test suite is not a truth machine. It is a finite collection of observations, probes, examples, regressions, or experiments. It can show that some cases were exercised, that some expected failures did not occur, that a previous bug has not reappeared, that a hypothesis survived a particular challenge, or that the system behaved acceptably under chosen conditions. Those are valuable claims. They are not the same as the universal claim that the program is correct.

The overreach happens when a green test suite is treated as if it established a stronger theorem than it actually tested. "The tests pass" may support "these examples work", "this regression is covered", "this interface still satisfies this contract under these fixtures", or "this risk was sampled under these assumptions". It does not by itself support "the system is correct", "the implementation satisfies the specification for all inputs", "the design is sound", "the model matches the world", or "the failure modes are exhausted".

This is where the validity/soundness distinction helps. Proof is the right shape for claims that need universal internal force: all inputs, all reachable states, all executions under a model, all refinements preserving an abstraction. Tests are the right shape for empirical contact, integration, regression, performance, usability, operational behavior, and premise checking. The mistake is to use tests rhetorically as if they had the force of proof, while also refusing to state the narrower empirical claim they actually support.

The practical demand is therefore not "less testing". It is better claim hygiene. Every test should be attached to the risk, hypothesis, invariant, regression, requirement, or environmental assumption it is meant to probe. Every conclusion drawn from tests should say what was sampled, what was not sampled, what assumptions were held fixed, and what kind of claim remains outside the test's reach.

In the language of programming hyperreality, overused tests become signs of rigor that outcompete rigor itself. They produce institutional confidence because they are countable, automatable, and visible. But if the suite does not expose the shape of the claim, the green result becomes a formal shadow detached from the system.

## Fact Check

[Dijkstra](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD268.html) gives the strong proof-side warning: program testing can reveal bugs, but it cannot establish their absence over a huge input and state space. His response was not just "prove more"; it was to design program structures where correctness arguments do not explode with program size.

[Hoare](https://ora.ox.ac.uk/objects/uuid%3Ae2c12b4d-cc50-439a-96d4-f9552a95f54f) gives the balancing correction. His paper asks why software became reliable without direct industrial proof in the strong Dijkstra sense. His answer does not dismiss formal methods. It treats them as a conceptual framework that influenced specification, review, assertions, testing, defensive programming, and disciplined engineering practice.

The [National Academies report on dependable software](https://www.nationalacademies.org/read/11923/chapter/4) supports the distinction. It says testing is indispensable and valuable as feedback on development process, but it also warns that testing and review alone cannot justify extremely high dependability claims. It also makes the model point directly: formal models used for analysis should themselves be tested, and end-to-end tests are needed to catch interactions not predicted by the model.

[Jackson and Zave](https://www.pamelazave.com/4dc.pdf) are especially close to this note's structure. Their requirements-engineering frame separates requirements, domain knowledge, and specification. In their completion criteria, requirements and domain knowledge must be validated, and a proof must show that the specification plus domain knowledge entails the requirements. This is almost the validity/soundness split in engineering form: validate the premises about the world, then prove the entailment.

[NASA IV&V](https://www.nasa.gov/?p=97668) expresses the industry version as verification and validation: verification asks whether the product is being built right; validation asks whether the right product is being built. This is not identical to logic's validity and soundness, but it points in the same direction.

[V. I. Arnold](https://archive-dsweb.siam.org/The-Magazine/All-Issues/vi-arnold-on-teaching-mathematics.html) gives the mathematical analogy. His provocative claim that mathematics is the part of physics where experiments are cheap supports the user's intended meaning of economy: not money alone, but the economy of understanding and verification. His later discussion of modelling also gives the caution: when probable or approximate facts are treated as axioms, deductions still need reality-facing checks before the model is trusted as a description of the world.

## Economy Of Understanding And Verification

The relevant economy is not only runtime cost, staffing cost, or process cost. It is the economy of establishing and preserving understanding.

A proof can be expensive to produce, but it can be cheap in the way that matters: it compresses many possible cases into one inspectable argument. A valid proof can cover infinitely many inputs, executions, or configurations that would be impossible to enumerate experimentally. It can also make the reason for correctness explicit, reusable, and reviewable.

The user's stronger attention-management claim is that more proof and fewer unsupported assumptions reduce the number of logical gaps that must be filled by yet another experiment, test, or expert rereading. A proof lets attention move away from the proved claim unless the assumptions, axioms, definitions, semantics, specification, or trusted implementation boundary changes. This does not make attention disappear. It routes attention to the remaining exposed places: the assumptions, the model-world mapping, the trusted computing base, and the claims not yet covered by proof.

This is the positive value of closure. Without proof or some comparably strong formal check, doubt remains live. The natural response is to keep adding tests, rerunning tests, widening fixtures, and still wondering which untested condition was missed. Proof does not eliminate all doubt, but it gives a principled reason to stop spending active attention on a covered claim and spend it elsewhere.

All else equal, fewer and clearer assumptions make this economy better. They shrink the surface where soundness still depends on empirical validation or informal trust. More derived theorems make fault localization sharper: when something breaks, the likely fault is where the proof no longer covers, where an assumption changed, where the formal statement was too weak, or where the formal model failed to describe reality.

Proof assistants make this attention economy operational. Lean 4 elaborates user-facing terms into a core type theory, and its trusted kernel checks the elaborator's output before new definitions or inductive types are accepted. Lake provides the normal project build path. When a formal definition, theorem, or assumption is changed in a way that invalidates dependent proofs, the affected files no longer elaborate or typecheck. The breakage becomes a to-do list produced by the formal dependency structure.

This is difficult to reproduce with ordinary programming languages plus tests. Tests can show that sampled behavior still satisfies chosen oracles. They usually do not tell us which logical consequences of a changed assumption have become invalid. Even high line coverage is not enough; the relevant issue is behavioral, path, state, environment, and oracle coverage. Building and running enough tests to approximate the dependency sensitivity of a proof assistant can be very costly, and still may miss the changed claim if no test was written for it.

This is the strongest Dijkstra point. The goal is not proof as ceremony. The goal is a program structure where verification effort does not grow explosively with the number of cases, versions, or components.

Testing has its own economy. A small experiment can reveal a false premise, bad specification, wrong environmental assumption, performance cliff, integration failure, or misunderstood user need faster than a formal proof can. But testing becomes wasteful when it samples behavior without a stated claim, risk, or hypothesis, or when it is used to certify a broader conclusion than the sampled evidence can bear.

The economical discipline is therefore:

- Use proof when a universal internal claim is the expensive thing to test.
- Use tests and experiments when the premise, model, environment, or integration is the expensive thing to trust.
- Use both when the formal frame is important but its contact with the world is uncertain.

## Critique Of The Reframing

The reframing is apt, but it needs guardrails.

First, soundness is overloaded. In logic, a sound argument is valid and has true premises. In formal methods, soundness often means a proof system, type system, static analysis, or verifier does not prove false properties about the modeled system. In systems engineering, validation often covers the world-fit side that this note is calling soundness-oriented. Therefore the phrase should be introduced explicitly, not assumed.

Second, proof does not give world-soundness by itself. A proof can be valid and still prove the wrong theorem, about the wrong model, under false domain assumptions, against a misleading specification, using an untrusted compiler, runtime, solver, hardware model, or semantics. This is the standard "verified wrong thing" problem.

Third, testing is not merely weak proof. Tests can be the right method when the claim is empirical: performance, usability, hardware behavior, sensor accuracy, distributional behavior, integration, deployment, and user fit. A proof that ignores these is not superior; it is answering a different question.

Fourth, proof can be uneconomical when the target is low consequence, rapidly changing, poorly specified, or cheaper to guard by isolation, rollback, monitoring, and repair. Hoare's lesson matters here: reliability often emerges from a system of practices, not from one proof artifact.

Fifth, proof itself is not a silver bullet. [DeMillo, Lipton, and Perlis](https://dl.acm.org/doi/10.1145/359104.359106) are useful as a warning against treating program proofs as if they automatically played the same role as accepted mathematical proofs in ordinary engineering organizations. Their strongest concerns are change, specification complexity, and the social process by which proofs become trusted. [Lamport's response](https://www.microsoft.com/en-us/research/publication/letter-to-the-editor/) is the needed balance: those concerns should not be used as an excuse to publish or ship algorithms without correctness arguments. The practical position is neither proof worship nor proof avoidance. Proof liberates attention when it is intelligible, maintained, connected to the right specification, and embedded in an engineering process that can keep its assumptions honest.

The critique does not defeat the reframing. It sharpens it:

- validity names the internal force of the formal argument;
- soundness names the trustworthiness of the whole claim when premises, model, specification, implementation, and world are considered together.

## Practical Rule

Before adding tests blindly, or before claiming too much from existing tests, state what kind of claim is being made.

Use proof, types, model checking, static analysis, or formal derivation for claims such as:

- this invariant always holds;
- this state is unreachable;
- this parser accepts exactly this grammar;
- this protocol cannot deadlock under the model;
- this memory access is always in bounds;
- this refinement preserves the abstract behavior.

Use tests, experiments, replay, simulation, fuzzing, property-based testing, or production observation for claims such as:

- this model matches the device;
- this requirement matches the user's need;
- this integration works end to end;
- this behavior is acceptable under load;
- this generated code preserved intent;
- this assumption survives real data;
- this failure mode remains observable and recoverable.

Every proof should name its premises. Every test should name its hypothesis or risk. Every formal shadow should remain answerable to the system, the environment, and the user need it represents.

Tests become stronger evidence when they are connected to explicit claims. They become weaker evidence when they are accumulated as undifferentiated reassurance.

## Relation To Programming Hyperreality

Testing becomes hyperreal when a green suite stands in for understanding without saying what risk it reduced.

Proof becomes hyperreal when a formal artifact stands in for truth without exposing the premises that make it relevant.

The validity/soundness split is a way to keep both honest. It refuses blind testing and blind proof alike.
