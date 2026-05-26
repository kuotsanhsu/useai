---
id: glossary
kind: index
status: active
source:
  - user-request: "Maintain a glossary that also make explicit local coinage."
tags: [glossary, terminology, local-coinage, retrieval]
depends_on: []
related: [programming-hyperreality, attention-management, retrieval-and-action-system]
used_by: [concepts/README.md, docs/documentation-style.md]
supersedes: []
---

# Glossary

Use this glossary to keep important terms stable, retrievable, and honest about provenance.

Status labels:

- External claim: a claim or framing taken from an outside source and locally qualified here.
- External phrase: a phrase taken from an outside source and locally qualified here.
- Local coinage: a phrase coined in this repo or conversation.
- Local adaptation: an existing term, metaphor, or phrase adapted for this repo's use.
- Stable local adaptation: a local adaptation that should be treated as stable terminology for future retrieval and writing.
- Standard term or phrase: a term or phrase already recognized in a relevant field.
- Repo workflow term: a local operating term for this repository.

## Terms

- Attention management
  - Status: local adaptation.
  - Meaning: the design of context, reminders, routing, boundaries, and review loops so limited human and AI attention goes to the work that matters.
  - Canonical note: `concepts/attention-management.md`.

- Artifact drift
  - Status: local coinage.
  - Meaning: the migration of attention from the work into artifacts that represent the work, such as dashboards, tests, metrics, summaries, plans, diagrams, and process rituals.
  - Canonical note: `concepts/attention-management.md`.

- Ambiguation hell
  - Status: local coinage.
  - Meaning: the failure mode where natural-language or AI-assisted programming seems to remove coding drudgery but relocates the work into ambiguity, assumption repair, prompt negotiation, review burden, and ownership of plausible but underspecified output.
  - Canonical note: `concepts/english-as-programming-interface.md`.

- Ceremonial accidental complexity
  - Status: local adaptation.
  - Meaning: avoidable complexity introduced by applying patterns, architecture, infrastructure, or process as signs of sophistication rather than as justified responses to the problem. Examples include excessive OOP, premature microservices, and infrastructure layers whose operational burden exceeds the complexity they remove.
  - Canonical note: `concepts/accidental-complexity-and-ceremony.md`.

- Code as pseudocode
  - Status: local adaptation.
  - Meaning: the use of actual programming, modeling, query, hardware-description, or proof languages as disciplined pseudocode when their semantics match the domain and their tools can execute, check, model-check, compile, or prove the artifact.
  - Canonical note: `concepts/code-as-pseudocode-and-executable-specs.md`.

- Code-as-pseudocode translation protocol
  - Status: local adaptation.
  - Meaning: the workflow of using a best-fit formal artifact as the semantic anchor, translating into a business-mandated target language, and validating preservation with properties, traces, fuzzing, differential tests, model checking, or translation validation.
  - Canonical note: `concepts/code-as-pseudocode-translation-protocol.md`.

- Dijkstra standard
  - Status: local adaptation.
  - Meaning: local shorthand for the Dijkstra-inspired demand that code remain under intellectual control and become a deposit of understanding, not a substitute for understanding.
  - Canonical note: `concepts/programming-hyperreality.md`.

- Death of clever code
  - Status: local adaptation.
  - Meaning: local shorthand for Hoare's resource-abundance argument: faster computers, cheaper storage, and better optimization make many clever efficiency tricks less necessary, especially when they hinder correctness reasoning, review, testing, maintenance, and repair.
  - Canonical note: `concepts/programming-hyperreality.md`.

- Deliberate over-engineering
  - Status: external phrase, locally developed.
  - Meaning: Hoare's phrase for extra engineering margin such as defensive checks, redundancy, safe reinitialization, timeouts, warm restart, and other structure that can improve reliability when proof is incomplete, while also adding maintenance and testing burden.
  - Canonical note: `concepts/error-handling-and-fault-tolerance.md`.

- Desert of the real in programming
  - Status: local adaptation.
  - Meaning: local adaptation of Baudrillard's phrase for the stronger stance that writing code itself should be denounced as unnecessary contact with reality. The compiler and assembly history is used as the cautionary precedent: routine low-level writing can become non-default without becoming obsolete.
  - Canonical note: `concepts/desert-of-the-real-in-programming.md`.

