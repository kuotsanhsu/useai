---
name: plan-review
description: Review every completed or nearly completed PLAN.md-driven work sequence. Use whenever a PLAN.md sequence ends, after broad cross-cutting work, or when Codex should compare plan to outcome, identify planning failure modes, promote durable lessons, and decide whether planning or attention-management rules should change.
---

# Plan Review

Reflect on each completed broad plan as an artifact of knowledge work. The review should improve future planning, not merely summarize what happened.

Plan review is mandatory closeout for every completed `PLAN.md` sequence. If a meta-review was required because the plan touched many files, use the meta-review result as an input before finalizing the plan.

Plan review is human-facing. Keep the user able to correct the retrospective, explain what felt useful or wasteful, and decide whether the workflow should change.

## Inputs

Read only what is needed:

1. The original `PLAN.md` if it still exists, or the durable record in related docs, skills, concepts, projects, observations, and git diffs if it was removed.
2. The final changed files and validation results.
3. Any authorized sidecar audit or independent validation results.
4. `skills/planning/SKILL.md`.
5. `skills/attention-management-review/SKILL.md` if the plan touched routing, docs, skills, or attention-management rules.
6. The meta-review output if broad plan-driven work touched many files.
7. `observations/observed-lessons.md` only when the user asks for observed lessons, a plan review needs precedent, or a workflow rule is being reconsidered.

## Review Questions

Answer these directly:

- What was the original goal?
- What actually changed?
- Which changes became durable knowledge, and where?
- Which temporary artifacts were removed, shrunk, or accidentally left behind?
- Did the plan preserve high-level mandates and the attention hierarchy?
- Did Markdown changes capture, refine, and highlight high-level mandates and insights?
- If many files changed, was a meta-review run before finalizing?
- Did the plan prevent scope drift, or did it create unnecessary overhead?
- Was delegated work useful, premature, absent, or overused?
- Did validation agree with the intended repository understanding?
- What should change in `skills/planning`, `skills/attention-management-review`, `docs/onboarding.md`, `docs/attention-management.md`, `AGENTS.md`, or durable knowledge notes?

## Output

For review-only requests, report:

1. findings first, ordered by impact;
2. useful planning behaviors to preserve;
3. planning failure modes or overhead;
4. durable follow-ups;
5. whether the planning skill or attention-management system should change.

For fix requests, make scoped edits. Prefer updating existing canonical files over creating more process docs.

Before changing `skills/planning` or other high-level process rules, surface the proposed lesson and why it follows from the completed plan. If the user has not already asked for the edit, ask for feedback before making the durable process change.

## Promotion Rules

- Planning workflow lessons belong in `skills/planning`.
- Post-plan review workflow belongs in this skill.
- Repo-wide attention-management lessons belong in `skills/attention-management-review`, `docs/attention-management.md`, or `concepts/attention-management.md`.
- Concrete observed lessons belong in `observations/observed-lessons.md` unless they are essential operating rules.
- Durable project state belongs in `projects/`.
- Cross-project ideas belong in `concepts/`.
- Reusable procedures belong in `skills/`.
