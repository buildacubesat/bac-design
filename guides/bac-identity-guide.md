# BAC Identity Guide

**Build a CubeSat – Brand, visual & communication standard** Version 1.4, 2026-10-30

> **Space for everyone.** This guide is the authoritative source for the Build a CubeSat (BAC) identity: brand usage, voice and tone, typography, color, form, imagery, graphic language, and the Ops/Mission communication modes. It is written so a human or an LLM can reproduce BAC's identity without a visual reference.
>
> **Relationship to the other BAC guides.** The guides live at https://github.com/buildacubesat/bac-design. The **BAC Interface Design Guide** is authoritative for how BAC interfaces communicate and behave: interaction states, motion, components, accessibility, data visualization, terminal presentation, and physical indicators. The **BAC Project & Tooling Guide** is authoritative for engineering and implementation conventions: licensing, versioning, repositories, data formats, SKUs, CLI implementation, configuration and secrets, Marimo structure, and Blender extensions. This Identity Guide is upstream of both for canonical brand tokens and communication modes. If rules appear to overlap, identity values come from this guide, interface behavior from the Interface Design Guide, and implementation/project behavior from the Project & Tooling Guide. The **BAC Trademark Policy** governs how others may use the BAC name and marks; this guide defines how they look.
>
> **Reference implementation.** Since 1.0 the visual language follows the BAC Ground mission-operations console. The executable copy of every token in this guide is `tokens.json` in bac-utils (§9); where this guide and that file disagree, fix whichever is wrong in the same change.

## 0. What This Is, in One Paragraph

Build a CubeSat is an open-source CubeSat platform (hardware kits, flight software, a ground segment, a storefront, and internal tools) run by a founder in Bern, Switzerland. The design language is **calm, structural, and engineering-grade**: neutral gray surfaces in light mode and slightly warm near-black surfaces in dark mode (never cold blue-gray), a light sans-serif for headings and prose, a monospace reserved for labels, figures and code, pill-shaped controls on softly rounded cards, no drop shadows, and one bold yellow that is the light-mode action color and the caution color everywhere. Status always speaks in color, shape and word together. It should read *utilitarian but not corporate, futuristic but not fantasy – science-forward with restrained sci-fi cues.* A small three-color **nebula** palette and a dark **Mission** identity mode exist for outward-facing and presentation-led communication; the restrained **Ops** mode serves technical and operational communication. The voice is plain-spoken and honest – a careful engineer who ships the caveats.

## 1. Brand & Product Context

- **Brand name:** *Build a CubeSat* on first reference; **BAC** thereafter (always fully capitalized). Lowercase bac is fine in code, filenames, SKUs. Never "buildacubesat" as a display name. The name, the abbreviation and the logo are **BAC Marks**: they are not open source and are excluded from the project's open licenses; their use by others follows the BAC Trademark Policy.

- **Legal entity:** nihil.space GmbH, Bern, Switzerland.

- **Mission:** spaceworthy CubeSat hardware and software anyone can build, study, and extend.

- **Timeline (historical, as of 2026-07):** 2020 project start → 2024 YouTube devlog → 2025 first suborbital test. Treat this as a dated snapshot; live company and product status, release dates included, belongs outside this spec.

**Surfaces this system covers**

| **Surface** | **What it is** |
|----|----|
| Storefront | buildacubesat.space – Shopify store (hero, founder story, merch, devlog, open-source, newsletter). Light + dark. |
| BAC Ground | The mission-operations console – overview, command, telemetry, plots, events, passes. Light + dark. The reference implementation of this guide's visual language. |
| Internal pricing tool and engineering notebooks | Marimo notebooks – BOM cost rollup, link, power and orbit budgets, charts, tables. Structure and conventions per the Project & Tooling Guide §4. |
| Product sheet | Dev Kit v1 – one-page printable spec sheet. |
| CLI tools & Blender extensions | Terminal apps (Rich) + VSE add-ons. Their implementation is specified in the Project & Tooling Guide; their interface behavior is specified in the Interface Design Guide; this guide supplies the identity layer. |

**Catalog:** Dev Kit v1 (2U dev kit), Education Kit v1, EPS v2, plus merch (Galaxy Tee, Remove-Before-Flight keychain, holographic stickers). Product codes follow the SKU scheme in the Project & Tooling Guide §2.9.

## 2. Voice & Tone (Content Fundamentals)

The voice is **plain-spoken, technical, and honest.** Never marketing hype, never corporate.

- **Person.** First person for the founder's story (*"In 2020 I set out to learn everything…"*); second person for the reader (*"Bring your own CM5…"*). Direct address; no "we are pleased to announce."

- **Casing.** Title Case for headings, titles and labels (*"This Project Is Open Source"*), with articles, conjunctions and short prepositions lowercase; sentence case for prose. **UPPERCASE mono** only for micro-labels, eyebrows, nav, chips and button labels (· ABOUT, INCLUDED, STRUCTURE & POWER, SAVE) and for status labels (Project & Tooling Guide §2.11). The rule holds everywhere – guides, READMEs, the docs site, Blender panels, notebooks (decided 2026-10-24).

- **Spelling.** American English everywhere: color, gray, behavior, license, center.

- **Honesty over polish.** Ship the caveats: *"(WIP)"*, *"TBD"*, *"currently in development"*, *"PRELIMINARY DRAFT"*, *"These contribute zero cost – the rollup is a lower bound."* The rule: **fail loudly, succeed quietly.**

- **Technical specificity.** Exact part numbers and units (TI TPSM5D1806, STM32F405, 100×100×227 mm ±0.5, 2S2P, 12'059 CHF). Numbers are tabular and precise.

- **Numbers & currency.** Period as the decimal separator. Thousands separator: straight apostrophe ' for CHF and metric values (Swiss style: 1'230 CHF, 12'059 CHF, 1'137.74 CHF); comma for USD prices (American style: \$1,517). (Technical notation application is mirrored in the Project & Tooling Guide §2.6.)

- **No emoji, ever.** Symbols carry meaning only: ✓ pass, ✗ fail, ! warning, → progression, , or · separator.

