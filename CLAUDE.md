# LLM Wiki Schema

## Purpose

This repository is a persistent wiki maintained by the LLM.

There are three layers:
- `raw/`: immutable source documents and assets
- `wiki/`: LLM-maintained knowledge pages
- `schema/`: supporting conventions and templates

## Obsidian workflow

- Obsidian is the canonical IDE for this repository.
- Create, update, move, and inspect notes through the Obsidian CLI whenever possible.
- Prefer Obsidian links and embeds to connect notes:
  - use `[[note]]` for references
  - use `![[note]]` for transclusion when quoting or grounding a page in source material
- Summary and topic pages should link back to source notes under `raw/sources/` and use embeds when a direct source transclusion is useful.
- Treat the graph view and backlinks as part of the knowledge system, not just presentation.

## Directory responsibilities

- `raw/sources/`: original source materials; treat as read-only
- `raw/assets/`: downloaded images, PDFs, and attachments referenced by sources
- `wiki/summaries/`: one summary page per source
- `wiki/topics/`: synthesis pages, cross-cutting analyses, and thematic overviews that connect multiple entities or sources
- `wiki/entities/`: pages for broad, stable conceptual buckets and organizing concepts. Use `wiki/entities/` as the default home for durable layers reflected in the source hierarchy (especially the folder structure under `raw/sources/agent/`), and avoid using it for narrow one-off products, vendors, or project pages.
- `wiki/queries/`: durable outputs produced from valuable user questions
- `schema/`: optional supporting templates or operational notes

## Ground rules

- Never modify files under `raw/` except when the user explicitly adds new source material.
- Prefer updating existing pages in `wiki/` over creating duplicate pages.
- Add links between related pages whenever a meaningful connection exists.
- When new evidence contradicts an older claim, update the relevant wiki pages and note the conflict clearly.
- Keep the wiki in markdown.
- Commits should follow the unified format `vault backup: YYYY-MM-DD HH:MM:SS`.

## Core workflows

### Ingest

When processing a new source:
1. Read the source from `raw/sources/`.
2. Create or update a matching page in `wiki/summaries/`.
3. Add links to related `wiki/topics/` and `wiki/entities/` pages.
4. Include an Obsidian source reference and, when useful, an embed from the source note.
5. Update affected pages in `wiki/topics/` and `wiki/entities/`.
6. Update `index.md` so the new or changed pages are discoverable.
7. Append an entry to `log.md`.

### Query

When answering a question:
1. Read `index.md` first to find likely relevant pages.
2. Read the relevant wiki pages.
3. Answer using the wiki plus raw sources when needed.
4. If the answer is durable and broadly useful, save it to `wiki/queries/` and update `index.md`.
5. Prefer Obsidian links so the answer becomes part of the graph.

### Lint

Periodically check for:
- orphan pages with no useful links
- stale claims superseded by newer sources
- contradictions across pages
- important concepts or entities that lack dedicated pages
- missing cross-references
- summary pages that do not point back to source notes

## Naming guidance

- Use concise, stable markdown file names.
- Prefer lowercase kebab-case file names.
- Keep one durable concept per page where practical.

## Required root files

- `index.md`: content-oriented navigation for the wiki
- `log.md`: append-only chronological activity log
