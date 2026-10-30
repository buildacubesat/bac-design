# Brand assets

The official Build a CubeSat marks at **v4r1**: the symbol, the wordmark and the logo, each as black, white and `currentColor` SVG. They are BAC Marks of nihil.space GmbH and are not covered by the repository's CC BY-SA 4.0 license; their use is governed by the [BAC Trademark Policy](../guides/bac-trademark-policy.md) (hello@buildacubesat.space).

## 1. Files

| File | What it is | Use |
| :-- | :-- | :-- |
| `bac-symbol-black-v4r1.svg`, `-white-` | The cube mark on a 400 × 650 canvas | Favicons, app icons, anywhere the mark stands alone |
| `bac-symbol-currentcolor-v4r1.svg` | The same, stroke and dot in `currentColor` | Inlined in HTML; takes the color of the text around it |
| `bac-wordmark-black-v4r1.svg`, `-white-`, `-currentcolor-` | BUILD A / CUBESAT, Nunito, outlined | Text-only placements |
| `bac-logo-black-v4r1.svg`, `-white-`, `-currentcolor-` | The horizontal lockup: symbol left, wordmark right | The default: headers, documents, signatures |
| `bac-logo-tagline-black-v4r1.svg`, `-white-`, `-currentcolor-` | The logo with SPACE FOR EVERYONE under the wordmark, in mono between two rules | Title pages, the storefront, anywhere the brand introduces itself |
| `bac-symbol-badge-light-v4r1.svg`, `-dark-` | The symbol on a filled rounded hexagon with a hairline | Stickers, avatars, favicons on colored or photographic backgrounds |
| `bac-logo-badge-light-v4r1.svg`, `-dark-` | The logo on the hexagon badge merged with a rounded rectangle around the wordmark | Stickers, merchandise, overlays on photos |
| `rocinante-symbol-…-v2r1.svg`, `rocinante-wordmark-…`, `rocinante-logo-…` | The Rocinante marks (the flight software stack): the horse in its ring, ROCINANTE over "CUBESAT SOFTWARE STACK", the stacked lockup – black, white, currentColor and the two-tone `color` in brand colors | The flight software's repositories, docs and console |

Every colored SVG also exists as PNG and WebP in `png/` and `webp/`, at 512 and 2048 px on the longest side (`bac-logo-black-v4r1-2048.png`), transparent, the WebP lossless – for the places that cannot take an SVG. Black on light surfaces, white on dark; never recolored (Identity Guide §8). The files carry only a `viewBox`, no `width` or `height`, and scale to whatever size the consumer sets. Each has a `<title>`, a `<desc>` with its construction and the trademark notice, and Dublin Core metadata (`dc:creator`, `dc:rights`, `dc:date`) naming nihil.space GmbH.

## 2. Construction

The files are written by [`bac-brand-assets`](https://github.com/buildacubesat/bac-utils/tree/main/tools/bac-brand-assets) in bac-utils from these values; nobody edits them by hand. The tool reads `../fonts/Nunito[wght].ttf` and writes here, the renderings included; `--check` fails if an SVG is out of date with its construction or a rendering is missing.

| Part | Construction |
| :-- | :-- |
| Symbol | A 1 × 1 × 2 box in true 30° isometric projection, cube edge 200: 346.41 wide, 600 tall, centered on the 400 × 650 canvas. One hexagonal outline with its six corners rounded 5 from the vertex, the inner edges – the top face's lower edges, the center vertical, the lower cube's top face – as a second path, and a dot at the center of the top face, an ellipse 60 × 34.64 (the 1:√3 ratio of a circle in isometric projection). Stroke 15, round joins and caps, no fill. |
| Wordmark | Nunito at weight 350, uppercase, tracking −0.03 em; cap height 100, 150 from baseline to baseline, "BUILD A" justified to the width of "CUBESAT"; 25 of margin. |
| Logo | The symbol on its own canvas; the wordmark 70 to its right, scaled so its two-line block is 70 % of the cube height and centered on the cube. The letter stems then match the cube stroke. |
| Tagline | SPACE FOR EVERYONE in IBM Plex Mono, tracking 0.286 em, sized to 72 % of the wordmark's width and centered under it, a rule either side filling the rest; the block of wordmark and tagline is centered on the cube. The same setting as the Rocinante subtitle. |
| Badge | The cube's hexagon grown by 70, corners rounded 60, a 2-unit hairline (`--border-strong` of the respective mode). The logo badge merges that hexagon with a rectangle grown by the same 70 around the wordmark, reaching left to the cube's center line so the two meet on the diagonals; the merge is filleted 30. Light: white; dark: `#1F1E1D`. |
| Rocinante | The head, eye and ear from the original Krita vector artwork, scaled 5× onto a 550 × 550 canvas; the ring a true circle of radius 241.35 and stroke 11 with three gaps where the ears and the neck cross it; ROCINANTE in Nunito 350 with 0.125 em tracking, the subtitle in IBM Plex Mono with 0.29 em tracking and a short rule either side; the logo stacks the wordmark under the ring. Two-tone in brand colors: `--text-strong` for head and word, `--bac-blue` for ring and subtitle. |

## 3. Versioning

The marks are versioned like hardware (Project & Tooling Guide §2.2): `v<version>r<revision>`, in the file name. A redrawn mark is a new version, an adjusted construction a new revision; the three marks move together. The v3r1 files (a bitmap trace of the symbol, the wordmark in the legacy face) are superseded and are not kept here; Rocinante's v1 is the Krita original.

## 4. Version History

| Version | Date | Change |
| :-- | :-- | :-- |
| v4r1, Rocinante v2r1 | 2026-10-29 | Files regenerated by `bac-brand-assets` 0.3.0: the Rocinante two-tone files renamed from `-colour-` to `-color-`, the SVG descriptions in American spelling. The marks themselves are unchanged. |
| v4r1 | 2026-10-27 | First release in this repository. Symbol reconstructed from exact isometric geometry on a 400 × 650 canvas, stroke 15, corners rounded; wordmark reset in Nunito 350, replacing the legacy face; the horizontal logo as the one lockup, with a tagline variant; the symbol and logo badges (light, dark); black, white and `currentColor` files with title, desc and Dublin Core metadata. Rocinante at v2r1: the marks rebuilt from the Krita file's vector layers, with the ring as a true circle, in the same colorings plus a two-tone in brand colors. PNG and WebP renderings of every colored mark at 512 and 2048 px. |
