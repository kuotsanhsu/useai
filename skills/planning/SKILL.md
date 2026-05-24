---
name: planning
description: Manage broad multi-step work in this repository with temporary PLAN.md coordination. Use when a task is cross-cutting, multi-turn, order-dependent, likely to need staged decisions, or when the user asks for planning, PLAN.md, task sequencing, status tracking, plan updates, or plan archival.
---

# Planning

Use `PLAN.md` as temporary coordination for broad active work. Do not let it become a second knowledge base, TODO dump, or specification.

Planning should preserve, sharpen, and apply high-level mandates and insights while respecting the attention hierarchy: hot routing in `AGENTS.md` and `PLAN.md`, focused policy in `docs/`, reusable workflows in `skills/`, and durable knowledge in `projects/`, `concepts/`, or `observations/`.

## When To Use PLAN.md

Suggest or update `PLAN.md` when a task has at least two of these properties:

- crosses several areas, such as docs, skills, concepts, projects, observations, or tooling;
- will likely span multiple turns;
- has order-dependent decisions;
- needs temporary decisions before promotion into durable docs or skills;
- may benefit from sidecar audits or delegated work after user approval.

Do not create `PLAN.md` for one-file edits, narrow wording changes, simple reviews, isolated README updates, or direct skill edits with a clear scope.

If a broad task arrives after a long conversation, check whether the scope is stale or ambiguous. Ask the user to restate the plan only when restatement would prevent carrying forward an obsolete plan.

## Workflow

1. If `PLAN.md` exists, read it before broad cross-cutting work.
2. Before substantial plan-driven edits, present a concise checkpoint:
   - goal;
   - high-level mandates and insights that should guide the work;
   - assumptions;
   - likely files or areas;
   - decisions that need user input;
   - what may be promoted to durable docs, skills, concepts, projects, or observations.
3. Keep the plan short and active:
   - goal;
   - invariants;
   - workstreams;
   - current step;
   - relevant mandates and insights;
   - decisions made;
   - open decisions;
   - delegated work, if authorized;
   - promotion rules.
4. Update the current step as work progresses.
5. Promote durable material out of `PLAN.md`:
   - reusable workflows -> `skills/`;
   - shared process -> `docs/`;
   - cross-project ideas -> `concepts/`;
   - project state -> `projects/`;
   - self-observation or observed lessons -> `observations/`.
6. After broad planning work touches several files, use `skills/attention-management-review/SKILL.md` as a meta-review to check whether Markdown changes captured, refined, and highlighted high-level mandates and insights, and to check duplication, routing clarity, stale links, and retrieval paths.
7. Every completed plan sequence must use `skills/plan-review/SKILL.md` as the closeout step. Do this even when the work seemed straightforward, because the review is what catches scope drift, leftover temporary artifacts, and missed promotion.
8. After plan review, delete `PLAN.md` or shrink it to only live unresolved work.

## Delegated Work

Use delegated work only after the user authorizes it.

Good delegated work is bounded sidecar audit: routing docs, retrieval paths, duplicate policy, stale indexes, or independent validation. The main agent owns synthesis, sequencing, and final edits unless write scopes are explicitly split.

## Writing Rules

- Preserve unresolved points as open decisions, not requirements.
- Keep English clear, brief, and consistent.
- Prefer links to canonical docs over copying policy into the plan.
- Keep `PLAN.md` useful for action, not exhaustive history.
- Treat the Markdown corpus as a data-driven attention hierarchy: hot information should stay short and easy to load; colder information should remain reachable through backlinks.
- Do not finish a completed plan without running the plan-review skill.
- Mention in the final answer whether `PLAN.md` was created, updated, shrunk, removed, or left unchanged.
