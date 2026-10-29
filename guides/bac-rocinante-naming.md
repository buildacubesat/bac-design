# Rocinante / Roci ''“ Software Stack Naming Note

**Build a CubeSat ''“ Internal Documentation** Version 0.1, 2026-07-14

This note documents the naming and branding convention for **Rocinante**, the product identity of BAC's flight software stack. It follows the Internal Tools Design Language Guide (v0.10) for naming, glyph, and versioning conventions, and should be read alongside that guide and the bac-software repo restructure issue.

## 1. What Rocinante is

Rocinante is the name of the software stack spanning both segments of BAC's onboard computing:

- **Flight segment** ''“ Zephyr RTOS running on STM32F405 MCU nodes (EPS board and others).

- **SBC segment** ''“ NASA F Prime running on Yocto Linux, on a Raspberry Pi CM5.

libcsp bridges the two segments; Yamcs handles the ground side and is out of scope for this naming note.

Rocinante is a **product identity**, not a repository name. It names the stack as a coherent thing a contributor or user can refer to ''“ "the Rocinante stack handles X" ''“ independent of where the code physically lives.

## 2. Naming rule

| **Context**                                              | **Form**                 |
|----------------------------------------------------------|--------------------------|
| First mention in a document or conversation              | **Rocinante**            |
| Subsequent mentions in the same document or conversation | **Roci**                 |
| Code namespace prefix                                    | lowercase roci or roci\_ |

This mirrors how **Build a CubeSat** shortens to **BAC** after first reference, and how bac is used as a lowercase code/filename prefix (Internal Tools Design Language Guide Â§2.3). Mixed case (Roci\_, ROCI, rOci) is never acceptable, consistent with the guide's blanket rule against mixed case in code and filenames.

**Examples:**

- Prose, first mention: *"The EPS node runs on Rocinante's flight segment."*

- Prose, thereafter: *"Roci handles telecommanding through libcsp."*

- Code: roci_eps, roci_hk_collector, roci::topology (namespace-appropriate casing per language convention, but the prefix itself is always lowercase roci).

- Commit / PR titles: treat as a proper noun, capitalized normally in a sentence ''“ *"Add Roci telemetry rate group for BNO086."*

## 3. Relationship to bac-software

Rocinante is **not** a repo rename ''“ at least not yet. This is an open question currently being worked through as part of the bac-software restructure issue that Gui is leading, which also covers:

- Whether the small/medium/large node concept from BAC's video content maps cleanly onto the flight-segment/SBC split.

- Whether the repo is renamed to reflect Rocinante externally, or keeps bac-software as its Codeberg name while Rocinante remains the internal product identity used in namespaces and documentation.

Until that's resolved, the working assumption is:

- **Repo name:** bac-software (unchanged, per the Internal Tools Design Language Guide Â§2.11 repo table).

- **Product identity inside the repo:** Rocinante / Roci, in namespaces, documentation headers, and prose.

This note should be updated once the restructure issue lands on a final answer.

## 4. Where this applies

- bac-docs documentation covering the flight software stack.

- Code comments, namespaces, and module names within bac-software.

- Codeberg issue and PR titles/descriptions referring to the stack as a whole.

- Discord and other community communications, following the project's normal warm/direct tone (Internal Tools Design Language Guide Â§2.3, Design System Specification Â§2).

It does **not** apply to:

- The bac-hardware or bac-structure repos, which are not part of the software stack.

- Yamcs (ground segment) or libcsp (third-party bridge library), which keep their own upstream names.

## 5. Open questions

- Repo naming (see Â§3) ''“ pending the restructure issue.

- Whether Rocinante gets its own logo/wordmark treatment, or stays a text-only product name nested under the BAC brand. No decision yet; default to text-only until specified.

## 6. Version history

| **Version** | **Date**   | **Change**                                                                                                   |
|-------------|------------|--------------------------------------------------------------------------------------------------------------|
| 0.1         | 2026-07-14 | Initial note. Documented Rocinante/Roci naming rule, relationship to bac-software, and scope of application. |