- **Glyphs & punctuation.**

  - × for quantities/formulas (2× INA260, 100×100×227 mm) – never lowercase "x".

  - , or · as a separator (v0.5.0, 2026-06-16).

  - **Never the em dash (—).** Use the en dash – (the *Gedankenstrich*) for parenthetical breaks and ranges.

  - Ligatures encouraged (leave font-feature-settings at defaults).

- **Vibe.** Open, generous, community-minded ("Space for everyone", CC BY-SA), grounded in real hardware. Quietly enthusiastic, never breathless.

**Copy examples to emulate**

- Headline: *Space for everyone*

- Subhead: *Build a CubeSat is an open-source CubeSat kit – currently in development!*

- Eyebrow: *· OSHW*

- Tool subtitle: *Multi-level BOM cost rollup and price derivation, v0.5.0, 2026-06-16*

- Disclaimer: *! Development, education & ground testing only. Not flight-qualified.*

## 3. Typography

Three families, each with one job. No serifs anywhere.

| **Role** | **Family** | **Token** | **Used for** |
|----|----|----|----|
| Wordmark | **Nunito** (rounded humanist) at weight 350, uppercase | --font-logo | The logo/wordmark **only**, and only as the outlined files in bac-design `assets/` (§8) |
| Headings | **Nunito Sans** 500 | --font-display, --fw-heading | UI and document headings, display type |
| Body | **Nunito Sans** 400 | --font-body | Prose, descriptions, table text, marketing copy |
| Mono | **IBM Plex Mono** 400/500 | --font-mono | Labels, eyebrows, chips, button labels, figures, units, identifiers, timestamps, code |

- **Headings are light.** Nunito Sans at 500, not bold. Display headings take tight tracking (--ls-tight, -0.02em).

- **Body is sans.** Prose is never set in mono. The monospaced body of the 0.x guides is retired.

- **Mono is for labels and figures.** Every number, unit, timestamp, identifier and code fragment is IBM Plex Mono with tabular figures (font-variant-numeric: tabular-nums), so columns line up and values read as data. Uppercase mono labels, eyebrows, chips and button labels take **--ls-label, 0.03em** – tight, not spaced-out.

- *Moon 2.0 is fully retired* (the legacy wordmark face). Do not reintroduce it. The Space Mono "future option" of the 0.x guides is dropped: mono no longer carries body text, and Plex Mono's tabular figures matter more than a typewriter character.

```css
:root {
  /* Families */
  --font-logo:    'Nunito', system-ui, sans-serif;         /* wordmark only */
  --font-display: 'Nunito Sans', system-ui, sans-serif;    /* headings */
  --font-body:    'Nunito Sans', system-ui, sans-serif;    /* prose */
  --font-mono:    'IBM Plex Mono', ui-monospace, 'SF Mono', Menlo, monospace;

  /* Weights */
  --fw-light: 300; --fw-regular: 400; --fw-medium: 500; --fw-semibold: 600; --fw-bold: 700;
  --fw-heading: 500;

  /* Type scale (rem; 1rem = 16px) */
  --text-2xs: 0.6875rem;  /* 11px – micro labels, table sublabels */
  --text-xs:  0.75rem;    /* 12px – captions, meta, eyebrow */
  --text-sm:  0.8125rem;  /* 13px – dense UI, secondary body */
  --text-base: 0.9375rem; /* 15px – body default */
  --text-md:  1.0625rem;  /* 17px – lead paragraph */
  --text-lg:  1.375rem;   /* 22px – h4 / card title */
  --text-xl:  1.75rem;    /* 28px – h3 */
  --text-2xl: 2.25rem;    /* 36px – h2 */
  --text-3xl: 3rem;       /* 48px – h1 */
  --text-4xl: 4rem;       /* 64px – display */
  --text-5xl: 5.5rem;     /* 88px – hero display */

  /* Line heights */
  --lh-tight: 1.05; --lh-snug: 1.2; --lh-normal: 1.45; --lh-relaxed: 1.65;

  /* Tracking */
  --ls-tight: -0.02em;  /* display headings */
  --ls-normal: 0;
  --ls-label: 0.03em;   /* uppercase mono labels, eyebrows, chips, buttons */
}
```

Fonts load from Google Fonts (cached offline after first load); surfaces that must work offline self-host the same files from bac-design `fonts/` (variable Nunito and Nunito Sans, the five static IBM Plex Mono faces, OFL 1.1). The wordmark's weight 350 is served by the variable file only, so it is included in the import for completeness and the wordmark is never set live:

```css
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@350;400;500;600;700;800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:ital,opsz,wght@0,6..12,400;0,6..12,500;0,6..12,600;0,6..12,700;1,6..12,400&display=swap');
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap');
```

## 4. Color

Color comes in **two layers**: a *functional* palette (neutral surfaces plus the status set, used everywhere) and a three-color *nebula* palette (Mission and marketing only). Light mode uses neutral grays; dark mode uses near-blacks with a slight warm cast. **Never a blue-gray neutral.**

### 4.1 Brand & Status (Constant Across Light/Dark)

| **Token** | **Hex** | **Meaning** |
|----|----|----|
| --bac-yellow | \#F7D400 | Brand yellow. Light-mode primary action and current selection; the caution color in both modes |
| --bac-yellow-press | \#EED228 | Pressed/hover yellow |
| --bac-green | \#3FB950 | Nominal / pass / healthy |
| --bac-red | \#E94538 | Alarm / fail / fault |
| --bac-blue | \#004C8B | Info – the info status fill and the hero-card surface |
| --bac-blue-press | \#0B5CAD | Darker info blue – light-mode links, focus ring, info ink |

**Fill and ink.** Each status has a *fill* (the hex above, for dots, bars, badges and filled shapes) and an *ink* for text, tuned per theme so it meets WCAG AA (§4.4): green \#1A7F37 / \#3FB950, alarm \#C9302C / \#FF5A4F, info \#0B5CAD / \#4C9AFF, caution \#7A5F00 / \#F7D400 (light / dark).

