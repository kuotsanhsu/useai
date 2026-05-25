---
id: lacanian-approach-to-programming-language
kind: concept
status: draft
source:
  - user-request: "Start a new thread out of curiosity on Lacanian approach to programming language."
  - source-note: "Jacques Lacan, Stanford Encyclopedia of Philosophy"
  - source-note: "Isabel Millar, The Psychoanalysis of Artificial Intelligence"
  - source-note: "Graham Joncas, Computational Psychoanalysis"
  - source-note: "Reddit r/lacan, Lacans Real and Computational Trinitarianism"
  - source-note: "W Watson, The Perverts Guide to Computer Programming Languages"
  - local-bridge: "Connect prior Lacan, symbolic reasoning, programming hyperreality, and English-as-interface notes."
tags: [programming-languages, psychoanalysis, lacan, signifier, semantics, ai, software-engineering, jouissance, matte-blanco]
depends_on: [symbolic-reasoning-and-meaning]
related: [code-simulacra-and-formal-shadows, english-as-programming-interface, programming-hyperreality, soundness-validity-and-software-evidence, glossary]
used_by: []
supersedes: []
---

# Lacanian Approach To Programming Language

Status: exploratory local adaptation. This is not a claim that programming-language theory has a settled Lacanian branch. It is a thread for testing whether Lacan's concepts help name recurring failures in code, AI-assisted programming, and software meaning.

The starting point is Lacan's claim that the unconscious is structured like a language. The [Stanford Encyclopedia of Philosophy entry on Lacan](https://plato.stanford.edu/entries/lacan/) is careful that Lacan's relation to language changes across his work, so this note should treat "language" as a pressure point rather than a slogan. For the prior psychoanalytic bridge in this repository, see [Symbolic Reasoning And Meaning](symbolic-reasoning-and-meaning.md).

## Containment Rule

Keep Lacanian vocabulary inside this note and explicitly Lacanian follow-up notes. Nearby non-Lacanian notes can link here when useful, but they should keep their own vocabulary: formal shadow, simulacra of the code, programming hyperreality, English as programming interface, soundness, validity, evidence, and attention management.

The purpose of this note is to add a subject-side diagnostic layer, not to rename the whole repository in Lacanian terms.

The Lacanian form of the project motto:

- Use the Symbolic to approach reality gradually, because direct encounter with the Real is disruptive. But keep the Symbolic answerable to the Real, or it becomes simulacrum.

## Source Access Notes

