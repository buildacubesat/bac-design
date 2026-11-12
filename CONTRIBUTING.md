# Contributing to bac-design

bac-design holds the normative text of the BAC guides. A change of meaning – a new rule, a retired token – is made here first; the tools in [bac-utils](https://github.com/buildacubesat/bac-utils) follow it.

## 1. How Changes Land

- A guide change is made on a feature branch (`guides/<topic>`) and merged into `main` with `git merge --no-ff` – never squashed. From outside, open a pull request on GitHub.
- A guide change bumps that guide's version and adds a line at the top of its version history (Project & Tooling Guide §6); the guide table in `README.md` follows.
- `exports/` is rebuilt with `bac-design-export` from bac-utils. The Markdown in `guides/` is authoritative.
- `assets/` and `templates/` are written by `bac-brand-assets` in bac-utils and never edited by hand; a change goes into the generator.
- Title Case headings, American spelling, straight apostrophes, the Gedankenstrich (–) and no emoji.

## 2. Developer Certificate of Origin

BAC asks for no contributor license agreement. Instead, every commit is signed off under the [Developer Certificate of Origin](https://developercertificate.org/) (DCO): by signing off you certify that you wrote the change, or otherwise have the right to submit it under this repository's license, and that the contribution and your sign-off are kept on public record.

Sign off each commit:

```sh
git commit -s
```

This adds a line such as `Signed-off-by: Ada Lovelace <ada@example.org>` from your `user.name` and `user.email`. The address has to match the commit's author address. Signing off is not the same as signing a commit with a GPG or SSH key – it needs no key.

- You keep the copyright in your contribution.
- Your contribution is licensed under the license of the part you change – CC BY-SA 4.0 for the guides, checklists and templates (see `LICENSE.md`) – the same license everyone receives it under. Nothing is relicensed, and there is nothing else to sign.
- A check on every pull request fails if a commit has no sign-off matching its author. To sign off a branch you already pushed, run `git rebase --signoff <base>` with the branch you opened the pull request against (for example `origin/main`), then `git push --force-with-lease`. For the last commit alone, `git commit --amend -s --no-edit` is enough.

## 3. Code of Conduct

Everyone in BAC's spaces follows the [BAC Code of Conduct](guides/bac-code-of-conduct.md). Report a possible violation to conduct@buildacubesat.space.