- Economy of attention
  - Status: standard phrase, locally developed.
  - Meaning: attention is scarce, so a useful knowledge-work system must choose what deserves attention, what stays cold but retrievable, and what can fade.
  - Canonical note: `concepts/attention-management.md`.

- Economy of understanding and verification
  - Status: local adaptation.
  - Meaning: the economy gained when a proof, model, test, or experiment reduces the cost of understanding and checking a claim. In this repo, proof is economical when it compresses many cases into one reusable argument and lets attention move away from proved claims until assumptions change; testing is economical when it cheaply challenges the premises, model, environment, or integration.
  - Canonical note: `concepts/soundness-validity-and-software-evidence.md`.

- English as programming language
  - Status: external claim, locally qualified.
  - Meaning: the claim that English now functions as a programming interface for AI systems. In this repo, the phrase does not mean English replaces formal semantics. It means English can express executable intent and therefore needs formal shadows, guardrails, rollback, tests, policies, and review before consequential action.
  - Canonical note: `concepts/english-as-programming-interface.md`.

- Formal shadow
  - Status: local adaptation.
  - Meaning: a formal representation that is not the system itself but preserves enough structure to reason with. It is the disciplined, checkable subset of code simulacra.
  - Canonical note: `concepts/code-simulacra-and-formal-shadows.md`.
  - Provenance note: the broader phrase appears in other intellectual contexts, but its software-engineering use here is local and narrower than the user's original "simulacra of the code" framing.

- Formal shadow of the code
  - Status: local coinage.
  - Meaning: a code-facing formal shadow, such as a call graph, causal graph, Datalog fact base, type model, spec, test, or trace. This was the later assistant framing, not the user's original phrase.
  - Canonical note: `concepts/code-simulacra-and-formal-shadows.md`.

- Formal language as thought instrument
  - Status: stable local adaptation.
  - Meaning: the use of natural language, mathematical notation, programming languages, specification languages, proof assistants, or other symbolic media as tools that shape, revise, constrain, and communicate thought rather than merely record finished thought.
  - Canonical note: `concepts/limits-of-language-and-formal-thought.md`.

- Generic programming
  - Status: standard term, locally developed.
  - Meaning: the Stepanov/Musser programming method of starting with algorithms, deriving the weakest useful requirements, organizing those requirements as concepts, and implementing efficient reusable components against those concepts. In this repo, it is the C++/STL lineage of code-as-pseudocode.
  - Canonical note: `concepts/stepanov-generic-programming-and-code-as-pseudocode.md`.

- Claim hygiene
  - Status: local adaptation.
  - Meaning: the practice of stating what a formal artifact, test, proof, model, benchmark, or source actually licenses, and not letting a narrow result imply a broader claim than the evidence supports.
  - Canonical note: `concepts/soundness-validity-and-software-evidence.md`.

- Hoare balance
  - Status: local adaptation.
  - Meaning: local shorthand for balancing Dijkstra's correctness and intellectual-grip standard with Hoare's account of reliability emerging from testing, review, defensive programming as deliberate over-engineering, maintenance, feedback, mathematical habits, and managed engineering practice.
  - Canonical note: `concepts/programming-hyperreality.md`.

- Irretrievability
  - Status: external claim, locally qualified.
  - Meaning: the risk that after a serious failure the system no longer preserves observation, control, rollback, authority, or another acceptable attempt. In this repo, it is used as an engineering check before high-consequence action, without requiring wholesale agreement with the source's ASI conclusions.
  - Canonical note: `concepts/error-handling-and-fault-tolerance.md`.

- Lacanian approach to programming language
  - Status: local adaptation, exploratory.
  - Meaning: a psychoanalytic lens for asking how programmers, reviewers, users, and AI agents are organized by signifiers such as names, tests, diagrams, prompts, dashboards, and formal artifacts; useful only when it improves a concrete programming diagnosis.
  - Canonical note: `concepts/lacanian-approach-to-programming-language.md`.