- The Millar reference is **Isabel Millar**, not "Sabel Millar." The [Springer book page](https://link.springer.com/book/10.1007/978-3-030-67981-1) is only preview/subscription content, but it gives reliable metadata, abstract, table of contents, and reviews. The [Kingston thesis record](https://researchinnovation.kingston.ac.uk/en/publications/the-psychoanalysis-of-artificial-intelligence-2/) gives a longer abstract and a submitted manuscript link, but direct PDF download failed locally. A [Vestigia review](https://vestigiajournal.com/wp-content/uploads/2021/12/Jeremy-Soh-Book-Review-Vestigia.v31.pdf) was accessible as a secondary source.
- Graham Joncas's [Computational Psychoanalysis](https://gjoncas.github.io/posts/2021-02-16-computational-psychoanalysis.html) was accessible directly.
- The [Reddit thread](https://www.reddit.com/r/lacan/comments/shr325/lacans_real_computational_trinitarianism/) was accessible as user-generated discussion. The author is deleted, some comments are deleted, and embedded images were not reviewed, so use it only as hypothesis material.
- The provided PDF, [The Pervert's Guide to Computer Programming Languages](https://s3-us-west-2.amazonaws.com/vulk-blog/ThePervertsGuidetoComputerProgramming-ThePaper.pdf), failed through the web fetcher but was downloaded with `curl` and text-extracted locally. The extracted text identifies copyright as W. Watson, Vulk LLC, 2017.

## Reference Summaries

Millar shifts the AI question from intelligence to enjoyment. The Springer description says the book asks what psychoanalysis can tell us about AI for "speaking, sexed subjects" and moves from "Does it think?" toward "Can it enjoy?" The Kingston abstract sharpens this into a move from object a to the **lathouse**, a technoscientific object "not quite being and not quite the other," with the Sexbot as the figure at the boundary of psychoanalysis and AI.

For programming-language work, Millar is useful by extrapolation. AI coding assistants are not just tools that answer whether they understand code. They are synthetic objects inside the developer's symbolic environment: they autocomplete, explain, refactor, reassure, and frustrate. The useful question becomes: what patterns of enjoyment, compulsion, dependency, fantasy, and anxiety form around the tool?

Joncas is mostly Matte Blanco rather than Lacan, but the bridge is strong for programming. The essay summarizes Matte Blanco's bi-logic: conscious thought preserves asymmetry, order, negation, and individuation; unconscious thought increasingly treats relations symmetrically. Joncas then connects this to ultrametric spaces, hierarchical clustering, and possible machine-learning approaches to dream reports and text.

For programming-language work, Joncas gives the cleanest formal contrast: programming semantics depend on asymmetry. Input/output, caller/callee, subtype/supertype, cause/effect, before/after, and ownership all matter. AI agents often fail by symmetric association: treating related APIs as interchangeable, flattening temporal order, confusing part and whole, or replacing operational semantics with similarity.

The Reddit thread proposes a loose bridge among Lacan's Real, Symbolic, and Imaginary and "computational trinitarianism." Its strongest reusable move is not its exact mapping, but the question it raises: how do private conviction, formal proof, computational repetition, and material resistance relate? One commenter gives the most useful warning: Lacan's RSI is often not enough by itself; symptom, sinthome, object a, or point de capiton may function as a necessary fourth term.

For programming-language work, the thread is useful as a prompt: Imaginary can name the programmer's mental model and diagrams; Symbolic can name syntax, types, APIs, compilers, tests, and proof systems; Real can name runtime failure, performance limits, security exposure, and everything the current formalism failed to master. But this should remain an interpretive lens, not a formal isomorphism.

Watson's paper directly applies Lacan and Zizek to programming languages. It argues that language choice is not only rational utility, power, or aesthetics, but also a choice shaped by fear, desire, ideology, and enjoyment. Its Part III maps Lacanian structures onto programming-language styles: psychotic or sociopathic languages as loose/instrumental, perverse languages as enjoyment in being the vessel of rules, obsessive languages as rule-making that defers completion, and hysterical languages as endless refinement of the code base or domain language.

For programming-language work, Watson is the most directly relevant but also the riskiest. The paper has useful provocations about language communities, type systems, boilerplate, DSLs, minimalism, and aesthetic refinement. But its clinical labels should not be treated as diagnoses of people or languages. The safer translation is: programming languages can stage different relations to rules, authority, completion, abstraction, and enjoyment.

## Comparison

The sources divide into four roles:

- Millar supplies the AI object: artificial intelligence as a lathouse-like technoscientific object organized around enjoyment, extimacy, sexuation, and fantasy.
- Joncas supplies the formal model: unconscious logic as symmetry, hierarchy, condensation, and ultrametric clustering.
- The Reddit thread supplies the register map: Imaginary, Symbolic, Real, and possibly a fourth stabilizing term as a way to discuss model, formalism, execution, and symptom.
- Watson supplies the PL application: language choice and language-community identity as libidinal and ideological, not just technical.

They agree that computation should not be treated as neutral symbol manipulation. Each source asks what a formal or technical system does to a subject:

- Millar asks what enjoyment AI organizes.
- Joncas asks how unconscious association might be formalized.
- Reddit asks how proof, computation, and material reality mediate conviction.
- Watson asks what programming-language choices reveal about desire, anxiety, and rule relations.

They disagree in method and reliability:

- Millar is theory-heavy and source-backed, but not directly about programming languages.
- Joncas is mathematically suggestive, but mostly a blog synthesis and not Lacan-centered.
- Reddit is exploratory discussion and should not support settled claims.
- Watson is directly on programming languages, but its psychoanalytic classifications are broad and sometimes rhetorically overextended.

The strongest combined thesis is modest:

- A Lacanian approach to programming language should analyze how names, syntax, types, tests, tools, prompts, and communities organize desire, anxiety, authority, and reality contact.

The weakest combined thesis would be too strong:

- Do not claim that programming languages literally have clinical structures or that Lacanian registers map cleanly onto mathematics, computation, and physics.

## Working Synthesis

The Lacanian approach should be the subject-side companion to the artifact-side notes already in this repository.

Those existing notes ask what makes an artifact trustworthy:

- a formal shadow is useful when it preserves enough structure to reason with;
- a code simulacrum is dangerous when representation displaces contact with the code;
- programming hyperreality appears when signs of rigor outcompete correctness, cost, users, production behavior, and understanding;
- English as programming interface treats natural language as executable intent that must compile into checkable artifacts before consequential action.

This note asks a different question:

- Why do programmers, teams, and AI users become attached to particular signs, tools, languages, explanations, and rituals even when those artifacts stop improving contact with the system?

The compact synthesis:

- A Lacanian approach to programming language is not a replacement for formal semantics. It is a diagnostic layer over programming practice. Formal semantics asks what code means inside a symbolic system. The Lacanian question asks how subjects become organized by that symbolic system: names, types, tests, prompts, dashboards, tools, failures, and the fantasy of finally understanding the machine.

The practical map:

- Imaginary: the image of the system, such as diagrams, clean APIs, elegant abstractions, and the mental model of what the code supposedly is.
- Symbolic: the rule system, such as syntax, type systems, specs, tests, CI, review norms, ownership labels, prompts, issue templates, and formal shadows.
- Real: what resists the model, such as runtime failures, race conditions, latency, production data, security exposure, hardware limits, undecidability, and maintenance cost.
- Symptom or sinthome: what keeps the system functioning despite contradiction, such as a recurring workaround, ritual, naming convention, flaky-test habit, manual deployment step, favored tool, or AI workflow that patches over a structural inconsistency.

AI coding assistants fit this synthesis as a lathouse-like twelfth camel: a synthetic object inserted into the programming process to make thought and action move. It is useful when it can be returned, meaning the generated plan becomes a diff, test, invariant, trace, or explanation that survives independent checking. It becomes hyperreal when the assistant's answer becomes the authority.

Matte Blanco adds the clean operational failure mode:

- Formal programming depends on asymmetry; AI often fails through symmetry.

A programming language distinguishes caller and callee, input and output, before and after, subtype and supertype, owner and dependency, cause and effect. AI-assisted coding often collapses those into "similar things." The review question is:

- Which directional relation did the model flatten into mere resemblance?

Watson adds the programming-language culture axis, but it should be kept non-clinical:

- Some languages promise freedom from rules.
- Some promise rescue by rules.
- Some invite endless refinement.
- Some invite hard-road identity.
- Some make a central abstraction into a privileged object: object, function, type, process, macro, pipeline, actor, or prompt.

The resulting rule:

- Programming languages are symbolic systems, but programmers do not relate to them only as rational users. They attach to them through images of mastery, rule, elegance, rebellion, discipline, productivity, and rescue. AI intensifies this because it speaks back from inside the symbolic order. The engineering discipline is to keep these signifiers answerable to execution, users, tests, traces, costs, failures, and repair.

## Starting Intuition

A Lacanian approach to programming language would not begin by asking only "what does this code denote?" It would also ask how the programmer, reviewer, user, and AI agent are caught in systems of signifiers.

Programming is full of signifiers that organize attention before their meaning is fully settled:

- names: `Context`, `Manager`, `Agent`, `Policy`, `SourceOfTruth`;
- artifacts: specs, diagrams, tests, dashboards, traces, prompts;
- institutional terms: clean, scalable, production-ready, platform, ownership;
- formal signals: types, lint rules, CI checks, coverage, proofs;
- failure signs: stack traces, flaky tests, incident labels, bug categories.

The question is not whether these signs are false. The question is when they anchor meaning and when they start circulating as substitutes for understanding.

## Symbolic Order

The symbolic order of programming is the system of rules and positions that makes an utterance count as code, a proof, a test, a bug, an owner, or an acceptable change.

Examples:

- a language specification defines what programs can mean;
- a compiler or typechecker says what may be admitted;
- a package manager and build system define dependency legitimacy;
- CI decides what can merge;
- review norms decide what counts as understandable;
- architecture documents assign roles such as client, server, owner, caller, maintainer, source of truth.

This is useful because it prevents programming from being private expression. But it can also hide responsibility. "The build passed" may become a sign that displaces the harder question: what did the build actually check?

## Imaginary Capture

The imaginary register is a useful warning about identification with a coherent image.

In programming, the image may be:

- the elegant architecture diagram;
- the clean API;
- the agentic workflow;
- the perfect abstraction;
- the green dashboard;
- the narrative that "the system is now understood."

This connects directly to [Programming Hyperreality](programming-hyperreality.md) and [Code Simulacra And Formal Shadows](code-simulacra-and-formal-shadows.md). The danger is not representation itself. The danger is over-identifying with the representation until it becomes more compelling than the system it should clarify.

## The Real Of Execution

The Real, in this local adaptation, is not "machine code" or "hardware" alone. It is what resists the current symbolic and imaginary frame.

Software examples include:

- race conditions that were absent from the design story;
- latency that invalidates an abstraction;
- undefined behavior;
- production data that breaks a clean type model;
- security attacks that exploit an unstated assumption;
- user behavior that refuses the intended workflow;
- cost, scheduling, and operational constraints that the model ignored.

The Real is where the signifying system fails to absorb the consequence. A good engineering practice does not eliminate this pressure. It builds ways to let that pressure return as evidence: logs, traces, tests, incidents, benchmarks, proofs, specifications, and rollback paths.

## AI And English As Interface

AI-assisted programming intensifies the Lacanian problem because English prompts can set off long chains of signifiers:

- prompt;
- plan;
- generated code;
- generated tests;
- generated summary;
- green check;
- confident explanation.

For the related AI-era thread, see [English As Programming Interface](english-as-programming-interface.md).

The risk is that the signifying chain becomes self-validating. A prompt can generate code, tests, and an explanation that all cohere with each other while still missing the Real of execution, users, security, or maintainability.

The discipline is to force the chain to pass through reality contact:

- What would falsify this interpretation?
- What does the type system actually guarantee?
- What did the test suite not observe?
- What production behavior would contradict the story?
- What assumption did the AI import without ownership?

Millar adds another question:

- What enjoyment does this tool organize?

That question should not be flattened into "does the user like it?" It asks about repetition, dependence, frustration, reassurance, control, fantasy, and the satisfaction of having the tool speak back.

Joncas adds a second operational question:

- Where did the system replace asymmetrical semantics with symmetrical association?

This is a useful debugging question for AI-assisted programming. A generated patch may be locally plausible because it grouped two APIs, two errors, or two files into the same class, while missing the directional relation that made one caller, owner, dependency, cause, or temporal step different from the other.

Watson adds a third community question:

- What relation to rules does this language or tool invite?

Some tools promise freedom from rules, some promise rescue by rules, some invite endless refinement, and some invite hard-road identity. These are not clinical diagnoses. They are patterns of technical enjoyment that can affect language adoption, review style, and tool loyalty.

## Practical Diagnostic Use

This lens is useful only if it changes diagnosis.

Ask:

- Which signifier is organizing the conversation too strongly?
- Does the name still match the behavior?
- Is the formal artifact a checkable shadow or a simulacrum?
- What is being treated as proof because it looks like proof?
- Where does the system push back against the story?
- What cannot be represented in the current spec, type, test, prompt, or diagram?
- Which asymmetrical relation is being collapsed into a loose equivalence?
- What enjoyment keeps this tool, language, or abstraction attractive even when it is causing pain?
- What symptom recurs despite the official explanation?

Strong candidate signifiers to watch:

- `clean`;
- `scalable`;
- `agent`;
- `platform`;
- `source of truth`;
- `done`;
- `production-ready`;
- `self-healing`;
- `correct`;
- `understood`.

Working register map:

- Imaginary: diagrams, metaphors, mental models, API aesthetics, the image of clean architecture.
- Symbolic: grammar, type systems, compilers, contracts, tests, proof obligations, review norms.
- Real: runtime failure, latency, race conditions, data drift, security exposure, undecidability, operational cost.
- Symptom or sinthome: the recurring workaround, bug class, ritual, naming convention, or tool attachment that holds the system together when the official architecture does not.

## Research Directions

- Is there existing work in critical code studies, software studies, media theory, or psychoanalysis that connects these sources more rigorously?
- Can this lens produce better engineering questions, or does it mostly rename ordinary ambiguity?
- How should this relate to formal semantics, where meaning is intentionally disciplined rather than psychoanalytic?
- Does the Lacanian lens help distinguish good naming from misleading naming?
- In AI programming, does the prompt become an address to the Other, or is that too metaphorical to be useful?
- Should "lathouse" become a local term for AI coding assistants, or would that import too much Millar-specific sexuation theory into ordinary tooling?
- Can Matte Blanco's symmetry/asymmetry distinction become a practical AI-code-review checklist?
- Can Watson's language-structure mapping be rewritten without clinical labeling, using only relations to rules, completion, authority, abstraction, and enjoyment?

For now, treat this as a curiosity thread with one useful constraint: no Lacanian vocabulary should be kept unless it improves a concrete programming diagnosis.
