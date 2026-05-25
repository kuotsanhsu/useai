# Documentation Style

This document is the source of truth for repository documentation style. Keep `AGENTS.md` as routing and put detailed documentation rules here.

## Uncertainty

Preserve status markers such as **UNCLEAR**, **TENTATIVE**, **TODO**, and **WIP**. Do not convert open questions, hypotheses, or rough notes into requirements without a confirmed decision.

When open questions are resolved, remove the stale open-question section and write the answers into the appropriate normal location: prose, front matter, glossary, decision record, routing note, or workflow rule. Do not leave a resolved-question answer ledger unless the document is explicitly a retrospective or decision log.

Separate:

- confirmed facts;
- user corrections;
- source notes;
- hypotheses;
- open questions;
- decisions;
- tool limitations;
- observed lessons.

## Information Hierarchy

Markdown changes should capture, refine, and highlight high-level mandates and insights. Do not leave important direction buried only in chat, temporary plans, or long notes.

Organize Markdown by length, importance, scope, and ambiguity:

- hot routing belongs in `AGENTS.md` and active `PLAN.md`;
- first orientation belongs in `docs/onboarding.md`;
- shared policy belongs in focused docs under `docs/`;
- reusable workflows belong in `skills/`;
- durable but colder evidence and reflection belong in `projects/`, `concepts/`, or `observations/`.
- temporary coordination for broad active work belongs in `PLAN.md`, then durable lessons should be promoted out when the work completes.

If a single note becomes too long to scan, split it by scope, action, ambiguity, or evidence level. Keep a short overview note as the router, move focused material into linked child notes, and preserve backlinks, provenance, and glossary links.

The conceptual model is the CPU memory hierarchy described in `concepts/attention-management.md`.

Use backlinks from hotter documents to colder documents so future agents can find relevant detail without loading everything eagerly.

When adding or moving Markdown files, add enough links or front matter for the file to be discoverable from an appropriate router, index, source note, or README section.

When introducing or clarifying a durable term, check whether it belongs in `concepts/glossary.md`. Add or update the glossary entry when the term is local coinage, a local adaptation of a standard term, a repo workflow term, or a term whose standardness is uncertain. Mark the status explicitly instead of implying literature recognition.

After broad `PLAN.md`-driven work touches many files, run a meta-review with `skills/attention-management-review/SKILL.md` before treating the work as complete.

## English

When editing project prose, improve wording for clarity, brevity, and consistency as part of the edit. Preserve meaning, uncertainty, and corrected terminology.

## Fact Check And Elaboration

When developing conceptual notes from conversation, fact-checking and elaboration are automatic unless the user explicitly asks for a quick unverified draft.

Use this default when the note involves named people, papers, projects, historical claims, source-sensitive claims, literature recognition, or claims about what a field believes.

Separate:

- what is confirmed by sources;
- what needs correction or softening;
- what is the user's interpretation;
- what is an assistant inference;
- what remains open.

Elaboration should explain consequences, distinctions, counterexamples, and practical use. It should not inflate weak evidence into a stronger claim. If a claim cannot be checked in the moment, mark it as unverified, tentative, or source-needed.

For durable Markdown, prefer inline source links near the claims they support plus a short source note in front matter when the source is important to retrieval.

## Markdown

Prefer ordinary Markdown that renders well in VS Code and GitHub. Use concise headings, short paragraphs, and lists only where they improve scanability.

In reference notes, use bullet lists instead of Markdown tables. Bullets are easier to edit incrementally, keep diffs smaller, and avoid forcing cold reference material into rigid columns.

In YAML front matter, keep compact list mappings such as `- source-note: "..."` simple. Avoid colons, parenthetical provenance, and renderer-sensitive punctuation in those values when they make diffs harder to review. This is primarily a diff-preview stability rule, not a claim that the Markdown file is invalid. Keep source-note values to the work title or source label, and put provenance details in body prose, inline links, or a separate front matter key.

In Markdown link targets, percent-encode reserved punctuation when a renderer misreads a valid URL. For example, prefer `uuid%3A...` over `uuid:...` in ORA object paths.

Avoid raw HTML and angle-bracket placeholders in Markdown, including inside inline code, unless the file explicitly requires HTML. Write placeholder examples as plain words, such as `projects/project-name/`, rather than with placeholder names wrapped in angle brackets. Rendered diff tools can misread HTML-like fragments and surface diff-marker spans.

When a Markdown issue appears only in a diff preview, first verify whether the file itself contains the suspicious text and whether the normal Markdown preview renders correctly. If the normal preview is correct and `rg` does not find the suspicious fragment, treat it as a diff-rendering artifact. Fix the file only when the artifact harms review, repeats often, or points to a pattern worth avoiding.

Markdown is permissive, so "syntax validity" is not a single yes/no property. Prefer layered validation:

- Run a real Markdown linter or parser when available, such as `markdownlint-cli2`, `markdownlint`, `cmark-gfm`, `pandoc`, or the VS Code Markdown preview.
- Use `git diff --check` for whitespace and patch hygiene.
- Use AI review on changed Markdown for meaning, hierarchy, links, provenance, local terminology, and whether the rendered prose follows this repository's attention-management rules.
- Do not rely on AI as the only syntax check. Parser and renderer behavior should be checked by tools when the exact Markdown rendering matters.

Use targeted `rg` checks only as smoke tests for known repository hazards, not as general Markdown validation. When Markdown or diff rendering looks wrong, check whether the suspicious fragment exists in the files:

```sh
rg -n -e "data[-]diff" -e "diff[-](start|end)" -e "\x3cspan" -e "\x3c/span" -e "\x3c[A-Za-z][A-Za-z0-9 /._:-]*\x3e" -g '*.md'
rg -n "^>" -g '*.md'
```
