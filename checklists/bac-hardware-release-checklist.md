# BAC Hardware Release Checklist

The steps for releasing one or more boards from a bac-hardware feature branch. Conventions: Project & Tooling Guide §2.1 (licensing), §2.2 (versioning and merging), §2.11 (status labels). Git is this checklist's history.

**Preparation**

0. Pick names – used everywhere:
   - `[display]`: Board Name vVrR
   - `[tag]`: subsystem-board-name-vVrR, e.g. `eps-main-board-v2r3`

1. Make sure you are on the correct feature branch
   ```
   git branch
   git switch <branch>
   ```
2. Pull latest changes
   ```
   git pull
   ```
3. Prune local tags
   ```
   git fetch --prune --prune-tags
   ```

---

**Artifacts & Documentation** *(repeat for each board)*

4. Run artifact generation
   ```
   bac-kicad-generate-artifacts [projectfolder] --ibom
   ```
5. Check all output files on the Desktop
6. If needed: manually make pinout graphic
7. If BOM: make manual corrections and notes, upload to DigiKey for a public list, add tags like `[tag]` or e.g. `devkit-v1` if part of an assembly – copy the public list URL for use in step 10 and the release
8. Make or update README from template (bac-docs `templates/`)
   - Add DigiKey public list URL as sourcing instructions link
9. Update repo README: board index, version and status label (`TESTING` for a pre-release, `RELEASED` once final)
10. Make or update release summary from template (bac-docs `templates/`)
    - Add DigiKey public list URL as sourcing instructions link
11. Make or update bac-page URL:
    ```
    bac-page [docs-url] "[tag]"
    ```
    *(use `--edit` flag to regenerate QR code)*
12. Make or update the docs entry on docs.buildacubesat.space *(once the site is live)*

---

**Git Workflow** *(repeat for each board)*

13. Check nothing unwanted is staged
    ```
    git status
    ```
14. Make release commit
    - Update revision history in README
    - Commit message: `[tag]`
15. Make signed tag
    ```
    git tag -s [tag] -m "Release [display]"
    ```
16. Verify the tag signature
    ```
    git tag -v [tag]
    ```
17. Repeat steps 4–16 for all remaining boards in the branch

18. Push commits and tags
    ```
    git push
    git push --tags
    ```

---

**Codeberg Releases** *(repeat for each board)*

19. Create Codeberg release from tag
    - Title: `[display]`
    - Upload artifacts from Desktop (gerbers ZIP, schematic PDF, BOM CSV, BOM HTML, position file `.pos`, STEP, render WebP)
    - Upload the PCBWay fabrication and assembly instructions (`.md`)
    - Paste release summary
    - Add DigiKey public list URL as sourcing instructions link
    - Tick **pre-release** if releasing for testing before merge

    *If pre-release: test, push fixes to feature branch, retag (e.g. `rc2`) and update release as needed. Once finalised, create the proper release tag and uncheck pre-release before proceeding.*

20. Open the release page and verify tag, artifacts, and release notes look correct

---

**Merge**

21. Switch to main and pull
    ```
    git switch main
    git pull
    ```
22. Merge feature branch with a descriptive commit
    ```
    git merge --no-ff <branch> -m "merge: <branch description> into main

    - Board Name vVrR (brief description)
    - Board Name vVrR
    ..."
    ```
23. Push
    ```
    git push
    ```
    *Tags travel with their commits – all releases now point to commits reachable from `main`. Never squash and never rebase a tagged branch: either leaves the tags off `main`.*

24. Delete the feature branch
    ```
    git branch -d <branch>
    git push origin --delete <branch>
    ```

---

**Promotion**

25. Announce and promote the release:
    - Post in Discord (release summary + Codeberg release link)
    - YouTube post or short
    - *(Future)* Update store page
    - Update the docs entry if not done in step 12 *(once the site is live)*
