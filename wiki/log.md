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

## [2026-11-22] schema | AGENTS.md v0.3: thesis language, attachment folder
- Thesis language: technical terms in English, some explanations in Chinese (§5.1). Wiki page format unchanged.
- Obsidian attachment folder set to raw/assets.
- Still open: search tool (qmd) at ~100 sources; private remote backup.

## [2026-11-22] brake | B3: 26-page PDF read in full
- `2511.03282v1.pdf` was loaded whole while trying to read only its abstract; the PDF reader cannot read page ranges without poppler.
- The other three PDFs were checked with metadata and a text sample only.

## [2026-11-22] lint | Coverage check of the first 4 sources
- Report: [[2026-11-22-coverage]]. No source pages written.
- No step or RQ meets M2. Biggest skew: no source on changing the appearance of real objects.
- Three schema changes proposed (book evidence level, second-hand claims, PDF tool for B3); not applied.

## [2026-11-22] schema | AGENTS.md v0.4: read PDFs by page range
- Poppler 26.09.0 installed with winget. §6.2 now reads PDFs with `pdfinfo` (page count) and `pdftotext -f -l` (page range), so B3 can be followed.
- Resolves proposal 3 of [[2026-11-22-coverage]]. Proposals 1 and 2 still open.

## [2026-11-22] batch | batch-1: ingest 4 sources
- Sources: [[2025-ning-genai-xr-review]] (full), [[2024-pan-ctgan]] (full), [[2021-itoh-ost-hmd-survey]] (partial, B3), [[2025-scrivener-intro-xr-book]] (contents only, B3).
- New concept: [[optical-vs-video-see-through]]. Updated hubs: step-2 to step-6, rq1 to rq3; overview, index.
- 18 wiki pages touched (limit 30). External lookups: 0. All sources `review: pending`.
- Review list: [[2026-11-22-batch-1]].

## [2026-11-22] review | approve batch-1
- All four batch-1 sources set to `review: approved`.
- Gap sections written in step-2 to step-6 and rq1 to rq3, and overview "Current position" written; each states how many sources back it and says "no gap statement yet" where evidence is thin.
- Still open: `book` evidence level, `secondhand` flag, reading Itoh §6.1/§6.3, CTGAN venue lookup.

## [2026-11-22] batch | batch-2: ingest 4 sources
- Discussed first: user placed the Priority 1 papers from [[2026-11-22-coverage]] plus Thing2Reality, then said "ingest batch-2".
- Sources: [[2001-raskar-shader-lamps]], [[2018-lindlbauer-remixed-reality]], [[2017-mori-diminished-reality-survey]], [[2025-hu-thing2reality]]. All under 20 pages; read by section with `pdftotext`, so each is `partial` (method details and study results skipped).
- New concepts: [[appearance-editing-of-real-objects]], [[diminished-reality]]. Updated: [[optical-vs-video-see-through]], all 6 pipeline hubs, 3 RQ hubs, overview, index.
- 20 wiki pages touched (limit 30). External lookups: 0. Gap sections unchanged (new sources pending).
- Review list: [[2026-11-22-batch-2]].

## [2026-11-22] review | approve batch-2
- Batch-2 sources set to `review: approved`; "(pending)" markers removed from hubs and overview.
- Gap sections rewritten with 8 approved sources: step-1 "not a gap"; step-3, step-4, rq1, rq2 now carry tentative gap statements with source counts; step-2, step-6 still "not established".
- Overview "Current position" now states the core gap tentatively: real-object appearance editing uses authored appearance, generative AI in XR makes virtual content; no source does both in place. Next check: targeted search for AR stylization.
