# bac-design

Build a CubeSat – the design guides: the normative text for the BAC identity, its interfaces, its tooling conventions and the use of its name and marks. Everything that renders or implements the design – the tokens, the reference gallery, the tools – lives in [bac-utils](https://github.com/buildacubesat/bac-utils) and follows the text here. If a rendered thing and a guide disagree, the guide wins.

## 1. The guides

| Guide | Version | Governs |
| :-- | :-- | :-- |
| [BAC Identity Guide](guides/bac-identity-guide.md) | 1.1 | Brand, voice, typography, colour, form, imagery, the Ops and Mission modes |
| [BAC Interface Design Guide](guides/bac-interface-design-guide.md) | 1.0 | Interaction, the five-state system, accessibility, components, data visualisation, the terminal profile, physical indicators |
| [BAC Project & Tooling Guide](guides/bac-project-and-tooling-guide.md) | 0.15 | Licensing, versioning, repositories, data formats, CLI and marimo implementation, documentation process |
| [BAC Project & Tooling Guide – condensed](guides/bac-project-and-tooling-guide-condensed.md) | follows the three above | The checklist used when reviewing tools |
| [BAC Trademark Policy](guides/bac-trademark-policy.md) | 1.1 | How others may use the Build a CubeSat name and marks |

Each guide is independently versioned and carries its own version history. `guides/` holds the Markdown source and is what to read and edit. `exports/` holds a PDF of each guide for handing to people outside git, regenerated on every change (`pandoc guides/<name>.md -o <name>.docx` with the reference document, then `soffice --headless --convert-to pdf`).

## 2. Where the executable side lives

- `tokens.json`, the canonical copy of the Identity and Interface guides' tokens, and `bac-design-tokens`, which writes every stylesheet, terminal colour and notebook style cell from it: [bac-utils/tools/bac-design-tokens](https://github.com/buildacubesat/bac-utils/tree/main/tools/bac-design-tokens).
- The reference gallery, seven boards that show the guides applied: [bac-utils/tools/bac-reference-gallery](https://github.com/buildacubesat/bac-utils/tree/main/tools/bac-reference-gallery).
- BAC Ground, the mission-operations console whose language the 1.0 guides adopted.

A change of meaning – a new rule, a retired token – is made here first; the value then changes in `tokens.json` in the same change set.

## 3. Brand assets

`assets/` holds the official Build a CubeSat symbol, wordmark and logo at v4r1, as black, white and `currentColor` SVG; [`assets/README.md`](assets/README.md) lists the files and their construction. They are BAC Marks under the Trademark Policy and are not covered by this repository's licence. The files are written by [`bac-brand-assets`](https://github.com/buildacubesat/bac-utils/tree/main/tools/bac-brand-assets) in bac-utils from the construction the Identity Guide §8 states, never edited by hand.

`fonts/` holds the self-hosted copies of the three families (Nunito, Nunito Sans, IBM Plex Mono; OFL 1.1) that offline surfaces and the tools use; see [`fonts/README.md`](fonts/README.md).

## 4. License

The guides and this README are licensed CC BY-SA 4.0. The Build a CubeSat name, the abbreviation BAC, the symbol, wordmark and logo are not: they are BAC Marks of nihil.space GmbH, and their use is governed by the [BAC Trademark Policy](guides/bac-trademark-policy.md). Describing a mark in a guide does not license it. The fonts in `fonts/` keep their SIL Open Font License 1.1. See `LICENSE.md`.

## 5. Version history

| Version | Date | Change |
| :-- | :-- | :-- |
| 1.1.0 | 2026-10-27 | The marks: `assets/` with the symbol, wordmark and logo at v4r1 (black, white, `currentColor`), written by `bac-brand-assets`; `fonts/` with the self-hosted Nunito, Nunito Sans and IBM Plex Mono. Identity Guide 1.1 (§8 construction of the marks, §3 wordmark weight and fonts) and Trademark Policy 1.1 (symbol, wordmark, logo). |
| 1.0.0 | 2026-10-27 | First release: the five guides moved out of Google Drive at Identity 1.0, Interface Design 1.0, Project & Tooling 0.15 and Trademark Policy 1.0, with PDF exports. |
