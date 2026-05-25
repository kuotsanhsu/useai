---
name: attention-management-review
description: Review and improve this repository's attention-management system. Use when Codex is asked to audit, copy, enforce, shorten, or repair AGENTS.md routing, onboarding, directory layout, documentation style, local skills, PLAN.md use, knowledge-base retrieval paths, meta-review after broad planning work, or broad repo/docs consistency.
---

# Attention Management Review

Use this skill as the repository meta-review. Keep the repository usable under attention constraints, and verify that Markdown changes capture, refine, and highlight high-level mandates and insights.

## Workflow

1. Start with the hot routing:
   - `AGENTS.md`
   - `PLAN.md` if present
   - `README.md`
   - `docs/onboarding.md`

2. Read focused policy only as needed:
   - `docs/attention-management.md`
   - `docs/directory-layout.md`
   - `docs/documentation-style.md`
   - relevant `skills/*/SKILL.md`

3. Identify canonical sources before judging duplication. Repetition is allowed when it acts as a local reminder, but it must point back to the same source of truth and must not change the rule.

4. Check the information hierarchy:
   - hot routing should be short and prominent;
   - focused policy should live in focused docs;
   - reusable workflows should live in skills;
   - durable evidence and reflection should have retrieval paths through README, indexes, or source notes.

5. Check high-level mandate handling:
   - important mandates and insights should be visible in hot or focused documents;
   - detailed support can live colder, but must be linked;
   - Markdown edits should improve the attention hierarchy instead of scattering guidance.

6. Check file purpose and reachability. New files should have an obvious bucket, purpose, and retrieval path. Do not delete or move files solely because they look weakly referenced; record the uncertainty or ask if ownership is unclear.

7. Check for unexpected unresolved open questions, open decisions, or ambiguous ownership that should have been caught by planning. Treat meta-review as a late safeguard, not the normal place to manage planning questions. Ask the user to resolve them, explicitly defer them, or restart planning if the issue changes scope. When open questions have been resolved, verify that the stale open-question section was removed and the answers were written into the appropriate normal location instead of left as a resolved-question ledger.

8. Check whether the reviewed scope is large, cross-cutting, multi-turn, source-heavy, or order-dependent. If so, use `skills/planning/SKILL.md` and temporary `PLAN.md` coordination instead of continuing as an ad hoc review.

9. Check for accidental automatic index changes. Only `PLAN.md` may be staged or unstaged by the agent as part of the planning loop. Durable docs, skills, concepts, source files, and final outputs must not be automatically staged or unstaged; preserve user-controlled index state.

10. Report findings first for review-only requests. For fix requests, make scoped edits that reduce drift or ambiguity.

## Whole Project Mode

Use this mode when the user asks for a whole-project meta-review.

- Treat the review as deep by default; use `skills/planning/SKILL.md` and `PLAN.md` before execution.
- Review all non-ignored files present in the worktree, including tracked, staged, unstaged, and untracked files. Treat `.gitignore` as the explicit exclusion boundary.
- Use read-only agents for parallel audits when that can speed up docs, skills, concepts, projects, observations, or worktree-hygiene review.
- Make scoped fixes automatically when findings are clear, but do not automatically stage or unstage non-`PLAN.md` files.

## Review Checklist

- `AGENTS.md` is short enough to use under attention constraints.
- `AGENTS.md` points to `docs/attention-management.md` instead of listing every route.
- Detailed policy is not duplicated in `AGENTS.md`.
- New or changed files have a retrieval path.
- README, onboarding, docs, skills, and knowledge-base notes do not describe conflicting workflows.
- Broad work uses `PLAN.md` only as temporary coordination.
- Planning and plan-review behavior is routed through `skills/planning` and `skills/plan-review`.
- After broad plan-driven work touches many files, a meta-review checks whether high-level mandates and insights are captured, refined, and highlighted.
- Large, cross-cutting, multi-turn, source-heavy, or order-dependent scopes are routed through `skills/planning/SKILL.md` and `PLAN.md`.
- Open questions and open decisions are surfaced to the user for resolution or explicit deferral.
- Resolved open questions are folded into the right durable prose, metadata, glossary, decision record, routing note, or workflow rule; stale open-question sections are removed.
- Only `PLAN.md` is automatically staged or unstaged, and only as part of the planning review loop; all other files keep the user's existing index state.
- Markdown follows the CPU memory hierarchy analogy: hot information is short and prominent; colder information is detailed but retrievable.
- Durable lessons are promoted out of temporary plans into docs, skills, project notes, concept notes, or observations.
- Uncertainty remains visible instead of becoming a hidden requirement.
- Reusable lessons are stated directly without unnecessary source framing.
- Changes to `concepts/attention-management.md` and `docs/attention-management.md` are checked against each other.

## Output

For review-only requests, return:

1. findings ordered by impact;
2. what is working and should be preserved;
3. durable follow-ups;
4. whether any skill, doc, README, or AGENTS update is warranted.

For fix requests, make the smallest durable change and mention whether related docs needed synchronization.
