# Log

Use one entry per operation.

Format:

## [YYYY-MM-DD] ingest | Title
- Source:
- Updated pages:
- Notes:

## [YYYY-MM-DD] query | Question or title
- Pages read:
- Output:
- Notes:

## [YYYY-MM-DD] lint | Scope
- Findings:
- Actions:

## [2026-04-11] ingest | Initial corpus ingest
- Source: `raw/sources/`
- Updated pages: `CLAUDE.md`, `schema/obsidian-workflow.md`, `wiki/summaries/*`, `wiki/topics/*`, `wiki/entities/*`, `wiki/queries/initial-corpus-overview.md`, `index.md`
- Notes: First ingest pass created summary notes for the current corpus, added topic and entity hubs, and adopted an Obsidian CLI plus reference/embed workflow.

## [2026-04-11] ingest | Refactor entity taxonomy around source hierarchy
- Source: `raw/sources/agent/`, `raw/sources/tools/`, `raw/sources/models/`
- Updated pages: `CLAUDE.md`, `schema/obsidian-workflow.md`, `wiki/entities/*`, affected `wiki/topics/*`, affected `wiki/summaries/*`, `index.md`
- Notes: Reworked `wiki/entities/` into broad concept buckets aligned with the major source layers, replaced narrow project-style entity links with concept-level entities, and clarified the entity/topic split in the rules.

## [2026-04-21] ingest | Incremental ingest from last log baseline
- Source: Changed files under `raw/sources/**` since last ingest (including `agent/engnieering/*`, `agent/skills/*`, `agent/hermes*`, `blogs/*`, `investment/fincept-terminal.md`, `models/trainning/*`, `tools/claude design.md`).
- Updated pages: new `wiki/summaries/*` for changed sources, updated `wiki/topics/managed-agents.md`, `wiki/topics/agent-harness-engineering.md`, `wiki/topics/agent-skills-and-domain-packs.md`, `wiki/topics/deep-research-and-autoresearch.md`, new `wiki/topics/small-models-and-tools.md`, updated `wiki/entities/*` (agent-engineering, agent-harness, agent-skills, deep-research, models, tools), `index.md`.
- Notes: Used incremental mode (read `log.md` baseline date -> git history diff for `raw/sources/**` -> update impacted summary/topic/entity/index pages). Kept human-readable log format without rigid field schema.
