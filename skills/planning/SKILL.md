---
name: planning
description: Manage broad multi-step work in this repository with temporary PLAN.md coordination. Use when a task is cross-cutting, multi-turn, order-dependent, source-heavy, likely to need staged decisions, or when the user asks for planning, research planning, PLAN.md, task sequencing, status tracking, plan updates, or plan archival.
---

# Planning

Use `PLAN.md` as temporary coordination for broad active work. Do not let it become a second knowledge base, TODO dump, or specification.

Planning should preserve, sharpen, and apply high-level mandates and insights while respecting the attention hierarchy: hot routing in `AGENTS.md` and `PLAN.md`, focused policy in `docs/`, reusable workflows in `skills/`, durable knowledge in `projects/`, `concepts/`, or `observations/`, and static plugin routing in `.codex-plugin/` and `.agents/plugins/`.

## When To Use PLAN.md

Suggest or update `PLAN.md` when a task has at least two of these properties:

- crosses several areas, such as docs, skills, concepts, projects, observations, or tooling;
- will likely span multiple turns;
- has order-dependent decisions;
- needs temporary decisions before promotion into durable docs or skills;
- may affect plugin-facing skills, references, metadata, or install routing;
- may benefit from sidecar audits or delegated work after user approval.

Do not create `PLAN.md` for one-file edits, narrow wording changes, simple reviews, isolated README updates, or direct skill edits with a clear scope.

If a broad task arrives after a long conversation, check whether the scope is stale or ambiguous. Ask the user to restate the plan only when restatement would prevent carrying forward an obsolete plan.

## Research Seed Protocol

Use this protocol when the user begins research with a large coherent but poorly structured text block.

1. First clean spelling and grammar while preserving the user's meaning and emphasis.
2. When `PLAN.md` is created for this research, preserve the original large coherent but unstructured user text in `PLAN.md` exactly as written under a clearly labeled original-seed section. Treat this as an intentional exception to keeping the active plan short, and remove or promote it during plan closeout.
3. Restructure the points into a clear outline without dropping claims, examples, cautions, or open questions.
4. Check the restructuring with the user before creating or updating `PLAN.md` for the research.
5. If the user agrees, create a short research plan that includes fact-checking, critique, source collection, synthesis, and promotion targets.
6. Ask the user to iterate on the plan until open decisions are resolved, or until the user explicitly marks specific decisions as deferred.
7. Ask the user for a final go before starting planning execution, research, source collection, delegated agents, or synthesis beyond the agreed plan.
8. Surface ambiguities as questions or open decisions instead of silently resolving them.
9. Keep a running reference record in the plan while research is active, then promote important references into the durable note or source note.

The plan should keep the user's original thesis visible as user interpretation, separate from confirmed facts, assistant inferences, source notes, corrections, and open questions.

When delegated agents are used, tell them that the verbatim original-seed section initiated the whole plan and is their grounding context for the user's intent. Ask them to use the restructured outline for execution while checking their interpretation against the original seed, especially when critiquing, narrowing, or rephrasing the user's claims.

## Agreement Gates

For planning and research work, do not treat a first draft plan as authorization to execute.

1. After drafting or materially updating a plan, explicitly ask the user to iterate with you until every open decision is either resolved or deliberately deferred.
2. Keep unresolved choices visible in `PLAN.md` as open decisions; do not convert them into assumptions unless the user approves that assumption.
3. After the user agrees that the plan is ready, ask for the final go before starting execution, research, source gathering, delegated agent work, or synthesis.
4. If the user gives new steering after the final go but before execution is complete, return to the iteration gate when the steering changes scope, sources, output shape, or acceptance criteria.
5. If genuine new open questions arise during planning, research, delegated agent work, or synthesis, follow the staged plan review loop: stage the current agreed `PLAN.md`, update `PLAN.md` with those questions, leave the new edits unstaged, notify the user to review the plan diff, and return to the iteration gate. The previous final go no longer authorizes work affected by those questions.

## Staged Plan Review Loop

Use Git staging to make plan iteration reviewable when `PLAN.md` is active.

This is the only automatic staging exception. Do not run `git add` for ordinary durable edits, concept notes, docs, skills, source files, or final outputs. Also do not unstage those files if the user staged them. Non-`PLAN.md` staging state belongs to the user.

