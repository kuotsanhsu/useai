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

7. Report findings first for review-only requests. For fix requests, make scoped edits that reduce drift or ambiguity.

## Review Checklist

- `AGENTS.md` is short enough to use under attention constraints.
- `AGENTS.md` points to `docs/attention-management.md` instead of listing every route.
- Detailed policy is not duplicated in `AGENTS.md`.
- New or changed files have a retrieval path.
- README, onboarding, docs, skills, and knowledge-base notes do not describe conflicting workflows.
- Broad work uses `PLAN.md` only as temporary coordination.
- Planning and plan-review behavior is routed through `skills/planning` and `skills/plan-review`.
- After broad plan-driven work touches many files, a meta-review checks whether high-level mandates and insights are captured, refined, and highlighted.
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
