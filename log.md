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
