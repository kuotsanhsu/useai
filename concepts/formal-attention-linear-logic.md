---
id: formal-attention-linear-logic
kind: concept
status: draft
source:
  - user-request: "Write down your previous findings regarding the formal analogy of linear logic with attention"
tags: [attention, linear-logic, focusing, ludics, proof-theory, formal-methods]
depends_on: [attention-management]
related: [attention-management, retrieval-and-action-system]
used_by: [attention-management]
supersedes: []
---

# Formal Attention And Linear Logic

This note records a formal analogy, not a claim of direct psychological or economic ancestry.

Linear logic, focusing, and ludics are useful for thinking about attention management because they formalize resource sensitivity, disciplined search, and addressable sites of interaction. The analogy should be used to sharpen repository design, not to treat proof theory as a theory of human attention.

## Core Analogy

- Linear logic treats assumptions as resources rather than freely copyable or discardable context. This fits the repository principle that attention is scarce and should not be spent on everything equally. See the [Stanford Encyclopedia of Philosophy entry on linear logic](https://plato.sydney.edu.au/entries/logic-linear/).

- Focusing reduces irrelevant proof-search choices by structuring derivations into disciplined phases. This fits the repository principle that future agents should read the right thing at the right time, instead of loading every possible context. See Jean-Marc Andreoli's [Logic Programming with Focusing Proofs in Linear Logic](https://academic.oup.com/logcom/article/2/3/297/1012743) and Robert Simmons's [Structural focalization](https://arxiv.org/abs/1109.6273).

- Loci in ludics suggest a model of addressable interaction sites. This fits the repository's backlink and CPU-memory-hierarchy model: every active item should have a location, and hotter documents should point to colder detail without carrying it all. See Jean-Yves Girard's [Locus Solum](https://girard.perso.math.cnrs.fr/0.pdf) and Pierre-Louis Curien's [Introduction to linear logic and ludics, part II](https://arxiv.org/abs/cs/0501039).

## Attribution Caution

- Linear logic was introduced by Jean-Yves Girard.
- Focusing in the linear-logic proof-search tradition is usually credited to Jean-Marc Andreoli.
- Loci belong more specifically to Girard's later ludics, not to basic 1987 linear logic.

The shared theme is not ordinary focus in the psychological sense. It is disciplined control over where search, interaction, and resource use happen.

## Design Implications

- Treat context as a resource. Do not make every agent read every note.
- Make active context locatable. A concept, rule, or decision should have a stable address in the repository.
- Reduce irrelevant branching. Routing documents and skills should narrow the next action rather than enumerate every possible path.
- Separate phases. Planning, execution, review, and promotion should not collapse into one undifferentiated activity.
- Preserve cold reachability. Detail can stay cold if hot documents provide reliable pointers to it.

## Research Directions

- Can focusing provide a better formal model for when an agent should stop searching and start acting?
- Can loci help define what counts as a stable address for a concept, rule, project, or observation?
- Can linear logic's treatment of resource use clarify when repetition is helpful reminder versus wasteful duplication?
- Can proof-search normalization inspire better plan-review or meta-review protocols?
