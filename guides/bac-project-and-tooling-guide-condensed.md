# BAC Guide Rules – Condensed Checklist for Reviewing Utils

- Source: BAC Project & Tooling Guide v0.16 (2026-10-29), BAC Interface Design Guide v1.1 (2026-10-29), BAC Identity Guide v1.3 (2026-10-29) and BAC Trademark Policy v1.2 (2026-10-29).

## Project-Wide

- License: software MIT; pyproject.toml has license = { text = "MIT" }. Hardware CERN OHL-S 2.0, mechanical parts and bac-structure included. Docs CC BY-SA 4.0, except READMEs and instructions that belong to a design, which follow its repository. Copyright line: Copyright (c) \<years\> nihil.space GmbH and Build a CubeSat contributors on the open Codeberg repositories; the GitHub repositories keep their nihil.space GmbH line; bac-ops (private) is all rights reserved.

- Legal entity: nihil.space GmbH only; never the LLC.
- Brand marks (name, BAC, cube mark, wordmark, lockup) are not openly licensed: BAC Trademark Policy. A repository that ships logo artwork says so in its README's license section.

- Software versioning: SemVer, displayed with a v prefix (bac-toolname v0.1.0). Hardware: v\<version\>r\<revision\>\[.\<patch\>\]\[-\<variant\>\]. Git tags \<tool\>-v\<X.Y.Z\> only where another repo pins the version; merge commits (git merge --no-ff), never squash, never rebase a tagged branch.

- Attribution fields: legal-entity field → nihil.space GmbH; project field → Build a CubeSat; one mixed field → Build a CubeSat by nihil.space GmbH. KiCad Company, STEP organization, 3MF Designer are entity fields; STL has none.

- Naming: "Build a CubeSat" on first reference, "BAC" thereafter, never Bac or BaC. Lowercase bac- in code and filenames; never mixed case.

- Typography: Gedankenstrich (–) only, never em dash (—). Straight apostrophes. ' thousands separator for CHF and metric, comma for USD. × not x. Decimal point. Headings numbered 1., 1.1 – no trailing period on subsections.

- Headings, titles and labels are Title Case everywhere (lowercase articles, conjunctions, short prepositions). American spelling everywhere: color, gray, behavior, license.

- The thousands separator is display only. CSV, JSON and TOML carry plain unformatted numbers.

- Axis directions use letters: Xm, Xp, Ym, Yp, Zm, Zp. Never -X or +Y. Lowercase in command-line values and file names (--face zp).

- Titles are matter-of-fact: "Power Budget Breakdown", not "Where the Watts Go".

- No emojis. Only semantic glyphs: ✓ pass, ✗ fail, ! warning, → progression, · or , separator.

- Status labels (Section 2.11): `DEVELOPMENT`, `TESTING`, `RELEASED`, `DEPRECATED`, `DO NOT USE`, `ARCHIVED`, `EXTERNAL` – uppercase words as inline code, each mapped to an Interface Guide state; never an emoji.

- Data formats: TOML for hand-edited config, CSV for tabular, JSON machine-to-machine, avoid YAML except where a framework or service requires it (Zephyr, F´, mkdocs.yml, workflow files).

- File naming for data files: {project}-{descriptor}-{YYYY-MM-DD}.{ext}; no version numbers in filenames.

- Design tokens: tokens.json in bac-utils (tools/bac-design-tokens) is the executable source of the Identity Guide's tokens, MIT or CC BY-SA 4.0. bac-design-tokens writes the gallery's and bac-suite's tokens.css, the Rich colors in bac_common.ui and every marimo style cell; never edit a generated copy, run uv run --no-sync bac-design-tokens and commit; --check fails CI on a stale copy. Other repos (BAC Ground) take a copy of the generated tokens.css.

- Repos: Codeberg primary (codeberg.org/buildacubesat-project/...); GitHub only for bac-page, CubeSat-Resources, bac-utils and bac-design (the guides).

- Time: UTC; Unix epoch machine-readable, ISO 8601 human-readable.

- Every doc about a versioned thing has a version history section. READMEs and user guides follow their subject's version, with no separate doc version; BAC-FSW-\* and BAC-SBC-\* documents keep their own versions; docs-site pages without a versioned subject take their history from git (last-updated date).

- SKUs: bac-\<cat\>-\<sub\>-\<name\>-\<versionstring\>\[-\<variant\>\], validated before API use.

## CLI Tools (Section 3)

- Python 3.11+, uv, pyproject.toml compatible with uv tool install, hatchling build backend, package bac_toolname, script bac-toolname = "bac_toolname.cli:main", minimum-pinned deps with no upper bounds.

