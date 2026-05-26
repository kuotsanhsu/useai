# useai

## Install As A Codex Plugin

This repo is itself a portable Codex plugin. The plugin manifest lives at `.codex-plugin/plugin.json`, and the local marketplace file lives at `.agents/plugins/marketplace.json`.

### From GitHub

For a normal user of this repo, the workflow is:

1. Clone or sync this repository from GitHub.
2. In Codex, add the cloned repo as a local plugin marketplace by selecting `.agents/plugins/marketplace.json`.
3. Install the plugin named `useai`.
4. Open any other project and ask Codex to use a namespaced skill such as `useai:planning`.

Do not point target projects at this repo with hard-coded absolute paths. Any machine-specific path belongs in the Codex plugin or marketplace configuration, not in the target project's checked-in files.

### Local Development

To use this plugin locally while also developing this repo, install the plugin from this working checkout's `.agents/plugins/marketplace.json`. Codex will load the checked-in plugin manifest, skills, docs, and concepts directly from this checkout.

From this checkout:

1. Confirm the marketplace file and plugin manifest exist:

   ```sh
   test -f .agents/plugins/marketplace.json
   test -f .codex-plugin/plugin.json
   ```

2. In Codex, add a local plugin marketplace from this file:

   ```text
   <this-checkout>/.agents/plugins/marketplace.json
   ```

3. In the Codex plugin UI, install `useai` from the `useai` marketplace.

4. Open another project in Codex and start a new session. Ask for one of the plugin skills by namespaced handle, such as `useai:planning`, `useai:conversational-kb-builder`, or `useai:code-as-pseudocode-analysis`.

5. Keep project-specific facts in that other project. The plugin should supply methods and references, not make the target project refer back to this checkout.

After changing plugin-facing skills, concepts, docs, plugin metadata, or this README in the useai checkout, validate the static plugin from the repo root:

```sh
python3 -m json.tool .codex-plugin/plugin.json
python3 -m json.tool .agents/plugins/marketplace.json
git diff --check
```

If the Codex plugin-creator validator is available in your environment, also run it against the repo root.

If Codex has already loaded the plugin, start a new session or reload plugins after editing so other projects see the updated checkout.

### Usage

In another project, ask Codex for the plugin skill you need:

- `Use useai:planning for this cross-cutting change.`
- `Use useai:code-as-pseudocode-analysis to analyze this codebase.`
- `Use useai:attention-management-review before closing out this repo-wide docs change.`

Target projects should keep their own facts, decisions, specs, tests, and evidence locally. The plugin supplies reusable methods and selected references.

This repository is a collection of skills, working knowledge, and reflective notes for deep knowledge work. It is meant to support software development, research, project management, and metacognitive practice by drawing from philosophy, psychology, economics, psychoanalysis, computer science, systems engineering, and operations research.

The repo treats knowledge work as an active practice: forming questions, building projects, testing assumptions, improving systems, and noticing the habits that shape the work. It is a retrieval and action system, not an archive.

## Purpose

This repository is intended to:

1. Guide the development of new projects from the earliest stages.
2. Support analysis of existing projects and identify concrete improvements.
3. Develop ideas through conversation with AI, combining human judgment with AI-assisted research, synthesis, editing, and critique.
4. Observe recurring habits, decision patterns, repeated questions, avoided questions, and productive routines.

## Repository Structure

Reusable workflows live under `skills/`. Shared process and attention-management rules live under `docs/`. Project-facing knowledge lives under `projects/`. Cross-project concepts live under `concepts/`. Reflective observations live under `observations/`. Static Codex plugin metadata lives under `.codex-plugin/`, with local marketplace routing under `.agents/plugins/`. Agent-facing routing and local operating rules live in `AGENTS.md`.

Current skills include:

- `skills/knowledge-work-refinement`: draft refinement, AI-assisted idea development, and descriptive observation of thought patterns.
- `skills/conversational-kb-builder`: durable knowledge-base capture from ongoing conversation.
- `skills/attention-management-review`: review of routing, documentation hierarchy, and retrieval paths.
- `skills/planning`: temporary `PLAN.md` coordination for broad work.
- `skills/plan-review`: retrospective review of completed plan-driven work.
- `skills/code-as-pseudocode-analysis`: semantic-anchor and validation analysis for implementations.
- `skills/useai-plugin-maintenance`: maintenance of this repo as a static Codex plugin.

## Knowledge Base

The knowledge base is organized for reuse. Notes should help me start, inspect, decide, revise, or notice something later.

Rough capture is welcome, but useful material should eventually be refined into one of four forms:

1. Skills: reusable procedures for recurring work.
2. Project knowledge: maps, assumptions, decisions, risks, and improvement ideas.
3. Conceptual knowledge: ideas, distinctions, models, and references that travel across projects.
4. Observations: descriptive records of habits, recurring questions, hesitations, corrections, and framing patterns.

The initial knowledge-base structure follows a simple rule: keep hot routing short, keep canonical meaning in clear sources, preserve uncertainty explicitly, and give every durable note a retrieval path.

## Portable Plugin

This repository is the plugin artifact. `.codex-plugin/plugin.json` points Codex at the checked-in `skills/` directory, and those skills route to reusable knowledge in `concepts/` and `docs/`.

There is no generation step and no copied `references/` tree. Edit the canonical source files directly, then reload the plugin in Codex when another project needs the update.

## Working Style

Notes, outlines, and draft thoughts in this repository are treated as provisional material for continued refinement, synthesis, and reuse. Some material may track patterns in how I think, decide, revise, hesitate, return to questions, or frame problems.

The goal is not to polish away uncertainty. The goal is to make partially formed thinking easier to inspect, extend, and develop.

## Project Inspiration

This repository is shaped by a few connected sources and questions:

- Jason Cheng's recommendations to read Vijay Janapa Reddi's ["English Is a Programming Language"](https://vijay.seas.harvard.edu/blog/english-is-pl) and Vaishak Belle and Gary Marcus's ["The Future Is Neuro-Symbolic: Where Has It Been, and Where Is It Going?"](https://doi.org/10.1609/aaai.v40i48.42130).
- A realization that formal methods and mathematics can offload attention and decisions reliably to arithmetic, processes, and computers, while language remains powerful but limited.
- Studies of Frege, Godel, Hoare, Dijkstra, Lamport, Alan Kay, Martin-Lof, Jean-Yves Girard, Judea Pearl, Benjamin C. Pierce, and Adam Chlipala, alongside practical experience using Lean 4.
- Broader study of non-classical logics and their implications for programming.
- A live question: whether Prolog- or Datalog-style models of software semantics, combined with neuro-symbolic AI and causal inference, can support automatic root-cause detection and reverse engineering.

## AI Assistance

This repository uses ChatGPT-5.4 Extra High for AI-assisted knowledge work.
