---
name: conversational-kb-builder
description: Build an incremental, durable knowledge base through ongoing conversation. Use when Codex should capture evolving project understanding, user corrections, hypotheses, source notes, open questions, design decisions, tool limitations, or transferable lessons into checked-in Markdown while keeping evidence, inference, and action separate.
---

# Conversational KB Builder

Use this skill to turn conversation into a retrieval and action system. Prefer checked-in Markdown first; treat databases, embeddings, or generated indexes as later layers.

## Core Workflow

1. Listen for durable knowledge.
   Capture statements that would matter in a later session: project goals, terminology corrections, design boundaries, source limitations, evidence provenance, unresolved questions, and reusable workflow lessons.

2. Classify before writing.
   Put each note into a clear bucket:
   - `project-goal`: active objective or deliverable.
   - `clarification`: user correction or framing update.
   - `source-note`: source artifact summary and provenance.
   - `hypothesis`: plausible but unconfirmed lead.
   - `decision`: confirmed design or process decision.
   - `open-question`: unresolved issue needing user or source evidence.
   - `todo`: tracked follow-up from review, planning, or implementation.
   - `tool-limitation`: observed limitation of a connector, script, model, or workflow.
   - `observed-lesson`: lesson from completed work that may guide future work.

3. Preserve uncertainty.
   Do not convert speculation into requirements. Mark status explicitly: `confirmed`, `active`, `unconfirmed`, `awaiting-confirmation`, `resolved`, `superseded`, or `observed`.

4. Fact-check and elaborate source-sensitive claims automatically.
   When the conversation involves named people, papers, projects, historical claims, literature recognition, or claims about what a field believes, separate fact-checking from elaboration before writing durable notes.
   - Confirm what sources support.
   - Soften or correct overstrong claims.
   - Mark user interpretation, assistant inference, and open questions explicitly.
   - Add inline links near supported claims when the source matters.
   - If source access is incomplete, record the limitation instead of presenting the claim as settled.

5. Write small, stable notes.
   Prefer appending a focused entry to an existing note over creating scattered one-off files. Create a new file only when it represents a durable category.

6. Keep retrieval paths visible.
   Link notes from the nearest index, README, project map, or skill. A note that cannot be found later has not really entered the knowledge base.

7. Promote carefully.
   Keep rough captures, hypotheses, decisions, canonical specs, and implementation plans separate until the user asks to consolidate or the role of the note is clear.

## Markdown Header Pattern

For substantial KB files or entries, use compact YAML front matter:

```yaml
---
id: h-001
kind: hypothesis
status: unconfirmed
source:
  - docs/SPEC.md
  - /absolute/path/to/source.md
tags: [project, topic]
depends_on: []
related: []
used_by: []
supersedes: []
---
```

Use `depends_on` when one note cannot be understood without another. Use `used_by` when a note becomes input to a spec, test, decision, or implementation plan.

For index files, keep front matter minimal. The body of the index is the relationship map.

## Writing Rules

- Use corrected terminology after the user corrects it.
- Attribute claims: user statement, source file, connector result, search summary, or inference.
- Record source-access limitations when evidence is partial.
- Prefer source artifact summaries over long verbatim excerpts.
- When elaborating, add consequences, distinctions, counterexamples, and practical use only as far as the evidence supports.
- Keep notes concise enough to scan and concrete enough to guide later work.
- Do not erase earlier uncertainty silently; resolve it by updating status and adding a short resolution note.

## Placement

Default locations in this repo:

- `projects/project-name/`: project maps, decisions, open questions, source notes, and improvement logs.
- `concepts/`: cross-project ideas, models, distinctions, and references.
- `observations/`: descriptive records of thought and work patterns.
- `skills/`: reusable workflows and protocols.

Do not create a new top-level directory unless the purpose and retrieval path are clear.

## Reporting

In the final answer, distinguish durable KB changes from source-code or test changes. Mention unresolved uncertainty instead of presenting transferred lessons as universal truth.
