# Brand assets

The official Build a CubeSat marks at **v4r1**: the symbol, the wordmark and the logo, each as black, white and `currentColor` SVG. They are BAC Marks of nihil.space GmbH and are not covered by the repository's CC BY-SA 4.0 licence; their use is governed by the [BAC Trademark Policy](../guides/bac-trademark-policy.md) (hello@buildacubesat.space).

## 1. Files

| File | What it is | Use |
| :-- | :-- | :-- |
| `bac-symbol-black-v4r1.svg`, `-white-` | The cube mark on a 400 × 650 canvas | Favicons, app icons, anywhere the mark stands alone |
| `bac-symbol-currentcolor-v4r1.svg` | The same, stroke and dot in `currentColor` | Inlined in HTML; takes the colour of the text around it |
| `bac-wordmark-black-v4r1.svg`, `-white-`, `-currentcolor-` | BUILD A / CUBESAT, Nunito, outlined | Text-only placements |
| `bac-logo-black-v4r1.svg`, `-white-`, `-currentcolor-` | The horizontal lockup: symbol left, wordmark right | The default: headers, documents, signatures |

Black on light surfaces, white on dark; never recoloured (Identity Guide §8). The files carry only a `viewBox`, no `width` or `height`, and scale to whatever size the consumer sets. Each has a `<title>`, a `<desc>` with its construction and the trademark notice, and Dublin Core metadata (`dc:creator`, `dc:rights`, `dc:date`) naming nihil.space GmbH.

## 2. Construction

The files are written by [`bac-brand-assets`](https://github.com/buildacubesat/bac-utils/tree/main/tools/bac-brand-assets) in bac-utils from these values; nobody edits them by hand. The tool reads `../fonts/Nunito[wght].ttf` and writes here; `--check` fails if a file is out of date with its construction.

| Part | Construction |
| :-- | :-- |
| Symbol | A 1 × 1 × 2 box in true 30° isometric projection, cube edge 200: 346.41 wide, 600 tall, centred on the 400 × 650 canvas. One hexagonal outline with its six corners rounded 5 from the vertex, the inner edges – the top face's lower edges, the centre vertical, the lower cube's top face – as a second path, and a dot at the centre of the top face, an ellipse 60 × 34.64 (the 1:√3 ratio of a circle in isometric projection). Stroke 15, round joins and caps, no fill. |
| Wordmark | Nunito at weight 350, uppercase, tracking −0.03 em; cap height 100, 150 from baseline to baseline, "BUILD A" justified to the width of "CUBESAT"; 25 of margin. |
| Logo | The symbol on its own canvas; the wordmark 70 to its right, scaled so its two-line block is 70 % of the cube height and centred on the cube. The letter stems then match the cube stroke. |

## 3. Versioning

The marks are versioned like hardware (Project & Tooling Guide §2.2): `v<version>r<revision>`, in the file name. A redrawn mark is a new version, an adjusted construction a new revision; the three marks move together. The v3r1 files (a bitmap trace of the symbol, the wordmark in Moon 2.0) are superseded and are not kept here.

## 4. Version history

| Version | Date | Change |
| :-- | :-- | :-- |
| v4r1 | 2026-10-27 | First release in this repository. Symbol reconstructed from exact isometric geometry on a 400 × 650 canvas, stroke 15, corners rounded; wordmark reset in Nunito 350 after the retirement of Moon 2.0; the horizontal logo as the one lockup; black, white and `currentColor` files with title, desc and Dublin Core metadata. |
