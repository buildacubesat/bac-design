# Rocinante / Roci – Software Stack Naming Note

**Build a CubeSat – flight software naming convention** Version 0.2, 2026-10-29

This note documents the naming convention for **Rocinante**, the product identity of BAC's flight software stack. It applies the naming, versioning and glyph conventions of the BAC Project & Tooling Guide (§2.2, §2.3, §2.6) and the voice of the BAC Identity Guide (§2); the Rocinante marks are defined in the Identity Guide §8 and covered by the BAC Trademark Policy §2. The guides live in bac-design (https://github.com/buildacubesat/bac-design).

## 1. What Rocinante Is

Rocinante is the name of the software stack running on BAC's onboard computers. It spans the three node classes of the BAC Project Overview §5.2:

- **Small nodes** – Zephyr RTOS on small, energy-efficient MCUs for deterministic subsystem control: always-on nodes such as the EPS MCU, and sensor heads.

- **Medium nodes** – Zephyr and NASA F Prime on larger MCUs for more demanding flight tasks such as FDIR and COMMS.

- **Large nodes** – Linux and NASA F Prime on higher-capability compute hardware such as the Raspberry Pi CM5; payload nodes.

The MicroMod carrier serves small and medium nodes, the CM5 carrier large nodes. STM32F405 processor boards are supported first, STM32U5 later. Nodes talk through a shared protocol boundary – CSP over CAN – rather than running one framework everywhere. The ground segment is out of scope for this note.

Rocinante is a **product identity**, not a repository name. It names the stack as a coherent thing a contributor or user can refer to – "the Rocinante stack handles X" – independent of where the code lives.

## 2. Naming Rule

| **Context**                                              | **Form**                |
|----------------------------------------------------------|-------------------------|
| First mention in a document or conversation              | **Rocinante**           |
| Subsequent mentions in the same document or conversation | **Roci**                |
| C and C++ identifiers, files, modules                    | lowercase roci\_ prefix |
| Kconfig symbols                                          | CONFIG_ROCI\_\*         |
| F Prime namespace                                        | Roci                    |

This mirrors how **Build a CubeSat** shortens to **BAC** after first reference, and how bac is used as a lowercase code and file name prefix (Project & Tooling Guide §2.3). Where a language or framework fixes the casing – uppercase Kconfig symbols, PascalCase F Prime namespaces – the prefix follows it. Within one identifier the casing is never mixed, and prose never writes Roci\_, rOci or ROCI.

**Examples:**

- Prose, first mention: *"The EPS node runs Rocinante on a small node."*

- Prose, thereafter: *"Roci handles telecommanding over CSP."*

- Code: roci_eps, roci_hk_collector, CONFIG_ROCI_HEARTBEAT, Roci::Topology.

- Commit and PR titles: treat as a proper noun, capitalized normally in a sentence – *"Add Roci telemetry rate group for BNO086."*

## 3. Relationship to bac-software

Rocinante is not a repository rename. The question is settled by the bac-software docs split (bac-software #105):

- **Repository:** bac-software keeps its name (Project & Tooling Guide §2.8).

- **Product identity inside the repository:** Rocinante / Roci, in namespaces, documentation headers and prose.

- **Document IDs** stay BAC-FSW-\* and BAC-SBC-\*, with their own version numbers (Project & Tooling Guide §2.2).

- **New code** uses the roci\_ prefix, CONFIG_ROCI\_\* and the Roci F Prime namespace. Existing bac\_ identifiers are renamed in a retrofit tracked as its own issue, not in passing.

## 4. Where This Applies

- bac-docs documentation covering the flight software stack.

- Code comments, namespaces and module names within bac-software.

- Codeberg issue and PR titles and descriptions referring to the stack as a whole.

- Discord and other community communication, in the project's plain-spoken voice (Identity Guide §2).

It does **not** apply to:

- bac-hardware or bac-structure, which are not part of the software stack.

- Third-party components – Zephyr, F Prime, libcsp, the ground segment software – which keep their upstream names.

## 5. Marks

Rocinante has its own marks at v2r1 – the horse head in a ring, the ROCINANTE wordmark over CUBESAT SOFTWARE STACK, and their stacked lockup – in bac-design `assets/` (`rocinante-*`), constructed as the Identity Guide §8 describes. They are BAC Marks under the BAC Trademark Policy and are not covered by the open licenses.

## 6. Version History

| **Version** | **Date**   | **Change** |
|-------------|------------|------------|
| 0.2         | 2026-10-29 | Moved from Google Drive into bac-design `guides/`. §1: the three node classes replace the flight and SBC segments; MicroMod and CM5 carriers; STM32F405 first, STM32U5 later; CSP over CAN. §2: CONFIG_ROCI\_\* and the Roci F Prime namespace. §3: settled by bac-software #105 – the repository stays bac-software, document IDs stay BAC-FSW-\* and BAC-SBC-\*, the bac\_ retrofit as its own issue. §5: the Rocinante marks, replacing the open question on a logo. References to the current guide names. Title Case headings, American spelling. |
| 0.1         | 2026-07-14 | Initial note. Documented Rocinante/Roci naming rule, relationship to bac-software, and scope of application. |
