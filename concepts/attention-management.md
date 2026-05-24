---
id: attention-management
kind: concept
status: active
source:
  - user-statement: "An important topic I would like to develop is attention management"
  - user-statement: "To forget is a feature not a bug."
  - user-statement: "This is the economy of attention."
  - user-statement: "Proof can shift attention away from formally covered claims until assumptions change."
  - user-statement: "Proofs free attention for other things; otherwise doubt keeps producing more tests."
  - source-note: "Elbert Hubbard quote on retentive memory and forgetting, attributed in The Note Book of Elbert Hubbard"
  - source-note: "Hulbert and Anderson, The Role of Inhibition in Learning"
tags: [attention, knowledge-work, systems, workflow, metacognition, memory, forgetting, economics]
depends_on: []
related: [retrieval-and-action-system, attention-management-reference-map, formal-attention-linear-logic, programming-hyperreality, soundness-validity-and-software-evidence, docs/attention-management.md, skills/planning, skills/plan-review]
used_by: [docs/attention-management.md, skills/attention-management-review, skills/planning, skills/plan-review]
supersedes: []
---

# Attention Management

Attention management is the design of systems that preserve limited human and AI attention for the work that matters.

In this repository, the term has both a practical and conceptual role:

- Practical: make future agents read the right thing at the right time.
- Conceptual: study how attention is allocated, protected, redirected, overloaded, or wasted in deep knowledge work.

## Working Definition

Attention management is not just "focus". It is the deliberate organization of context, reminders, triggers, boundaries, and review loops so that important actions become easier to take and irrelevant detail becomes easier to ignore.

This repository treats attention management as data-driven design for knowledge work: structure should change in response to observed use, retrieval failures, repeated friction, and durable insights.

## Forgetting

Forgetting is a feature, not a bug. It is one of the natural mechanisms by which attention protects focus.

Because forgetting is expected, attention management should not try to preserve everything equally. It should ask what is worth remembering, then create deliberate practices, structures, reminders, and retrieval paths around those things.

The goal is not merely to store important ideas externally. The goal is to put enough effort into remembering them that they become embodied over time: easier to notice, easier to use, and more naturally present in future work.

The Elbert Hubbard line usually appears as "A retentive memory may be a good thing, but the ability to forget is the true token of greatness." The point, for this repository, is not moral self-congratulation and not careless deletion. It is discrimination. A great memory retains what matters; a greater discipline also releases what no longer deserves active attention.

This matches a functional view of forgetting in memory research: irrelevant or outdated material can compete with the thing currently needed, and selective inhibition can make action easier. Forgetting is therefore not only loss. It can be an active protection against interference.

## Economy Of Attention

Attention is scarce. Humans and AI systems are both bound by attention constraints, and those constraints can be useful because they force selection.

To pay attention to everything is to pay attention to nothing. A useful knowledge-work system should therefore decide what deserves attention, what should remain retrievable but cold, and what can be allowed to fade.

## Proof As Attention Cache

Proof is an attention-management device. Once a claim is formally proved, attention can move away from that claim and toward the assumptions, axioms, model-world mapping, trusted implementation boundary, and claims not yet covered by proof.

This is controlled forgetting, not neglect. A proved claim does not have to remain a live doubt that continually demands more tests, more rereading, and more reassurance. It can be allowed to cool down, while the assumptions and invalidation conditions stay retrievable.

The benefit is not that proof removes all attention. It localizes attention. When assumptions change, a proof assistant can expose dependent breakage through failed elaboration or typechecking, turning hidden logical invalidation into an explicit repair list.

For the software-engineering version of this idea, see `concepts/soundness-validity-and-software-evidence.md`.

## Artifact Drift

Attention can migrate from the work into artifacts that represent the work: dashboards, AI summaries, tests, metrics, plans, diagrams, and process rituals. These artifacts are useful when they compress reality and point back to action. They become dangerous when maintaining the representation becomes more attractive than inhabiting the thing represented.

For the software-engineering version of this problem, see `concepts/programming-hyperreality.md`.

## CPU Memory Hierarchy

The repository should organize attention like a CPU memory hierarchy: small, hot, frequently accessed state near the active task; larger, colder, more ambiguous material farther away but still reachable.

- Register-like state: the smallest active routing state, such as the prime directive and current plan step.
- L1-like cache: short private context needed for immediate action, such as `AGENTS.md` and active `PLAN.md`.
- L2/L3-like shared cache: onboarding, attention-management, layout, and documentation-style maps.
- RAM-like working memory: skills, project notes, concepts, observations, and active indexes.
- Disk-like cold storage: durable evidence, source notes, observed lessons, and older drafts.

Backlinks are the cache-line pointers of the system: hot documents should point to colder documents so detail can be loaded when needed without keeping everything in immediate attention.

## Threads To Explore Next

These are the strongest conceptual imports to develop next:

- Herbert Simon: information abundance creates attention scarcity.
- Daniel Kahneman: attention is a limited shared capacity, close to an attention budget.
- Sebastian Watzl: attention imposes a priority structure on mental life.
- Christopher Sims and rational inattention: limited information-processing capacity can be modeled as an economic constraint.
- Simone Weil and Iris Murdoch: attention shapes what one is capable of seeing; adapt this descriptively before importing moral judgment.
- Formal attention management through linear logic, focusing, and ludics: context as resource, proof search as disciplined attention, and loci as addressable sites of interaction.

For the colder reference map of relevant philosophers, psychologists, and economics researchers, see `concepts/attention-management-reference-map.md`.
For the formal proof-theoretic analogy, see `concepts/formal-attention-linear-logic.md`.

## Current Principles

- Keep hot routing small.
- Route through a focused map when the trigger list grows too large for the hot file.
- Put detailed policy in focused documents or skills.
- Treat forgetting as a natural filter; spend memory effort on what should shape future action.
- Treat attention as scarce; design for selection, not total coverage.
- Use proof, types, and other formal checks to cache settled claims and reroute attention to changed assumptions and uncovered claims.
- Keep representational artifacts answerable to the work they represent.
- Make Markdown changes capture, refine, and highlight high-level mandates and insights.
- Make every durable note retrievable from a nearby index, README, or router.
- Treat repetition as a local reminder only when it points back to the same source of truth and does not change the rule.
- Use temporary plans for broad active work, then always run plan review and promote durable lessons into stable notes.
- Run a meta-review after broad planning touches many files.
- Preserve uncertainty explicitly so unresolved issues do not masquerade as decisions.

## Questions To Develop

- When does a reminder help, and when does it become duplication noise?
- What makes a file "hot", "warm", or "cold" in an attention hierarchy?
- How should the CPU memory hierarchy analogy guide real file placement and backlinking?
- How should a system decide what must be read before action?
- How can action be enforced without creating too much process overhead?
- When does planning protect attention, and when does it become its own distraction?
- What belongs in memory, what belongs in a skill, and what belongs in a project note?
- How should attention management differ for humans, AI agents, and human-AI collaboration?

## Useful Lenses

- Systems engineering: boundaries, interfaces, feedback loops, failure modes.
- Operations research: queues, bottlenecks, prioritization, constraints.
- Psychology: working memory, salience, habit, avoidance, cognitive load.
- Economics: scarce attention, opportunity cost, incentives.
- Computer science: caching, indexing, routing, retrieval, locality.
- Philosophy: what deserves attention, what counts as relevance, how inquiry is structured.

## Relation To This Repo

The operational rules live in `docs/attention-management.md`. This note is for developing the broader idea over time.

Changes to this concept should trigger a check of the operational attention-management system. Changes to the operational system should trigger a check of this concept note.
