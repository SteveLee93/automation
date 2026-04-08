# AGENTS.md

## Scope
This file is the repository-level guide for agentic coding agents working in `C:\Users\RobotSW\Documents\develop\automation`.

This repository is a Markdown-first growth research workspace, not a conventional application codebase. The main work product is structured Markdown under `growth-projects/`, with shared rules in `growth-projects/shared/` and source-specific rules in each project folder.

Before changing anything, read this file together with:
- `PROJECT_OPERATING_GUIDE.md`
- `README.md`
- `growth-projects/shared/AGENTS.md`
- `growth-projects/shared/config/naming_rules.md`
- `growth-projects/shared/docs/output_rules.md`

Then read the local `AGENTS.md` for the project you are editing:
- `growth-projects/x-growth-os/AGENTS.md`
- `growth-projects/news-growth-os/AGENTS.md`
- `growth-projects/youtube-growth-os/AGENTS.md`
- `growth-projects/integrated-growth-os/AGENTS.md`

## Repository shape
The workspace is organized around separate source-specific projects plus a shared rules layer.

- `growth-projects/shared/`: common rules, naming, templates, scoring, categories, output rules
- `growth-projects/x-growth-os/`: X-based collection and analysis
- `growth-projects/news-growth-os/`: news-based collection and analysis
- `growth-projects/youtube-growth-os/`: YouTube-based collection and analysis
- `growth-projects/integrated-growth-os/`: cross-source integrated analysis and handoff

Representative outputs confirm the dominant pattern in this repo:
- `growth-projects/x-growth-os/data/processed/<DATE>/08_collection.md`
- `growth-projects/news-growth-os/data/processed/<DATE>/08_news_collection.md`
- `growth-projects/youtube-growth-os/data/processed/<DATE>/08_youtube_collection.md`
- `growth-projects/integrated-growth-os/data/outputs/<DATE>/21_integrated_analysis.md`
- `growth-projects/integrated-growth-os/data/outputs/<DATE>/22_close_handoff.md`

## Tooling reality: build, lint, test
There is currently no evidence of a conventional build, lint, or automated test toolchain in this repository.

Observed facts:
- no root `package.json`
- no `pyproject.toml`
- no `pytest.ini`
- no `tox.ini`
- no `tsconfig*.json`
- no ESLint, Prettier, Biome, Jest, Vitest, or Playwright config
- no `.github/copilot-instructions.md`
- no `.cursor/rules/` and no `.cursorrules`

Because of that, do **not** invent commands like `npm test`, `pnpm lint`, `pytest`, or `npm run build` unless those files are added later and verified in the repo.

### Current command guidance
- Build: not configured in this repository
- Lint: not configured in this repository
- Test: not configured in this repository
- Single test: unavailable because no test runner is configured in the repository

### What to run instead
When validating changes, use the closest truthful checks available:
- read the affected Markdown files and confirm sections, headings, and filenames match existing patterns
- check neighboring files in the same project/date folder for consistency
- verify names against `growth-projects/shared/config/naming_rules.md`
- verify output structure against `growth-projects/shared/docs/output_rules.md`
- if you change project instructions, cross-check the relevant project `AGENTS.md`

For repository hygiene, basic git inspection is still valid:
- `git status`
- `git diff`

Do not present these as build or test commands. They are only change-review commands.

## Primary style: Markdown-first, structured, explicit
The dominant “code style” in this repo is document structure, naming discipline, and metadata completeness.

Follow these rules consistently:
1. All durable outputs are Markdown.
2. Put a clear title at the top using a level-1 heading.
3. Start documents with compact metadata bullets.
4. Keep section names explicit and scannable.
5. End collection/analysis artifacts with summary-style sections, diagnostics, or action notes when the surrounding pattern uses them.

This is visible in current outputs such as:
- `growth-projects/x-growth-os/data/processed/2026-04-07/08_collection.md`
- `growth-projects/news-growth-os/data/processed/2026-04-07/08_news_collection.md`
- `growth-projects/youtube-growth-os/data/processed/2026-04-07/08_youtube_collection.md`
- `growth-projects/integrated-growth-os/data/outputs/2026-04-07/21_integrated_analysis.md`

## Naming conventions
File naming is strict and should be treated as part of the interface. Use `growth-projects/shared/config/naming_rules.md` as the source of truth.