- Let it crash
  - Status: standard Erlang slogan, locally qualified.
  - Meaning: Armstrong's Erlang fault-tolerance slogan: when an isolated worker cannot safely continue, let it fail quickly and let linked supervisors handle restart, fallback, escalation, and logging. It is not a license to ignore expected domain errors, untrusted inputs, irreversible side effects, or safety-critical invariants.
  - Canonical note: `concepts/error-handling-and-fault-tolerance.md`.

- Meta-review
  - Status: repo workflow term.
  - Meaning: a review of routing, documentation hierarchy, duplication, retrieval paths, and whether Markdown changes captured high-level mandates and insights.
  - Canonical skill: `skills/attention-management-review/SKILL.md`.

- Neuro-symbolic causal debugging
  - Status: local adaptation.
  - Meaning: a debugging approach that uses neural models for messy extraction and hypothesis generation, symbolic rules for inspectable derivation, and causal interventions for root-cause validation.
  - Canonical concept: `concepts/causal-code-intelligence.md`.

- No silver bullet
  - Status: standard phrase, locally developed.
  - Meaning: Brooks's warning that no single technology or management technique can by itself remove software's essential complexity. In this repo, it balances the temptation to treat English-driven AI or formal proof as complete liberation from programming difficulty.
  - Canonical note: `concepts/english-as-programming-interface.md`.

- Ouroboros
  - Status: local adaptation.
  - Meaning: a closed loop where representations validate other representations and no outside contact is required.
  - Canonical note: `concepts/programming-hyperreality.md`.

- Plan review
  - Status: repo workflow term.
  - Meaning: mandatory closeout review for each completed `PLAN.md` sequence.
  - Canonical skill: `skills/plan-review/SKILL.md`.

- Programming hyperreality
  - Status: local coinage.
  - Meaning: the condition where signs of engineering rigor outcompete contact with correctness, cost, users, production behavior, and understanding.
  - Canonical note: `concepts/programming-hyperreality.md`.
  - Provenance note: applies Baudrillard's broader idea of hyperreality to software engineering practice, but is not treated as a standard term of art.

- Proof as attention cache
  - Status: local adaptation.
  - Meaning: the use of proof, types, or formal checks to let attention move away from settled claims and toward assumptions, changed boundaries, and uncovered claims. It is controlled forgetting, not neglect.
  - Canonical note: `concepts/attention-management.md`.

- Retrieval and action system
  - Status: local coinage.
  - Meaning: a knowledge base organized to make future retrieval and action easier, not merely to store thoughts.
  - Canonical note: `concepts/retrieval-and-action-system.md`.

- Semantic anchor
  - Status: local adaptation.
  - Meaning: the best-fit formal artifact that fixes the intended meaning during translation, validation, or implementation in a less suitable target language.
  - Canonical note: `concepts/code-as-pseudocode-translation-protocol.md`.

- Simulacra of the code
  - Status: local adaptation.
  - Meaning: the user's original framing for code-facing representations that can start to stand in for code, system behavior, or understanding itself. Formal shadows are the useful checkable subset; simulacra names the broader risk that representation displaces reality contact.
  - Canonical note: `concepts/code-simulacra-and-formal-shadows.md`.

- Soundness/validity evidence split
  - Status: local adaptation.
  - Meaning: local reframing of software testing versus proof. Proof establishes validity inside a formal frame; tests and observations support the broader soundness of premises, models, requirements, environment assumptions, and world fit. The framing critiques overusing tests and making broader claims than a test suite can warrant, while also preserving the need for tests where formal models meet reality. Use carefully because soundness and validity have narrower technical meanings in logic and formal methods.
  - Canonical note: `concepts/soundness-validity-and-software-evidence.md`.

- Twelfth camel
  - Status: local adaptation.
  - Meaning: a disciplined fiction introduced to make an operation possible, then withdrawn or tested against reality.
  - Canonical note: `concepts/programming-hyperreality.md`.

- Weakest real formal artifact
  - Status: local adaptation.
  - Meaning: the least elaborate programming, modeling, query, proof, simulation, or specification artifact whose semantics are strong enough to express and check the claim at hand.
  - Canonical note: `concepts/code-as-pseudocode-and-executable-specs.md`.
