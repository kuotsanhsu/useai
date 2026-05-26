---
name: useai-plugin-maintenance
description: Maintain this repository as a static Codex plugin. Use when Codex should update plugin metadata, marketplace routing, plugin-facing skills, or repo-as-plugin documentation without generating copied plugin artifacts.
---

# Useai Plugin Maintenance

Use this skill to maintain the repository as a static Codex plugin.

The source of truth is the repository root. The plugin is not generated. Codex installs this checkout directly through `.agents/plugins/marketplace.json`, then loads skills from `skills/` through `.codex-plugin/plugin.json`.

## Core Rules

- Keep target projects free of absolute paths back to this repository.
- Put reusable workflows in `skills/`.
- Put detailed reusable knowledge in `concepts/` or `docs/`.
- Keep project-specific truth in the target project.
- Do not copy source notes into `plugins/` as generated references.
- After plugin-facing changes, validate the static plugin instead of running a generator.

## Workflow

1. Edit source material in this repository.
   - General reusable procedures belong in `skills/`.
   - Cross-project concepts belong in `concepts/`.
   - Shared process guidance belongs in `docs/`.

2. Update static plugin routing when the install shape changes.
   - Plugin manifest: `.codex-plugin/plugin.json`
   - Install metadata: `.agents/plugins/marketplace.json`
   - Skill metadata: `skills/*/SKILL.md` and `skills/*/agents/openai.yaml`

3. Validate the plugin manifest and repository hygiene:

```sh
python3 -m json.tool .codex-plugin/plugin.json
python3 -m json.tool .agents/plugins/marketplace.json
git diff --check
```

4. If the Codex plugin-creator validator is available in the current environment, run it against the repo root:

```sh
python3 "$CODEX_HOME/skills/.system/plugin-creator/scripts/validate_plugin.py" .
```

## Editing Guidance

- Prefer making source skills portable enough to work both in this repo and in target projects.
- If a skill references concepts or docs, use repo-relative paths from the skill file, such as `../../concepts/name.md`.
- If a target-project use case needs project facts, do not add those facts to this plugin. Add them to the target project.
- If a concept should be available to plugin users, link it from `concepts/README.md` and the relevant skill references.

## Closeout

Mention whether the static plugin manifest and marketplace routing were changed, and whether validation passed. If source skills or concepts changed, mention which skill or concept now exposes the behavior.
