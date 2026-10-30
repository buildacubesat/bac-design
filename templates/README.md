# Templates

The Build a CubeSat document templates at **v1r1**: the A4 letterhead in English and German, and the 16:9 slides template. They apply the Identity Guide as the Reference Gallery shows it (Ops by default – white paper, a monochrome hierarchy, the kicker before a mono eyebrow – and the Mission surface for the outward-facing title, divider and closing slides) and carry the v4r1 marks, which are BAC Marks of nihil.space GmbH under the [BAC Trademark Policy](../guides/bac-trademark-policy.md); the templates themselves are CC BY-SA 4.0 like the rest of the repository, the marks in them are not.

## 1. Files

| File | What it is |
| :-- | :-- |
| `bac-letterhead-en-v1r1.docx` | A4 portrait letterhead, English: the logo and the address block in the header, a placeholder letter, the contact line and page numbers in the footer |
| `bac-letterhead-de-v1r1.docx` | The same in German |
| `bac-slides-template-v1r2.pptx` | 16:9 slides template: twelve layouts in the slide master and one sample slide per layout |

## 2. Letterhead

Nunito Sans 400 at 10.5 pt for the letter, IBM Plex Mono at 8 pt (0.03 em tracking) for the address block, the date and reference table, the eyebrow, the signature role and the footer. Margins 20 mm left and right, the header at 14 mm from the top edge, the text block starting 48 mm down. The page reads, top to bottom: the logo (40 mm wide, the height from the file's own aspect) with the address block right; the recipient; the date, reference and contact as a small mono table (muted labels, strong values); the kicker – the short BAC Yellow dash – before a strong mono eyebrow such as `OFFER · DEV KIT V1`; the subject in Nunito Sans at 14 pt; salutation, paragraphs and closing; the sender in strong ink over the role as a mono label. Spacing sits on the 4 px grid (60 DXA). Footer: a `--border-strong` hairline, then `hello@buildacubesat.space · buildacubesat.space · +41 31 561 93 45` over `UID CHE-172.893.875`, and `Page x of y` right. The date is written `Bern, YYYY-MM-DD`; the German version uses ss, the Gedankenstrich and `Freundliche Grüsse`.

To write a letter: open the file, replace the placeholder lines, save under a new name, export to PDF. The fonts are not embedded in the `.docx` – install them from `../fonts/` on the machine that edits the letter; the PDF export embeds them. In Google Docs the file opens with its layout intact; Nunito Sans and IBM Plex Mono are in the Google Fonts catalogue.

## 3. Slides

`bac-slides-template-v1r2.pptx`, 10 × 5.625 in (16:9). Theme fonts Nunito Sans for titles and body; IBM Plex Mono on the eyebrows, figures, labels, the footer and the contact slide. Theme colors: text `#1F1F1F` / `#3F3F3F`, surfaces `#FFFFFF` / `#F9F9F9`, accents BAC Yellow, info blue, the nebula triad and green; links `#0B5CAD`.

Type scale, the guide's rem scale at body 16 pt = 1 rem: title slides 40 pt (a half-width column), section titles 44 pt, content titles 32 pt, quotes 30 pt, lead 18 pt, body 16 pt, captions and card text 14 pt, eyebrows 10 pt, labels 9 pt, footer 8 pt; the section number 88 pt in mono (`--text-5xl`), stat figures 30–44 pt in mono. Display type is Nunito Sans 500 with −0.02 em tracking, mono labels take +0.03 em.

Slides are a presentation surface, so Mission (Identity Guide §7):

- **Light layouts** sit on `--space-paper` `#F4F1EA`. Cards are paper wells – white 42 % over paper, flattened to `#F9F7F4` with a `#D7D3D2` edge and 10 px corners – and may carry a top rule in Orbital Teal `#0E9594`, Ion Violet `#7A5AF8` or Plasma Rose `#C64677`, one color per card, as the Tooldance media kit does.
- **Dark layouts** sit on the nebula (`nebula.jpg`, 1920 × 1080, from the Tooldance media kit of 2026-10): titles in `--space-paper`, secondary text `--space-muted` `#8F879E`, the eyebrow in `--mission-rose-on-dark` `#DE5C8C`, dates and links in `--mission-teal-on-dark` `#1A9A99`. Dark cards are the viewport's panel color `#101421` at 75 % with a teal edge.
- The kicker stays BAC Yellow on both surfaces.

| Layout | For |
| :-- | :-- |
| `TITLE` | The first slide on paper: logo, kicker and eyebrow with deck type and date, title, subtitle, a meta line; the right half is a half-bleed photo slot for hardware photography (delete it for a text-only title) |
| `TITLE_MISSION` | The first slide on the nebula; the recessed viewport (gridded dark panel, teal border, inner glow) on the right is the product-render slot |
| `SECTION`, `SECTION_MISSION` | Dividers: a faint display numeral in mono over the section title |
| `TITLE_BODY` | Title with one text block |
| `TWO_COLUMNS` | Two paper wells with teal and violet top rules: before/after, options, pros/cons |
| `IMAGE_CAPTION` | Commentary left; the picture right in a paper well with a mono caption under it |
| `TITLE_ONLY` | Everything composed on paper: the hero card and stat cards, charts (the sample shows the hero card beside four stat wells with nebula top rules) |
| `TITLE_ONLY_MISSION` | The same on the nebula: timelines, roadmaps, one big statement. The sample timeline: done steps in Orbital Teal on a solid line, the current step BAC Yellow, the steps ahead hollow on a dashed line, mono dates, a callout card under it; up to five steps |
| `TABLE` | A table placeholder: mono header labels over a strong rule, hairline row rules, no fills |
| `QUOTE` | One sentence at 30 pt under a Plasma Rose opening mark, a short rose rule, a portrait slot with name and a mono role line; a half-bleed photo slot on the right (delete it for a quote that stands alone) |
| `CONTACT` | The closing slide on the nebula: the logo with tagline lockup, title, contact lines in mono; the sample adds a resources card |
| `BLANK` | Full-bleed images and hand-composed diagrams |

The kicker (an 18 × 4 px BAC Yellow dash before a strong, uppercase mono eyebrow) opens every slide; it is the brand mark, not a decoration, and the eyebrow names the slide's context. Every content layout carries the footer – the deck name as a mono label left, the symbol and the slide number right; change the footer text once in the slide master. The hero card (info blue, white text, an uppercase title over the short red rule) lifts one item per deck. No shadows, no emoji; one dominant yellow per slide besides the kicker.

To start a deck: copy the file, delete the sample slides you do not need, add slides from the layouts. In Google Slides, import the `.pptx` (File → Import slides, or open it from Drive and save as Google Slides); the layouts come with it and the fonts resolve from the Google Fonts catalog.

## 4. Construction

The templates are written by the scripts kept with [`bac-brand-assets`](https://github.com/buildacubesat/bac-utils/tree/main/tools/bac-brand-assets) in bac-utils (`templates/letterhead.js` and `templates/slides.js` on docx-js and pptxgenjs, `marks.py` for the marks (taken from `assets/png/`) and `surfaces.py` for the Mission viewport, `theme.py` for the deck's color scheme); the numbers above are theirs. A change goes into the script, the file is regenerated, and the version moves – a redesigned template is a new `v`, an adjusted one a new `r`.

## 5. Version history

| Version | Date | Change |
| :-- | :-- | :-- |
| Slides v1r2 | 2026-10-30 | The slides on the Mission surfaces of the Tooldance media kit: light layouts on `--space-paper` with paper wells and nebula top rules, dark layouts on the nebula photo instead of the rendered hero, the new `TITLE_ONLY_MISSION` layout with a timeline in Orbital Teal and BAC Yellow, a quote slide with a Plasma Rose mark, portrait and photo slot, a resources card on the contact sample; the slogan "Space for everyone". The letterhead stays at v1r1. |
| v1r1 | 2026-10-27 | First release: the letterhead redone on the v4r1 logo with Nunito Sans and IBM Plex Mono (the previous letterhead kept its layout and content, with `hello@buildacubesat.space` as the address), in English and German; the slides template with twelve layouts and a sample deck, replacing hand-placed slides on a single blank layout. |