1. After writing the first draft of `PLAN.md`, stage that file only with `git add PLAN.md`.
2. Before starting each new clarification-driven iteration, stage the current agreed or baseline `PLAN.md` with `git add PLAN.md`.
3. After editing `PLAN.md` for that iteration, leave the new edits unstaged. Summarize what changed, then ask the user to review the unstaged-vs-staged diff in VS Code Git diff.
4. When the user agrees that the plan is ready, stage `PLAN.md` again with `git add PLAN.md`, then ask for the final go before execution or research begins.
5. When the whole plan is completed, unstage `PLAN.md` so temporary coordination does not remain staged. Leave the working-tree contents intact unless plan review calls for deleting or shrinking the file.

Do not stage or unstage unrelated files as part of this loop. If `PLAN.md` contains user edits that are not part of the current iteration, preserve them and call out the boundary.

## Workflow

1. If `PLAN.md` exists, read it before broad cross-cutting work.
2. Before substantial plan-driven edits, present a concise checkpoint:
   - goal;
   - high-level mandates and insights that should guide the work;
   - assumptions;
   - likely files or areas;
   - decisions that need user input;
   - what may be promoted to durable docs, skills, concepts, projects, or observations;
   - whether the static `useai` plugin may need skill, reference, metadata, marketplace, or validation updates.
3. Keep the plan short and active:
   - goal;
   - invariants;
   - workstreams;
   - current step;
   - relevant mandates and insights;
   - decisions made;
   - open decisions;
   - open questions raised during research or delegated work;
   - delegated work, if authorized;
   - plugin/export impact, if any;
   - promotion rules.
4. Update the current step as work progresses.
5. Promote durable material out of `PLAN.md`:
   - reusable workflows -> `skills/`;
   - shared process -> `docs/`;
   - cross-project ideas -> `concepts/`;
   - project state -> `projects/`;
   - self-observation or observed lessons -> `observations/`;
   - portable plugin behavior -> `skills/`, `concepts/`, `docs/`, `.codex-plugin/plugin.json`, `.agents/plugins/marketplace.json`, or `skills/useai-plugin-maintenance/SKILL.md`.
6. After broad planning work touches several files, use `skills/attention-management-review/SKILL.md` as a meta-review to check whether Markdown changes captured, refined, and highlighted high-level mandates and insights, and to check duplication, routing clarity, stale links, retrieval paths, static plugin impact, and validation coverage.
7. Every completed plan sequence must use `skills/plan-review/SKILL.md` as the closeout step. Do this even when the work seemed straightforward, because the review is what catches scope drift, leftover temporary artifacts, and missed promotion.
8. After plan review, delete `PLAN.md` or shrink it to only live unresolved work.

## Delegated Work

Use delegated work only after the user authorizes it.

Good delegated work is bounded sidecar audit: routing docs, retrieval paths, duplicate policy, stale indexes, or independent validation. The main agent owns synthesis, sequencing, and final edits unless write scopes are explicitly split.

For source-heavy research, delegated work can include independent source summaries, fact-checking, counterargument collection, and critique of both the user's initial claims and other agents' findings. Assign each subagent a bounded question and require source links, uncertainty markers, and corrections. The main agent must reconcile conflicts, check important claims directly when needed, and own the final synthesis.

If a delegated agent raises a genuine new open question that affects scope, sources, output shape, acceptance criteria, or interpretation, the main agent must add it to `PLAN.md` using the staged plan review loop, notify the user to review it, and restart the planning iteration gate before continuing affected work.

## Writing Rules

- Preserve unresolved points as open decisions, not requirements.
- When open decisions are resolved and promoted into durable notes, remove stale open-question sections and write the answers into normal prose, metadata, glossary entries, decision records, routing notes, or workflow rules.
- Keep English clear, brief, and consistent.
- Prefer links to canonical docs over copying policy into the plan.
- Keep `PLAN.md` useful for action, not exhaustive history.
- Do not automatically stage or unstage non-`PLAN.md` changes. Report changed files and leave non-`PLAN.md` index state to the user.
- Treat the Markdown corpus as a data-driven attention hierarchy: hot information should stay short and easy to load; colder information should remain reachable through backlinks.
- When the repo itself is being developed as a plugin source, plan for both audiences: future contributors using this checkout and Codex instances using the static `useai` plugin.
- If plugin-facing skills, selected references, or plugin metadata change, validate the static plugin through `skills/useai-plugin-maintenance/SKILL.md`.
- Do not finish a completed plan without running `useai:plan-review`.
- Mention in the final answer whether `PLAN.md` was created, updated, shrunk, removed, or left unchanged.