**Blue means information.** Blue has exactly one family and one meaning: info status, links and focus. The bright \#4277FD "secondary accent" of the 0.x guides is retired – it failed AA as text in both modes and as a surface for white text, and would have been a second brand blue between info blue and Ion Violet.

**Yellow.** In light mode BAC Yellow is the primary action and selection color *and* the caution color. In dark mode it is the **caution color only**: primary buttons are gray and state marks are neutral (the Interface Design Guide §3). Functional warnings always use BAC Yellow with dark text on filled surfaces; there is no separate amber token. The small yellow **kicker** bar before eyebrows (--kicker) is a brand mark and stays in both modes.

**"One dominant use" means one visually dominant yellow surface or action per screen state.** Multiple small semantic uses may coexist when they carry real meaning – for example a primary yellow action alongside caution badges or status markers. The rule prevents competing large yellow focal points; it does not suppress legitimate semantic indicators.

### 4.2 Nebula Palette – Mission and Marketing

Three emission-line colors with clear hue distance from each other and from the status set. Use **only in the Mission mode, marketing and presentation charts** – never in Ops interfaces or ops charts (those use the console plot colors, the Interface Design Guide §8).

| **Token** | **Fill** | **Name** | **Text on paper / white / tint** | **Text on ink / space surface** | **Tint** |
|----|----|----|----|----|----|
| --nebula-teal | \#0E9594 | Orbital Teal | --mission-teal-ink \#007878 | --mission-teal-on-dark \#1A9A99 | --nebula-teal-tint \#E1F3F2 |
| --nebula-violet | \#7A5AF8 | Ion Violet | --mission-violet-ink \#6E4BE8 | --mission-violet-on-dark \#8F73FF | --nebula-violet-tint \#ECEBFF |
| --nebula-rose | \#C64677 | Plasma Rose | --mission-rose-ink \#B8396B | --mission-rose-on-dark \#DE5C8C | --nebula-rose-tint \#FFE7ED |

- The three fills sit at the same perceived lightness, so no series dominates. As chart marks they reach 3.2–4.1:1 on Mission paper and 3.9–5.0:1 on --space-ink; text always uses the ink or on-dark variant, which meets 4.5:1.

- **No fourth color.** Beyond three series, fall back to neutrals and tints.

- Orbital Cyan, Ion Blue, Solar Copper, Deep Field Violet and Nebula Ember are retired (they crowded together or sat too close to status colors). Plasma Rose takes Solar Copper's Mission job (§4.5).

### 4.3 Neutral Ramp

The light family, taken from the BAC Ground console. Dark-mode surfaces are listed with the semantic tokens (§4.4).

```css
:root {
  --neutral-0:   #FFFFFF;
  --neutral-50:  #F9F9F9; /* light page background */
  --neutral-100: #F1F1F1;
  --neutral-200: #E6E6E6;
  --neutral-300: #D0D0D0;
  --neutral-400: #A9A9A9;
  --neutral-500: #8A8A8A;
  --neutral-600: #6D6D6D; /* light muted text */
  --neutral-700: #4F4F4F;
  --neutral-800: #3F3F3F; /* light body text */
  --neutral-900: #282828;
  --neutral-950: #1F1F1F;
}
```

### 4.4 Semantic Tokens (Light Default → Dark Override)

Brand, status and nebula fills are identical across modes; neutrals, surfaces, inks, tints and the chart series change. The **BAC Interface Design Guide** defines when and how light/dark modes switch; the **BAC Project & Tooling Guide** covers the generated copies for Marimo and Rich.

| **Token** | **Light** | **Dark** | **Role** |
|----|----|----|----|
| --bg | \#F9F9F9 | \#1F1E1D | Page background |
| --bg-raised | \#FFFFFF | \#232221 | Bars, raised strips |
| --surface-card | \#FFFFFF | \#282726 | Cards, panels |
| --surface-sunken | \#F1F1F1 | \#2F2E2D | Wells, inputs idle (lighter than --bg in dark) |
| --surface-hover | \#E6E6E6 | \#353433 | Hover tint, gray buttons |
| --text | \#3F3F3F | \#E5E5E5 | Primary text |
| --text-strong | \#1F1F1F | \#FFFFFF | Headings, emphasis |
| --text-muted | \#6D6D6D | \#A9A8A6 | Secondary text |
| --text-faint | \#8A8A8A | \#858483 | Disabled / decorative only, never content |
| --text-on-accent | \#3F3F3F | \#1F1E1D | Text on yellow or light accent fills |
| --border | \#E6E6E6 | \#353433 | Default hairline |
| --border-strong | \#D0D0D0 | \#3F3E3D | Emphasized border, header rules |
| --link | \#0B5CAD | \#4C9AFF | Links |
| --focus-ring | \#0B5CAD | \#4C9AFF | Focus outline |
| --btn-primary-bg | \#F7D400 | \#353433 | Primary button fill |
| --btn-primary-hover | \#EED228 | \#3F3E3D | Primary button hover |
| --btn-primary-text | \#3F3F3F | \#E5E5E5 | Primary button label |
| --accent-state | \#F7D400 | \#E5E5E5 | Switch on, selected segment, current card, progress fill |
| --accent-state-text | \#3F3F3F | \#1F1E1D | Text on --accent-state |

Measured: body text 10.0:1 on the light --bg and 13.2:1 on the dark one; --text-muted 4.91:1 on the light --bg, 4.58:1 on light wells, 7.0:1 on the dark --bg and 5.7:1 on dark wells; --link 6.3:1 (light) and 5.8:1 (dark). --text-faint is 3.3:1 in light mode and therefore never carries content.

**Status inks and tints.** Text on a status tint uses the matching ink: --bac-green-ink \#1A7F37 / \#3FB950, --bac-red-ink \#C9302C / \#FF5A4F, --bac-blue-ink \#0B5CAD / \#4C9AFF, --bac-yellow-ink \#7A5F00 / \#F7D400. Tints are low-chroma fills, not glows: light --bac-green-tint \#E8F7EA, --bac-red-tint \#FCE9E7, --bac-blue-tint \#E6EDF3, --bac-yellow-tint \#FEF7D1 (the fill mixed 12, 12, 10 and 18 % into white); dark \#243725, \#3F2421, \#182835, \#3D3719 (16, 16, 22 and 14 % into \#1F1E1D). Every ink meets 4.5:1 on its tint in both modes.

