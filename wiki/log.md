---
type: log
updated: 2026-11-22
---

# Log

Append-only. Each entry starts with `## [YYYY-MM-DD] type | title`.
Types: ingest, batch, query, lint, review, brake, schema.
Last 5 entries: `grep "^## \[" wiki/log.md | tail -5`

## [2026-11-22] schema | AGENTS.md v0.1 created
- Raw sources: papers and technical articles, platform and market news. Own project records, experiment data, and meeting notes are excluded.
- Brakes: conservative (15 pages per ingest, 30 per batch, PDF over 20 pages read partially, 3 external lookups per session, no subagents unless asked).
- Ingest: batches of up to 5, reviewed afterwards; pending sources cannot support overview positions or RQ gaps.
- Language: English first, then a short 中文說明 section.
- Skeleton created: index, log, overview, 6 pipeline hubs, 3 RQ hubs, templates (source, concept, entity).

## [2026-11-22] schema | AGENTS.md v0.2: git
- Folder is now a git repo (branch main). One commit per write operation; a rejected batch is undone with `git revert` after approval (§6.6, C9).
- PDFs, raw/assets/, and Obsidian window state are not tracked (.gitignore).
