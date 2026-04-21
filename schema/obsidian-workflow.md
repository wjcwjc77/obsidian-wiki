# Obsidian Workflow

## Canonical environment

- Vault: `wikispace`
- IDE: Obsidian
- Preferred interface for note operations: Obsidian CLI

## Linking conventions

- Use `[[note]]` for references between summaries, topics, entities, and queries.
- Use `![[note]]` when a wiki page should directly quote or transclude a source note.
- Prefer source-first grounding: each summary should point to its `raw/sources/` note.

## Ingest conventions

- Create one summary note per source.
- Add topic and entity links in every summary note.
- Use topic pages as synthesis hubs across multiple sources, especially for cross-cutting comparisons or thematic overviews.
- Use entity pages as the default home for broad, recurring conceptual buckets. Prefer stable layers that mirror the source hierarchy under `raw/sources/agent/`, rather than narrow one-off products, vendors, or project pages.
- Update `index.md` and `log.md` during every ingest pass.

## Update modes (full + incremental)

- Keep both update modes available.
- Full mode is for initialization or recovery.
- Incremental mode is the default when `wiki/` already contains meaningful pages.

Mode selection:
1. If `wiki/` has no meaningful content, run full ingest on `raw/sources/`.
2. Otherwise run incremental ingest.

### Incremental baseline

- Read the most recent `ingest` record in `log.md`.
- Infer last ingest time from that record and use it as baseline.
- If baseline cannot be inferred, fall back to one full ingest.

### Change detection

- Detect changed source files from git history since the inferred baseline time.
- Limit scope to `raw/sources/**`.
- At minimum include added and modified files; include rename/delete when relevant for link cleanup and page consistency.

### Impact mapping

For each changed source file, update only impacted pages:
- corresponding summary page(s) in `wiki/summaries/`
- related synthesis pages in `wiki/topics/`
- related concept buckets in `wiki/entities/`
- affected discoverability entries in `index.md`

### Logging (no hard-coded schema)

- Continue writing ingest entries to `log.md` in the existing human-readable style.
- Do not require rigid key names or fixed machine schema.
- Prefer entries that remain traceable for next incremental run, including:
  - source scope/files processed
  - pages updated
  - brief baseline relation note (for example, “since last ingest”)

## Commit conventions

- All commits should use the unified format `vault backup: YYYY-MM-DD HH:MM:SS`.
- Use local repository time for the timestamp.
- Do not use alternative commit subject styles unless the user explicitly asks for an exception.