**Hero card.** --hero-bg (= --bac-blue), --hero-text \#FFFFFF (8.7:1), --hero-rule (= --bac-red, decorative). See §6 and the Interface Design Guide §6.

### 4.5 Accent Hierarchy – Ops vs Mission

In the base and **Ops** system, **BAC Yellow** is the light-mode primary accent *and* the caution color in both modes; there is no accent color in dark mode. Blue is information. Nothing else is an accent.

In **Mission** collateral, **Plasma Rose** carries decorative emphasis: draft labels (a PRELIMINARY pill), ornamental bars and dividers, other non-semantic highlights. On the dark hero it uses --mission-rose-on-dark (\#DE5C8C); on paper, --mission-rose-ink for text and the fill for marks. Teal and violet carry diagrams, viewport light and charts.

Semantic warnings always use BAC Yellow, never rose. **Disclaimers** on Mission paper sit in a neutral outline (--border-strong, \#D0D0D0); the text carries the message and the ! glyph marks it. A warning a *tool* raises is always BAC Yellow.

## 5. Form & Layout Foundations

### 5.1 Spacing – 4px Base Grid

--space-1 4, --space-2 8, --space-3 12, --space-4 16, --space-5 24, --space-6 32, --space-7 48, --space-8 64, --space-9 96, --space-10 128 (px). Generous whitespace.

**Containers.** --container **1200px** for documents, the storefront and anything people read; --container-wide **1540px** for dashboards and dense data views such as BAC Ground; --container-narrow 760px. Default gutter = --space-5.

### 5.2 Corners – Soft Cards, Pill Controls

| **Token** | **Value** | **Use** |
|----|----|----|
| --radius-sm | 6px | Inputs, tags, small elements |
| --radius-md | 10px | Cards, panels, wells, callouts, every larger surface |
| --radius-pill | 100px | Buttons, chips, tabs, segmented controls, status pills |

Controls are pills; surfaces are 10px cards. The 3/5/8/12/18px "engineering fillet" scale of the 0.x guides is retired.

### 5.3 Depth – No Shadows

**No drop shadows.** Depth comes from background steps (--bg → --surface-card → --surface-sunken / --bg-raised) and hairline borders. Cards do not lift on hover. The only inset effect left is the Mission paper well (§7).

### 5.4 Borders

Hairline --border (1px) is the default separator. A **strong header rule with no outer border** is the canonical treatment for dense data tables; the BAC Interface Design Guide defines its application across web, notebook, and terminal interfaces. --border-w: 1px, --border-w-thick: 1.5px.

## 6. Backgrounds, Imagery & Surfaces

- **Backgrounds (Ops/base UI) are flat surfaces** – neutral gray in light, slightly warm near-black in dark. No decorative gradients, noise, glassmorphism, or atmospheric texture in base or Ops surfaces. (The store hero and "open source" panels go full-bleed dark with the cube mark.)

- **Mission surfaces may be expressive.** Restrained starfields, orbital lines, soft nebula light in teal and violet, and dark viewport glow are allowed when the context is marketing, product collateral, or high-level presentation – never in Ops UI.

- **Imagery** is real hardware photography – true-to-life color, no heavy filters.

- **Illustration.** Allowed: technical wireframes, schematic overlays, CAD-derived outlines, orbital diagrams, and simple geometric space motifs. Not allowed: cartoon spacecraft, hand-drawn mascots, fantasy planets, or painterly sci-fi art.

- **Cards and panels.** --surface-card, 10px radius, hairline border, no shadow. Selected state follows the Interface Design Guide (--accent-state). No colored-left-border-only cards.

- **Hero card.** One info-blue card per view may lift the single most time-critical or primary-context item (BAC Ground's "Next pass"): --hero-bg fill, white text, an uppercase title over a short red --hero-rule. The red rule is **decorative** – a nod to the founder's former video intro cards – and never an alarm. Same card in light and dark.

- **Transparency/blur** used rarely (a sticky header may sit on a translucent surface). **No glassmorphism.**

## 7. Communication Modes – Ops & Mission

BAC uses two identity modes over the same canonical brand foundation. They affect both visual treatment and communication context. In software implementations they may be expressed as optional theme layers using --mission-\* or --space-\* tokens without overwriting the functional base tokens.

> **Ops is functional. Mission is expressive. Both are BAC.** Use **Ops** for technical and operational communication: tools, dashboards, the ground console, technical documents, datasheets, engineering reports, and other contexts where clarity and restraint dominate. Use **Mission** for outward-facing and presentation-led communication: website heroes, product sheets, launches, sales material, and marketing. A surface may contain interactive elements in either mode; the communication purpose, not the presence of controls, determines the identity layer. When a rule differs between the two – gradients, nebula color, texture – the Ops reading is the strict one and the Mission reading is the expressive one.

| **Theme** | **Use for** | **Character** |
|----|----|----|
| **Ops** | Technical/operational communication, internal tooling, BAC Ground, technical docs, datasheets, dense data UIs | Flat neutral surfaces, pill controls, 10px cards, no decoration, monochrome hierarchy, status colors only where they mean something, one yellow action in light mode |
| **Mission** | Marketing, sales, product sheets, website heroes, presentation surfaces | Dark heroes (--space-ink \#171320), inset viewport panels with teal/violet light, warm --space-paper \#F4F1EA content, Plasma Rose for decorative emphasis |

**Mission theme – three canonical surface types:**

1.  **Dark recessed viewport** – for product renders/diagrams; deep \#171320 bg, teal-tinted border, inner teal and violet glow.

2.  **Light inset paper well** – for overview/included sections; translucent white, soft inset edge.

3.  **Rule-based table** – no box; top rule + header underline only.

Mission core surface tokens: --space-ink \#171320 (deepest dark / hero), --space-surface \#241B3F (raised dark, violet-shifted), --space-paper \#F4F1EA (warm content bg), --space-muted \#8F879E (secondary text on dark).

**Mission surface tokens** – literal values that make the three surface types reproducible:

```css
:root {
  --mission-viewport-bg: #171320;
  --mission-viewport-border: rgba(14, 149, 148, 0.38);
  --mission-viewport-glow:
    inset 0 0 24px rgba(14, 149, 148, 0.16),
    inset 0 0 72px rgba(122, 90, 248, 0.14);

  --mission-paper-well-bg: rgba(255, 255, 255, 0.42);
  --mission-paper-well-border: rgba(36, 27, 63, 0.14);
  --mission-paper-well-shadow:
    inset 0 1px 2px rgba(255, 255, 255, 0.70),
    inset 0 -1px 3px rgba(23, 19, 32, 0.08);
}
```

### 7.1 Product Sheet Print & Export

Product sheets are a print-first surface, so treat paper as the primary target:

- Target **A4 portrait** first, **US Letter** second.

- Page margins **12–16 mm**.

- Avoid full-bleed dark ink except in the hero.

- Minimum body size: **8.5 pt** in print, **12 px** on screen.

- Export PDFs with **embedded fonts** when licensing allows.

- Raster diagrams at **300 dpi** minimum; prefer vector where possible.

### 7.2 Letterhead and Slides

The letterhead (v1r1) and the slides template (v1r2) in bac-design `templates/` (versioned as the Project & Tooling Guide's `v<version>r<revision>`) are the identity applied to the two documents everyone writes, built against the Reference Gallery's document family and product sheet.

- **The kicker is a brand mark.** Every slide and every letter opens with the short BAC Yellow dash (18 × 4 px, rounded 2) before a strong, uppercase IBM Plex Mono eyebrow that names the context – deck type and date, subject or reference. The kicker stays yellow on both surfaces; the eyebrow takes `--text-strong` on paper and `--mission-rose-on-dark` on the Mission hero. The dash is not the one dominant yellow of the slide.

- **Letterhead (Ops).** A4 only, English and German. Nunito Sans 400 at 10.5 pt for the letter, IBM Plex Mono at 8 pt with `--ls-label` for the address block, the date and reference table, the eyebrow, the signature role and the footer; the subject in Nunito Sans 500 at 14 pt. The logo at 40 mm, its height from the file's own aspect. Spacing on the 4 px grid. Footer: a `--border-strong` hairline over the contact line and the UID, `Page x of y` right. The address is `hello@buildacubesat.space`, the date `Bern, YYYY-MM-DD`; the German uses ss, the Gedankenstrich and `Freundliche Grüsse`.

- **Slides.** 16:9, importable into Google Slides, thirteen named layouts with placeholders. Slides are a presentation surface, so Mission: the light layouts sit on `--space-paper` with paper wells that may carry a teal, violet or rose top rule; the dark layouts (title, section, title-only, closing) sit on the nebula, and the title carries the recessed viewport as the product-render slot. Type at body 16 pt = 1 rem: titles 40–44 pt, content titles 32 pt, the section numeral `--text-5xl` in mono, stat figures in mono; display type Nunito Sans 500 with `--ls-tight`. Photo slots – half-bleed on the title and the quote, a paper well with a mono caption on image-and-caption – are for hardware photography (§6). A timeline marks done steps in Orbital Teal, the current one in BAC Yellow and the steps ahead hollow. One hero card per deck (§6). The quote opens with a Plasma Rose mark. The closing slide carries the logo with tagline lockup (§8), never the tagline as a free line.

- Templates are generated, never edited by hand: `bac-brand-assets` in bac-utils writes them, the Mission surfaces rendered from the gallery's CSS; a change goes into the generator and moves the revision. bac-design `templates/README.md` lists every construction value.

### 7.3 Documents

Guides, policies, checklists and other text documents handed out as PDF are Ops surfaces and print-first. The Markdown stays authoritative; the PDF is generated from it by `bac-design-export` in bac-utils and never edited by hand.

- **Page.** A4 portrait first, US Letter second. Margins 18 mm top and bottom, 16 mm left and right; the running header and footer sit in the margins. Fonts embedded, subset.

- **Page one.** The logo (13 mm high), then the kicker and a strong mono eyebrow with the version and date (`VERSION 1.4 · 2026-10-30`), the title in Nunito Sans 500 at 30 pt with `--ls-tight`, the lead – the document's standard line – at 12.5 pt, a mono meta line where the document names authors, and the contents with page numbers for a document of three or more sections. The body starts on page two.

- **Body.** Nunito Sans 400 at 9.5 pt on `--lh-normal`. Section headings in Nunito Sans 500: 15 pt over a 1.5 px `--text-strong` rule, then 11.5 pt and 10 pt; the section number in IBM Plex Mono, `--text-muted`.

- **Running header and footer**, IBM Plex Mono at 7 pt in `--text-muted` – the only text under the 8.5 pt print minimum of §7.1. Header from page two: the document name in uppercase left, version and date right. Footer: the repository and license line left, page x / y right.

- **Elements.** Tables as in §5.4: uppercase mono header labels over a 1.5 px `--text-strong` rule, hairline rows, no fills, no outer border, 8.5 pt. Code in IBM Plex Mono at 8 pt on `--surface-sunken` with 6 px corners. A callout (a Markdown blockquote) is a hairline card in `--border-strong` with 10 px corners, not a quote bar. Bullets are a short `--text-muted` dash. Links in `--link`.

- **No Mission surface.** No dark ink, no nebula color, no shadows. Every color, family, weight and radius comes from the tokens; only the print sizes above are set for paper.

## 8. Iconography & Graphic Language

- **System: Lucide** (lucide.dev, ISC license) – 24×24 line icons, 2px stroke, round caps and joins, drawn in currentColor. Match icon weight to text weight. BAC Ground's own two UI icons (theme toggle, two-line menu) already follow these conventions.

- **Embed icons inline as SVG** – copied Lucide paths, or lucide-react in React apps. No runtime CDN script: an operations console has to work offline.

- **Sizes.** Icon buttons use **18px** icons; inline icons follow the line height of the text they sit in.

- **Fallback: Tabler Icons** (MIT, same grid and stroke) when Lucide lacks a technical icon; the two sets mix without looking out of place.

- **Status shapes are not icons.** The filled, hollow, dashed and outlined shapes of the five-state system are a separate glyph set owned by the Interface Design Guide §2.

- **Semantic symbols** (text, not icons): ✓ pass, ✗ fail, ! warn, → progression, , or · separator. Their interface semantics are defined in the BAC Interface Design Guide.

  **To be decided – glyph coverage.** None of the three BAC families has ✗, nor any other cross mark (✔ ✕ ✖ ✘); the only cross they share is ×, which §2 reserves for quantities. Until this is decided, ✓ and ✗ render in the surface's system font, as a pair – in the guide PDFs, on the web and in Google Slides alike – and no custom symbol font is made for them (decided 2026-10-30). Arrows and box drawing come from IBM Plex Mono.

- **Brand marks, v4r1.** Three marks, versioned together like hardware (`v<version>r<revision>`, Project & Tooling Guide §2.2) and supplied as black, white and `currentColor` SVG in bac-design `assets/`; written by `bac-brand-assets` in bac-utils from the construction below, never edited by hand. Black and white only, never recolored; `currentColor` is for inlining in HTML, where the mark takes the color of its text.

  - **Symbol** – an isometric 2U cube: a 1 × 1 × 2 box in true 30° projection, cube edge 200 on a 400 × 650 canvas (346.41 wide, 600 tall, centered). One hexagonal outline with its six corners rounded 5 from the vertex; the inner edges – the top face's lower edges, the center vertical, the lower cube's top face – as a second path; a filled dot at the center of the top face, an ellipse 60 × 34.64 (the 1:√3 ratio of a circle in isometric projection). Stroke 15, round joins and caps, no fill.
  - **Wordmark** – BUILD A over CUBESAT in Nunito 350, uppercase, tracking −0.03 em, cap height 100 and 150 from baseline to baseline, the first line justified to the width of the second; outlined, so the files carry no font.
  - **Logo** – the horizontal lockup: the symbol on its canvas, the wordmark 70 to its right, scaled so its two-line block is 70 % of the cube height and centered on the cube. There is no stacked lockup.
  - **Logo with tagline** – the logo with SPACE FOR EVERYONE under the wordmark: IBM Plex Mono, 0.286 em tracking, sized to 72 % of the wordmark's width and centered under it with a rule either side filling the rest – the setting the Rocinante subtitle uses – the block of both centered on the cube. The tagline is set only in this lockup, never in Nunito and never alone as a mark; as prose it reads *Space for everyone.*
  - **Badges** – the symbol on a filled rounded hexagon (the cube's silhouette grown by 70, corners rounded 60, a `--border-strong` hairline) and the logo on that hexagon merged with a rounded rectangle at the same offset around the wordmark, the merge filleted, white for light surfaces and `--bg` dark for dark ones; for stickers, avatars and anything on a colored or photographic background, where the plain marks would lose their edge.
  - **Rocinante** – the flight software stack's own marks: the horse head in a ring with three gaps, ROCINANTE in Nunito over CUBESAT SOFTWARE STACK in IBM Plex Mono, and their stacked lockup, at v2r1 in bac-design `assets/` (`rocinante-*`). Monochrome like the BAC marks, plus a two-tone in brand colors: `--text-strong` for head and word, `--bac-blue` for ring and subtitle.

  The symbol, the wordmark and the logo are BAC Marks under the BAC Trademark Policy and are excluded from the open licenses; this description exists so they are reproduced correctly, not as a license. Colors and type tokens are not marks on their own.

- **No emoji. No hand-drawn illustration in UI.**

## 9. Reference Applications & Exemplars

These are visual applications of the identity system. Interaction and accessibility rules live in the **BAC Interface Design Guide**; implementation rules live in the **BAC Project & Tooling Guide**.

**BAC Ground.** The mission-operations console is the reference implementation of this guide's visual language: surfaces, status system, controls, density and the hero card were adopted from it in 1.0.

**Design tokens.** The canonical, executable copy of this guide's tokens is `tokens.json` (W3C design-tokens format) in bac-utils (tools/bac-design-tokens, see the Project & Tooling Guide §2.8). Its generator writes every copy: the reference gallery's and the bac-suite's `tokens.css`, the Rich colors in bac-common and the Marimo style cells. A token change lands in `tokens.json` and in this guide in the same change; nobody edits a generated copy by hand. `tokens.json` and the generated stylesheets are licensed MIT or CC BY-SA 4.0, at your option, so any software – including the AGPL-licensed BAC Ground, which takes a copy of the generated `tokens.css` – may use them.

**BAC Reference Gallery.** The companion BAC Reference Gallery provides reproducible HTML/CSS/SVG exemplars showing how the three BAC guides can be applied to representative documents, interfaces, data visualizations, physical communication, and other media. The gallery is a **reference, not a template library**: compositions may be adapted freely, while the underlying identity, interface, and tooling rules remain authoritative in their respective guides.

The HTML/CSS/SVG sources are the canonical gallery artifacts. PNG and PDF versions are generated exports for convenient viewing, sharing, and print reference. If an exemplar conflicts with a guide, **the guide wins**. The gallery lives in bac-utils (tools/bac-reference-gallery); its pages and illustrations stay CC BY-SA 4.0, except the BAC Marks shown in them, which follow the BAC Trademark Policy.

Current exemplar families include:

- Identity overview

- Ops vs Mission

- Document family

- Interface patterns

- Data visualization

- Physical communication

- Dev Kit product sheet

**Representative applications**

- **Website** – storefront (home, product, about) in light + dark. Base UI rules govern functional areas; Mission may be used for heroes, launches, and product storytelling.

- **BAC Ground** – Ops throughout: wide container, flat neutral surfaces, status chips, ops plot colors, one hero card on the overview.

- **Internal pricing tool and notebooks** – visual treatment uses the Ops theme: stat cards, data tables, charts, and controls rebranded cleanly off default Marimo styling. Interaction and chart presentation are specified in the Interface Design Guide; notebook structure and implementation are specified in the Project & Tooling Guide.

- **Product sheet** – the Dev Kit v1 reference exemplar demonstrates a Mission-led, print-first product sheet: restrained dark starfield hero, recessed technical viewport, warm paper body, inset information wells, rule-based specifications, and restrained nebula accents. Its composition is illustrative rather than mandatory; other product sheets should reproduce the underlying hierarchy and Mission language rather than copy the layout verbatim.

## 10. Source Materials & Caveats

**Sources** (may require access): website buildacubesat.space; short links bac.page/\*; code on Codeberg (codeberg.org/buildacubesat-project/\*) and GitHub (github.com/buildacubesat/\*) – see the Project & Tooling Guide §2.8 for the repo split; the BAC Ground console and its design notes (design/README.md in the bac-ground repository); the **BAC Project & Tooling Guide** (authoritative for project and tooling behavior); the Dev Kit v1 product-sheet PDF.

**Caveats**

- **Reference Gallery.** The BAC Reference Gallery is a companion implementation aid derived from the three governance guides. Its HTML/CSS/SVG sources are canonical for the exemplars themselves; PNG and PDF files are generated representations. The gallery demonstrates possible applications and does not create new identity, interface, or implementation rules.

- **Example content is non-authoritative.** Product values, prices, availability, dates, engineering measurements, status, and other project data appearing in exemplars are illustrative unless explicitly linked to a current authoritative source. Do not treat an exemplar as a source of live project information.

- **BAC Ground is the reference, not a dependency.** Where the console and this guide differ (for example the console's DM Sans / Roboto Mono, 400-weight headings and neutral \#1F1F1F dark background), this guide wins; the console syncs to the generated tokens.

- Fonts load from Google Fonts CDN or are self-hosted from bac-design `fonts/` where a surface must work offline. Moon 2.0 is retired.

- The official marks are the v4r1 files in bac-design `assets/` (`bac-symbol-*-v4r1.svg`, `bac-wordmark-*-v4r1.svg`, `bac-logo-*-v4r1.svg`, nihil.space GmbH); the reference gallery ships the symbol as `assets/bac-symbol.svg`. Official hardware photography should replace the illustrative renders when available.

## 11. Quick Reference – The Non-Negotiables

1.  **Build a CubeSat** on first reference; **BAC** thereafter. Lowercase bac is for code, filenames, and identifiers only.

2.  Voice is plain-spoken, technical, honest, and quietly enthusiastic. **Fail loudly, succeed quietly.**

3.  **Nunito** = wordmark (uppercase), **Nunito Sans** = headings (500) and body (400), **IBM Plex Mono** = labels, figures and code (tabular, 0.03em label tracking). Never mono body text.

4.  **BAC Yellow** (\#F7D400) is the light-mode primary action and the caution color in both modes; dark mode has no accent – gray buttons, neutral state marks. "One dominant use" means one visually dominant yellow action or surface per state; legitimate small semantic indicators may coexist.

5.  Status is color + shape + word: green \#3FB950, caution \#F7D400, alarm \#E94538, info \#004C8B, each with a per-theme ink for text.

6.  Blue means information, links and focus – nothing else.

7.  **Neutral grays in light, slightly warm near-blacks in dark** – never a cold blue-gray.

8.  **Pill controls, 6px/10px surfaces, no shadows**, hairline borders.

9.  **Ops is functional and restrained. Mission is expressive and presentation-led. Both are BAC.** The communication purpose determines the mode.

10. Mission may use the nebula triad (Orbital Teal, Ion Violet, Plasma Rose), restrained starfields/orbital lines and inset viewports; Plasma Rose carries non-semantic emphasis. Ops stays flat and never uses nebula color.

11. **No emoji**, no glassmorphism. Technical wireframes and CAD/schematic motifs are allowed; cartoon or painterly sci-fi imagery is not. Icons are Lucide, inline.

12. Use the en dash –, never the em dash —, except when naming the forbidden glyph itself. Use × for quantities and ' for Swiss thousands separators.

13. Tokens live in `tokens.json` in bac-utils; every other copy is generated.

14. The Interface Design Guide owns interaction, accessibility, data-viz behavior, components, and physical indicators. The Project & Tooling Guide owns engineering/project/software implementation conventions.

15. The BAC name and marks are not open source: their use by others follows the **BAC Trademark Policy**.

## 12. Version History

The BAC governance guides are independently versioned. Product and subsystem documentation follows the version of the artifact it documents; see the BAC Project & Tooling Guide for the full documentation rule.

| **Version** | **Date** | **Change** |
|------------|-------------|-----------------------------------------------------------------|
| 1.4 | 2026-10-30 | §7.2: the slides template at v1r2 – Mission throughout, the light layouts on paper with wells and nebula top rules, the dark layouts on the nebula, the timeline and quote treatments, thirteen layouts. §8: the tagline as prose reads *Space for everyone.*; glyph coverage of ✓ and ✗ recorded as to be decided, system font until then New §7.3: documents – the print spec of the guide PDFs, generated from the Markdown by `bac-design-export` (A4 first, page one with logo, kicker, eyebrow, title, lead and contents, the body type and heading sizes, running header and footer, tables, code and callouts, Ops only). |
| 1.3 | 2026-10-29 | The governance alignment of the 2026-10-24 docs stock-take. §1: nihil.space GmbH as the only legal entity; the timeline snapshot without its forward-looking entry; no price in the catalog line – prices belong on the storefront. The slogan shortened to "Space for everyone", matching the tagline. §2: Title Case for headings, titles and labels everywhere, replacing sentence case and its Blender and marimo exceptions; American spelling. Headings to Title Case and American spelling throughout. |
| 1.2 | 2026-10-28 | §7.2: the letterhead (A4, EN and DE) and the slides template (16:9, twelve layouts) at v1r1 in bac-design `templates/`, generated by `bac-brand-assets`; the kicker as a brand mark, the Mission hero and viewport on the dark layouts, the type scale at body 16 pt, photo slots, the tagline lockup on the closing slide. |
| 1.1 | 2026-10-27 | §8: the marks at v4r1 – the symbol's construction (true 30° isometric 2U cube, edge 200, stroke 15, corners rounded 5, the dot 60 × 34.64 on a 400 × 650 canvas), the wordmark in Nunito 350 with −0.03 em tracking, the logo as the horizontal lockup at 70 % of the cube height and gap 70, the logo with tagline, the badges, and the Rocinante marks at v2r1; black, white and `currentColor` files in bac-design `assets/`, written by `bac-brand-assets`; no stacked lockup. §3: the wordmark weight, 350 added to the Nunito import, the self-hosted fonts in bac-design `fonts/`. §10: the file names. |
| 1.0 | 2026-10-27 | Rebased on the BAC Ground console language, with Mänu as design owner (decided 2026-10-24 to 2026-10-27). §0: the language summary rewritten. §1: BAC Ground and the notebooks as surfaces. §3: Nunito Sans 500 headings and Nunito Sans 400 body; IBM Plex Mono for labels, figures and code only, with 0.03em label tracking (--ls-label); --fw-heading; --lh-normal 1.45; Space Mono dropped as a future option. §4: the console status set with fill/ink split (green \#3FB950, caution \#F7D400, alarm \#E94538, info \#004C8B); \#4277FD retired, blue means info, links and focus; yellow is caution only in dark mode; the nebula palette redone as a triad – Orbital Teal \#0E9594, Ion Violet \#7A5AF8, Plasma Rose \#C64677 with inks, on-dark shades and tints – retiring Orbital Cyan, Ion Blue, Solar Copper, Deep Field Violet and Nebula Ember; the warm ramp replaced by the console's neutral ramp (--neutral-\*); light --bg \#F9F9F9, dark --bg \#1F1E1D with derived surfaces, wells lighter than --bg in dark; new --btn-primary-\*, --accent-state, --hero-\* and --kicker tokens; Plasma Rose takes copper's Mission job and disclaimers get a neutral outline (§4.5). §5: containers 1200px and 1540px (--container-wide); radii 6px/10px plus pill controls; no shadows. §6: the hero card and its decorative red rule. §7: Mission paper \#F4F1EA; the viewport lit in teal and violet; --mission-card-shadow removed. §8: Lucide embedded inline, 18px icon buttons, Tabler as fallback, status shapes are not icons. §9: BAC Ground as reference implementation; tokens.json in bac-utils as the executable token source with generated copies, MIT or CC BY-SA 4.0. §11: the non-negotiables rewritten. §1, §8, §9, §11: the BAC name, abbreviation, cube mark, wordmark and lockup are BAC Marks, excluded from the open licenses and governed by the new BAC Trademark Policy 1.0. |
| 0.9 | 2026-10-24 | §4.4: --text-muted and --link moved to WCAG AA values (#6C6B67/#A3A29C, \#2F5FD6/#7BA0FE), the focus ring split into its own --focus-ring row at the plain accent, the measured ratios recorded; derived inks for text on status tints and on Mission paper. §9: the gallery's home in bac-utils, tokens.css as the executable token copy, the stylesheets' MIT or CC BY-SA 4.0 dual license (decided 2026-10-08 and 2026-10-09). |
| 0.8 | 2026-08-11 | Added the **BAC Reference Gallery** as the companion visual exemplar set. Established HTML/CSS/SVG as the canonical exemplar source with PNG/PDF as generated exports; clarified that exemplars demonstrate rather than prescribe layouts and must not be treated as sources of live project data; expanded the product-sheet reference guidance; and replaced the stray ⚠ disclaimer example with the approved ! glyph. |
| 0.7 | 2026-08-10 | Replaced the former Design System Specification with a three-guide structure. Renamed this document to **BAC Identity Guide** and narrowed its authority to brand, voice, visual primitives, imagery, and Ops/Mission communication modes. Moved interaction, accessibility, data-viz behavior, components, and physical indicators to the new BAC Interface Design Guide; project/tooling implementation remains in the BAC Project & Tooling Guide. Preserved the clarified one-dominant-yellow rule from the v0.7 migration work. |
| 0.6 | 2026-07-08 | Added §9 Hardware Indicators (LEDs) as a UI design convention: single-color semantics (white=power, green=pass, red=fault, yellow=warn, blue=activity), tri-color R/Y/G health-LED usage, and behavior rules (solid vs. blink, latching faults, documenting "off," blink pattern as the accessibility-required non-color channel). Renumbered §9–§14 to §10–§15 accordingly and updated the two live cross-references to Accessibility (now §12). |
| 0.5 | 2026-07-08 | Resolved the Ops/Mission tension. Made the split explicit ("Ops is functional, Mission is expressive; both are BAC"). Reconciled the no-gradient and no-amber rules with Mission visuals – base/Ops stay flat and yellow-warned, Mission may use restrained nebula texture and Solar Copper for non-semantic emphasis. Reintroduced Nebula Ember (#A94E52) as a Mission-only accent. Added an accent-hierarchy rule (§4.5), a data-viz series order (§4.6), literal Mission surface tokens and product-sheet print rules (§7), and a new Accessibility section (§11). Softened the "not sci-fi" vibe line and dated the company timeline as a historical snapshot. |
| 0.4 | 2026-07-08 | Restructured to match the Internal Tools Design Guide format: added a titled subtitle line with version and this version-history section (Quick reference promoted to a numbered section). Converted all em dashes to en dashes (–) per the brand's own typography rule. Updated guide references to v0.10. |
| 0.3 | 2026-07-08 | Number/currency clause: apostrophe ' for CHF and metric values, comma for USD prices – mirrored from the guide's §2.7. |
| 0.2 | 2026-07-08 | Trimmed tooling detail and reconciled with the Internal Tools Design Guide: retired Moon 2.0 (→ Nunito / Nunito Sans / IBM Plex Mono), removed amber (warnings use BAC Yellow), added the authority-split note and pointers to the guide in place of restated tooling rules. |
| 0.1 | 2026-07-08 | Initial specification generated via Claude Design: functional + nebula color systems, warm neutral ramp, type scale, spacing / radii / shadows / motion, Ops and Mission theme layers, iconography, React component primitives, and UI kits. |
