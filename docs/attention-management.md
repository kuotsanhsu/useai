# Attention Management

Attention management is the system that makes actions enforceable without turning `AGENTS.md` into a manual.

For conceptual development of the topic, see `concepts/attention-management.md`.

## Enforcement Model

Actions are enforced through trigger points:

- `AGENTS.md` stays short and names what to read or use.
- Focused docs hold detailed policy.
- Skills hold reusable workflows.
- `PLAN.md`, when present, holds temporary coordination for broad active work.
- Indexes and backlinks make colder knowledge discoverable.

The rule is simple: when an action crosses a boundary, read the boundary document first.

## Boundaries

- Orientation or status request: read `docs/onboarding.md`.
- File creation, movement, deletion, or reorganization: read `docs/directory-layout.md`.
- Markdown, KB, README, or skill edits: read `docs/documentation-style.md`.
- Durable conversational capture: use `skills/conversational-kb-builder/SKILL.md`.
- Draft refinement or thought-pattern observation: use `skills/knowledge-work-refinement/SKILL.md`.
- Broad multi-step work: use `skills/planning/SKILL.md`.
- Completed PLAN.md-driven work: use `skills/plan-review/SKILL.md`.
- Broad consistency review: use `skills/attention-management-review/SKILL.md`.

## Broad Work

Use `PLAN.md` only for broad, multi-step, cross-cutting work. It is temporary coordination, not a second knowledge base.

Planning must take high-level mandates and insights into account. A plan should identify the relevant mandates before sequencing work, then promote any durable insight back into docs, skills, concepts, projects, or observations.

Create or update `PLAN.md` when work crosses several areas, depends on sequencing, or needs temporary decisions before promotion into durable docs or skills.

Use `skills/planning/SKILL.md` to manage active plan-driven work.

The planning skill owns the only automatic index exception: `PLAN.md` may be staged or unstaged inside the planning review loop; all other file staging state belongs to the user.

Close out every completed `PLAN.md` sequence in this order:

- Promote durable lessons into the appropriate doc, skill, project note, concept note, or observation.
- If the work touched many files, run `skills/attention-management-review/SKILL.md` first so the plan review can use the meta-review result.
- Run `skills/plan-review/SKILL.md`.
- Remove `PLAN.md` or shrink it to live unresolved work.

## Documentation Sync

When editing a file, check whether the change affects a hotter or more canonical source:

- directory changes may require `docs/directory-layout.md`;
- Markdown or KB conventions may require `docs/documentation-style.md`;
- skill map or first-read changes may require `docs/onboarding.md`;
- public-facing purpose or structure changes may require `README.md`;
- reusable workflow changes belong in a skill, not `AGENTS.md`.

## Concept And Practice Sync

Attention management is both a concept being developed and a practice used by this repository.

When `concepts/attention-management.md` changes, check whether the operational system should change:

- `AGENTS.md` routing;
- this file;
- `docs/onboarding.md`;
- `docs/directory-layout.md`;
- `docs/documentation-style.md`;
- `skills/attention-management-review/SKILL.md`;
- related knowledge-base indexes or retrieval paths.

When the operational attention-management system changes, check whether `concepts/attention-management.md` should be updated with the broader principle, open question, or observed lesson.

If no sync update is needed, mention that in the final response.

## Design Principle

Organize information by importance, temperature, scope, and ambiguity. Hot routing should be short. Durable evidence can be colder, but it must have a retrieval path.

This is data-driven design for knowledge work: let the repository structure respond to observed use, repeated failures, retrieval needs, and durable insights.
