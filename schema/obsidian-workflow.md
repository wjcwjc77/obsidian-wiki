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