- Stack: Rich for output; argparse for simple tools, Typer for multi-subcommand; InquirerPy for guided prompts (4 or more choices, or costly mistakes; plain \[y/N\] fine for low stakes); tomllib for config; python-dotenv for secrets.

- Standard flags: -v/--version and hidden --debug on every tool; the rest where they apply. -v/--version (non-negotiable, prints toolname v0.x.x), -l/--list where a named set exists, --env-file PATH, --dry-run (prints what would happen, labeled "dry run – no changes made"), --debug (hidden from --help, shows tracebacks), --init (first-time setup; the tool detects missing setup and points to it), --config PATH for tools with persistent settings (default ~/.config/bac/{toolname}.toml).

- Secrets: never hardcoded, .env plus python-dotenv, commit .env.example without values, .env in .gitignore.

- Filters write to stdout unless -o FILE; batch tools skip an existing output with a ! line and exit 0, --force redoes it; two inputs to one output is an error before any work.

- In-place editing tools: plan every change, show it, ask once (--yes for scripts, --dry-run stops before), keep \<file\>.bak unless --no-backup, edit by span so the diff shows only the change, leave a file that changed under the tool alone and report it.

- Errors: stderr, raise BacError or a subclass (UsageError exit 2, ConfigError, ExternalToolError) and let bac_common.cli.run print it, no tracebacks unless --debug, exit 0/1/2. Rich rendering: \[#E94538\]ERROR\[/\] Short description. plus an indented suggestion.

- --help is 24 lines or fewer at 80 columns (48 for a subcommand whose options are the tool's vocabulary), counted on Python 3.11; one-sentence description, defaults noted, 2 or 3 examples; Typer examples in the epilog behind a \b line.

- Reference implementation: bac-common in bac-utils (make_parser/run_typer, run, ui, config, testing), lib/bac-common/tests/demo_tool.py as the shape of a tool.

## Terminal Presentation (Interface Guide Section 10)

- Rich colors through bac_common.ui's generated constants: success \[#3FB950\]✓, error \[#E94538\]✗, warning \[#F7D400\]!, labels \[bold\], muted \[dim\], paths and identifiers \[cyan\]. One hex per role, tuned for dark terminals. At most three active colors per screen state; one dominant yellow.

- Liveness: anything silent for more than about 1 second shows a spinner or progress bar (rich.progress). Progress bar: task name, bar (#F7D400), one right-aligned status (x/n, or %, or elapsed). Collapse progress after completion.

- Tables: rich.table.Table, default HEAVY_HEAD; box.SIMPLE for secondary tables; numerics right-aligned; do not wrap cells.

- Panels only for the opening run summary and the final result block (Panel(..., box=SIMPLE, border_style="dim")). Rules for section dividers. Opening panel: \[bold\]bac-toolname\[/bold\] \[dim\]v0.1.0\[/dim\]\nOne-sentence description. Canonical header: Build a CubeSat – toolname v0.1.0.

- Run structure: opening panel → step log (one print per step, ✓/✗ lines) → result summary (numbers, always shown even on partial failure; dry run appends \[dim\](dry run – no changes made)\[/dim\]).

- Destructive or costly actions require explicit confirmation or before/after review.

- Terminal tools do not implement light and dark themes.

## Marimo Notebooks (Section 4)

- Stack: marimo via uv, pandas or polars, Altair primary, Matplotlib secondary, Plotly for 3D only, and pyarrow\>=15.0 in every notebook that shows a table.

- WebAssembly notebooks (molab, mkdocs-marimo on cubesat-resources.space): Pyodide's package set at Pyodide's versions only; no compiled packages outside its list, sgp4 among them; PEP 723 metadata uses minimum bounds, never ==; molab does not rewrite those bounds; 2 GB memory cap.

- Header cell is a mo.vstack of a three-paragraph intro (what it estimates and how to drive it, what to compare, links) and mo.callout(kind="warn", title="Planning Estimates Only"). No "!" intro line.

- Cell order: header, style, imports, constants, shipped profiles, profile loader (upload / parse / status, three cells), control elements, panel layout, sidebar, panel render, resolve, computation, chart conventions, headline cards, model callouts, map, charts, tables, export, assumptions and acknowledgment, revision history.

- Two constraints force the splits: a cell cannot read a UI element it defines, and mo.sidebar must be the last expression of its cell. Dataflow, not file position, sets execution order, so the export cell may read ASSUMPTIONS_MD defined below it.

- Style cell is the canonical shared text, written by bac-design-tokens (never edited by hand; notebook-specific rules go after its last line): light-dark() rather than a prefers-color-scheme media query, --heading-font set or headings fall back to Lora, --bg light-dark(#F9F9F9, \#1F1E1D), --text light-dark(#3F3F3F, \#E5E5E5), --text-muted light-dark(#6D6D6D, \#A9A8A6), Nunito Sans for headings (500) and body, IBM Plex Mono for code only, 10px callouts, no .vega-embed rule (charts render on canvas in a shadow root).

- Headings and callout titles are Title Case with lowercase articles, conjunctions and prepositions, as everywhere. Notebook copy uses American spelling.

- UI elements: show_value=True on every slider, plus include_input=True where typed entry helps; numeric controls built through clamping N()/S() helpers, since an out-of-range value takes the panel cell down; data_editor values validated (finite numbers, tolerant \_flag() for checkboxes, duplicate names skipped and reported); a control's value is unreadable in its defining cell; preset-versus-profile resolved by comparing the preset's current value with what the profile said; sidebar switch pattern; two-column panel default with accordions for rarely-touched groups; mo.ui.number shows a comma separator and cannot be overridden.

- Charts: alt.theme.enable(...), not the deprecated alt.themes.enable; width='container' does not cross alt.vconcat; downsample below Altair's 5'000-row transformer cap; a log axis dies on a 0 in the series; chart conventions live in one shared cell; the chart title carries the legend semantics; axis titles always explicit. Chart text, axes, ticks and subtitles carry no color (marimo's chart theme sets them; labelColor, titleColor, domainColor, tickColor, subtitleColor are banned by a test). PALETTE is the shared notebook palette \["#2E7ED8", "#7D7D7D", "#9D7800", "#0E903A", "#E4463E"\] and MUTED = "#A9A8A6" if IS_DARK else "#6D6D6D", both generated.

- Maps: keyed CARTO tiles as mark_image with .scale(None), mercator scale = 256·2^z/(2π), clip=True on every layer, fixed 960 × 540 px, zoom slider, tiles-off switch with the Natural Earth coastline as fallback, legends orient="bottom", chart rendered bare because mo.ui.altair_chart refuses geoshapes, credit line underneath, ground tracks split on \|Δlon\| \> 180.

- Output: six gray mo.stat(bordered=True) cards under "Headline Numbers", no direction= coloring – the callouts do the judging. Callout kinds: warn model limit or failed check, danger hard impossibility, info note, success the single all-clear. Cross-tool callouts named "X Against Y", shown only when the sibling's results table is present.

- Exports: labels "Download report (.md)", "Download profile (.toml)", "Download … (.csv)"; names bac-\<tool\>-\<qualifier\>-\<date\>.\<ext\>; report header Generated YYYY-MM-DD HH:MM UTC (Unix N) with BAC \<Tool\> \<version\>, bac.page/\<slug\>. Profile: \<name\>.; CSV never runs through fmt_int.

- Assumptions text: bold-lead paragraphs, one per model area, a Limitations paragraph, one closing line; glossary deep links on first use to https://cubesat-resources.space/references/glossary/#slug; no bullet lists.

- Tooling: marimo check --fix before every commit, marimo check as the CI lint step; headless tests via app.run() and tests/harness.py; marimo export html --no-include-code as the cheapest check that every Altair spec validates. Headless checks miss empty charts (dotted field names, layers filtered to nothing) – render specs with vl-convert once per chart change; Vega has no apostrophe thousands, use labelExpr.

- Repository layout: notebooks/bac-\<name\>/ with bac\_\<name\>.py, README.md, tests/, examples/, a pyproject.toml whose version equals TOOL_VERSION (test enforced); SPDX line first; no bac-common (not in Pyodide); exempt from -v/--help; ruff with E501, B018, F841 off. Two bac.page links per notebook, molab-\<tool\>-app and molab-\<tool\>, both reading main; a moved number is a new version with a revision row and re-recorded figures.

- Compiled models (pymsis) are evaluated offline by a PEP 723 script beside the notebook and embedded as a text table; never edited by hand; a test compares against a fresh evaluation.

## Mission Profile Contract (Section 2.7.1)

- Top level: name, tool (bac\_\<tool\>), tool_version.

- \[spacecraft\] (body, mass, drag coefficient, drag attitude as an axis: ram_x, tumbling…) and \[\[deployables\]\] are written by the lifetime notebook and read by thermal, orbit viewer and power budget; pointing directions go in the owning tool's table in letter form (nadir_zm); panels stay in the power budget's \[\[panels\]\], matched to deployables by name.

- Normative shared tables: \[orbit\] (altitude_km, inclination_deg, ltdn_hours, epoch, sim_days, min_elevation_deg), \[ground_station\] (station, latitude_deg, longitude_deg, min_elevation_deg), \[target\] (name, latitude_deg, longitude_deg), \[map\] (tiles, zoom, key).

- Results in \[results.\<tool\>\] at the end, per-row results in \[\[results.\<tool\>.modes\]\], ignored when the writing tool reloads its own file.

- A missing key keeps the loading tool's default; a tool ignores what it does not own instead of failing.

- Author detected from tool, else from a signature table (\[\[modes\]\], \[sensor\], \[storage\]). The loader status block states what was taken and what was ignored.

- Writer is hand-rolled because Pyodide has no tomli_w: escape backslash, quote, newline, carriage return and tab; unwrap numpy scalars; drop NaN and infinity; lowercase booleans; header comment as one block.

- Reader is P() with dotted sections, bool coercion, float-from-integer-default, and a profile_warnings list; PH() distinguishes absent from empty.

## Web and HTML Surfaces (Interface Guide Sections 3, 4, 5, 11)

- prefers-color-scheme by default, light when the system reports no preference (CSS cannot tell that case from light), with an optional \[data-theme\] override; test both. Inside marimo, follow marimo's own setting with light-dark() instead.

- WCAG AA contrast (--text-muted \#6D6D6D/#A9A8A6, --link \#0B5CAD/#4C9AFF, status inks on their tints), focus is a 3 px solid --focus-ring outline (\#0B5CAD/#4C9AFF) with 2 px offset and no halo, prefers-reduced-motion respected, color never the only state channel – every state is color + shape + word.

- Motion tokens: ease-standard cubic-bezier(0.2,0,0.1,1); durations 120/200/320 ms; no bounces or infinite loops.

- States: nominal green \#3FB950 filled circle, caution yellow \#F7D400 triangle, alarm red \#E94538 square, info blue \#004C8B diamond, no data/planned gray dashed hollow circle; text uses the per-theme ink (green \#1A7F37/#3FB950, red \#C9302C/#FF5A4F, info \#0B5CAD/#4C9AFF, caution \#7A5F00/#F7D400). No functional amber; \#4277FD is retired, blue means info, links and focus.

- Surfaces: --bg \#F9F9F9 light, \#1F1E1D dark; cards \#FFFFFF/#282726; wells lighter than the page in dark. Dark mode has no accent: gray primary buttons, neutral --accent-state; yellow means caution only. Light primary buttons are yellow with dark text.

- Form: pill buttons, chips and tabs with uppercase IBM Plex Mono labels at 0.03em; 6px inputs, 10px cards; no shadows, no hover lifts. Body Nunito Sans 400, headings Nunito Sans 500, every number in mono tabular figures.

- Charts: ops charts use the console plot colors (--chart-1..6, per theme; no --chart-4/-5 as plain series where the chart carries pass/fail); Mission charts the nebula triad (teal \#0E9594, violet \#7A5AF8, rose \#C64677, max three series); notebooks the shared palette.

- Icons: Lucide, inline SVG (no CDN script), 18px in icon buttons; status shapes are not icons. Containers 1200px (reading) and 1540px (dashboards). At most one info-blue hero card per view; its red rule is decorative.

- Ops versus Mission mode from the Identity Guide; controls in one region; labels on every input; units next to values.

## Blender Extensions (Section 5)

- VSE tools: bl_category = "VSE Tools"; non-VSE: bl_category = "BAC".

- UI labels Title Case, as everywhere. No abbreviations unless standard Blender, such as FPS and AVI.

- Three sub-panels: Bulk Import, Sequential Proxies, Strip Utilities. Sub-panel order is fixed: one-line layout.label description → full-width operator buttons with a built-in icon and text → property rows.

- Property names snake_case; display names Title Case with units in parentheses ("Pause (s)"); description= required on every property, a complete sentence, no trailing period.

- Destructive or long-running operators need a confirm dialog or a visible before/after indicator; long-running ones are modal timers (PASS_THROUGH, cancel(), settings in a scene property group), invoked with "INVOKE_DEFAULT".

## Shell Scripts (not explicitly covered – apply the spirit)

- Same flags where meaningful (-v/--version, --dry-run, -h), fail loudly (set -euo pipefail), errors to stderr, exit codes 0/1/2, no emojis, Gedankenstrich, version history in the header or README.
