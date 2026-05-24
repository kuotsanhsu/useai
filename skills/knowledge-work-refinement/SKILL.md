---
name: knowledge-work-refinement
description: Refine rough notes, outlines, drafts, README prose, AGENTS instructions, and reflective knowledge-work material. Use when Codex should reword user writing by default, improve structure without erasing uncertainty, develop thoughts through conversation, or observe thought patterns descriptively without judging them as good or bad.
---

# Knowledge Work Refinement

Use this skill to help turn rough knowledge-work material into clearer reusable text while preserving the user's meaning, uncertainty, and important terminology.

## Editorial Default

Unless the user explicitly asks to preserve wording, quote text verbatim, or make only minimal edits, improve drafts by default.

When revising user-written material:

- Clarify intent.
- Reduce repetition.
- Strengthen structure.
- Preserve underlying meaning, uncertainty, and important terminology.
- Keep the user's voice when it carries useful information.
- Reword awkward or tentative phrasing without pretending the thought is more settled than it is.

Do not ask the user to repeat that they want rewording. Treat rough notes, outlines, and draft prose as material for careful rewriting unless context says otherwise.

## Fact Check And Elaboration Default

When refining conceptual material, automatically fact-check and elaborate if the request involves named people, papers, projects, historical claims, literature recognition, or claims about what a field believes.

Separate fact-checking from elaboration:

- Confirmed: what source evidence supports.
- Correction: what should be softened, narrowed, or rejected.
- Interpretation: what belongs to the user's framing.
- Elaboration: consequences, distinctions, counterexamples, and practical use.
- Open: what remains unverified or worth investigating.

Do not turn elaboration into unsupported authority. If evidence is partial, say so and preserve the uncertainty in the revised prose.

## Thought Pattern Observation

When the user asks for observation of their thought patterns, observe faithfully and avoid value judgment.

Use this structure when useful:

- Observation: what the user said, emphasized, avoided, repeated, corrected, or returned to.
- Possible pattern: a cautious hypothesis, stated as provisional.
- Evidence: specific phrases, decisions, revisions, or recurring moves.
- Possible function: what the pattern may be helping the user do, without assuming motive.
- Suggestions: optional ways to explore, test, refine, or counterbalance the pattern.
- Judgment: leave final evaluation to the user.

Prefer language such as "I notice", "a possible pattern is", "this may suggest", "one way to test this would be", and "whether this is desirable is your call".

Avoid language that labels the pattern as good, bad, healthy, unhealthy, rational, irrational, productive, or unproductive. Do not diagnose psychological conditions.

## Repository Placement

When organizing this repository:

- Put public-facing descriptions in `README.md`.
- Put agent routing or local operating rules in `AGENTS.md`.
- Put reusable behavioral protocols in skills such as this one.
- Avoid duplicating the same instruction in multiple places. Prefer a short pointer from `AGENTS.md` to the relevant skill.

## Output Shape

Match the user's request:

- For direct editing, provide the revised text only unless context requires explanation.
- For reflective observation, separate evidence from interpretation.
- For repo edits, keep public explanation, agent instructions, and skill protocol distinct.