Key patterns already established:
- dates use `YYYY-MM-DD`
- time slots use `HH`
- raw files include time and source, such as `11_collection_raw.md` or `13_news_raw.md`
- processed morning collection files use stable names like `08_collection.md`, `08_news_collection.md`, `08_youtube_collection.md`
- integrated outputs use fixed milestone names like `12_integrated_analysis_am.md`, `21_integrated_analysis.md`, `22_close_handoff.md`
- candidate files use stable names like `08_watch_account_candidates.md`, `08_source_candidates.md`, `08_channel_candidates.md`

Do not rename files casually. If a file naming change is required, update related references and preserve the source/project distinction.

## Source-of-truth hierarchy
When rules conflict, prefer the more specific file:
1. task-specific prompt or local project document being edited
2. project-local `AGENTS.md`
3. `growth-projects/shared/AGENTS.md`
4. shared config/docs such as naming, scoring, categories, and output rules
5. root-level orientation docs like `PROJECT_OPERATING_GUIDE.md`

## Project-specific working model
Keep the role separation intact.

- X project: fast signal capture, account/keyword-driven collection, reaction surface
- News project: fact confirmation, source credibility, regional context
- YouTube project: explanation depth, channel credibility, learning value
- Integrated project: cross-confirmation, clustering, final judgment, next actions

Do not blur these responsibilities when editing prompts, AGENTS files, or output templates.

## Formatting guidelines
### Headings
- use one `#` title per file
- use `##` for major sections
- use `###` for repeated item blocks when the existing file uses that pattern
- keep headings descriptive, not cute

### Metadata bullets
Most output files begin with short metadata bullets immediately after the title. Preserve that style.

Common metadata fields seen in the repo include:
- execution or authoring time
- date
- input sources
- applied time range
- total counts
- importance/trust distributions
- collection path distributions
- rerun/raw usage notes

### Lists
- prefer `- ` bullets
- keep one fact per bullet where possible
- use consistent label formatting like `- 시각:` or `- 카테고리:` inside repeated item blocks
- preserve Korean labels when editing existing Korean-language documents

## Language and tone
Most repository documents are written in Korean, with selective English technical terms and English section titles where already established. Match the local file’s language.

- if the file is Korean-first, keep it Korean-first
- if a template already uses English headings like `Quick Notes` or `Action Notes`, preserve them
- do not rewrite documents into a different language unless the task explicitly requires it

## “Code style” guidance for actual code additions
There is little to no established JS/TS/Python source code in the current repository. That means there is **no grounded repo convention** yet for imports, module layout, or type systems.

So:
- do not claim there is an established import order if no code exists
- do not claim there is a formatter or linter if none is configured
- do not claim there is a test framework if none is configured

If you must add automation code later:
- keep it isolated and clearly named
- document the runtime and invocation in README or adjacent docs
- avoid introducing multiple runtimes at once
- prefer explicit errors over silent failure
- avoid hidden side effects on existing Markdown data

## Error handling and safety expectations
Even in a Markdown-first repo, changes can still damage operating flow.

- do not silently change file naming schemes
- do not remove required sections like Diagnostics, Quick Notes, Growth Notes, or Action Notes when neighboring files expect them
- do not collapse source-specific distinctions
- do not replace structured bullets with loose prose if the file family is structured
- when a rerun or snapshot condition matters, keep that note explicit

If something is unknown, say it is unknown instead of fabricating a value.

## How to edit safely
Before editing:
1. read the nearest equivalent file in the same folder family
2. read the relevant shared rule file
3. preserve existing section order unless the task explicitly changes structure
4. preserve filename semantics and date-folder placement

When editing:
1. make the smallest change that satisfies the request
2. preserve metadata bullets and section labels
3. maintain existing terminology across sibling files
4. keep outputs easy to scan in 1–3 minutes

After editing:
1. re-read the changed file
2. compare against neighboring examples
3. confirm that names, headings, and required sections still match repo patterns

## Agent expectations for this repository
Agents operating here should optimize for correctness of structure and operating continuity, not for framework cleverness.

Good behavior in this repo means:
- respecting shared rules before making local changes
- keeping Markdown outputs structurally consistent
- preserving the source-role separation across projects
- being explicit when no automated validation exists
- not hallucinating missing tooling or workflow files

## Cursor / Copilot rule files
As of this analysis, no repository Cursor or Copilot instruction files were found:
- no `.cursor/rules/`
- no `.cursorrules`
- no `.github/copilot-instructions.md`

If those files are added later, update this document so the repository-level guidance references them explicitly.
