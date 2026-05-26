# Directory Layout

Keep the project layout flat until there is a concrete reason to split it.

- `AGENTS.md`: hot routing for agents.
- `README.md`: public entry point.
- `docs/`: shared process, attention-management, layout, and documentation rules.
- `skills/`: reusable workflows and protocols.
- `projects/`: project-facing maps, assumptions, decisions, risks, source notes, and improvement logs.
- `concepts/`: cross-project ideas, distinctions, models, references, and reusable frames.
- `observations/`: descriptive records of habits, recurring questions, hesitations, corrections, and framing patterns.
- `.codex-plugin/`: static Codex plugin manifest for this repository.
- `.agents/plugins/`: local marketplace routing for installing this repository as a Codex plugin.

Prefer adding files to existing buckets over creating new top-level directories.

Every new file needs a clear purpose and a retrieval path:

- documentation files should be linked from the nearest router, README section, index, or source note;
- KB files should identify their source, status, and relationship to later action when that relationship is durable;
- skills should contain reusable procedures, not one-off notes;
- static plugin metadata should route to canonical source files instead of generated copies;
- rough captures should stay in the closest existing bucket until their role is clear.

If a new file's purpose cannot be stated in one sentence, do not add it yet.

Do not add subdirectory `AGENTS.md` files preemptively. Reconsider them only after repeated directory-specific mistakes show that root routing plus focused docs and skills are not selective enough.
