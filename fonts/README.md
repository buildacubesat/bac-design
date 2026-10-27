# Fonts

The three families of the BAC Identity Guide §3, self-hosted so that every surface and tool that must work offline – the brand-asset generator, the guide exports, a console without network – uses the same files the web surfaces load from Google Fonts.

| Family | Role (Identity Guide §3) | Files | Source |
| :-- | :-- | :-- | :-- |
| Nunito | Wordmark only (`--font-logo`), set at weight 350 | `Nunito[wght].ttf`, `Nunito-Italic[wght].ttf` – variable, 200–1000 | [googlefonts/nunito](https://github.com/googlefonts/nunito), v3.602 |
| Nunito Sans | Headings 500, body 400 (`--font-display`, `--font-body`) | `NunitoSans[YTLC,opsz,wdth,wght].ttf`, `NunitoSans-Italic[YTLC,opsz,wdth,wght].ttf` – variable | [googlefonts/NunitoSans](https://github.com/googlefonts/NunitoSans) |
| IBM Plex Mono | Labels, figures, code (`--font-mono`) | `IBMPlexMono-Regular.ttf`, `-Italic`, `-Medium`, `-SemiBold`, `-Bold` – static, the weights the stylesheet imports | [IBM/plex](https://github.com/IBM/plex) |

Variable files cover every weight the guides use, including the wordmark's 350, which the Google Fonts import does not serve. The static Plex Mono files are the five faces `@import` loads; Plex ships no variable mono.

## License

All three families are licensed under the SIL Open Font License 1.1 – `OFL-Nunito.txt`, `OFL-NunitoSans.txt`, `OFL-IBMPlexMono.txt` beside the files. The OFL permits bundling, embedding in PDFs and outlining into artwork; it does not permit selling the fonts on their own. The fonts are not BAC Marks and not covered by the repository's CC BY-SA 4.0 licence; they keep their own.
