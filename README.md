# Legislative Manager

Legislative Manager is a controlled legislative-engineering environment for designing, structuring, reviewing, and packaging Kansas legislative work under Constitutional Engineering Office governance.

It provides the engineering factory in which bills, constitutional amendment packages, statutory revisions, definitions, fiscal-note packages, maps, and publication packages are prepared before any Human Engineer approval or public release.

---

## Mission

This repository exists to engineer:

- bills
- constitutional amendment packages
- statutory revisions
- legislative definitions
- fiscal-note packages
- supporting maps and traceability records
- publication-ready legislative packages

The mission is engineering integrity: authority is cited, unknowns are identified, lifecycle states are controlled, and no package advances by implication.

---

## What Legislative Manager Is

Legislative Manager is the specialized manager repository that performs legislative engineering.

It holds:

- Kansas legislative engineering standards
- project specifications and production packages
- manager prompts and certification records
- proof-of-concept validation materials
- jurisdiction-organized template surfaces

Work in this repository is intended to be metadata-complete, versioned, reviewable, and traceable from source authority through engineered artifacts.

---

## What Legislative Manager Is Not

- It does **not** enact law.
- It does **not** replace elected legislative authority.
- AI does **not** approve legislation.
- Publication does **not** equal enactment.
- Human Engineer approval gates remain controlling at every material progression point.

Presence of an artifact in this repository—whether drafted, committed, or packaged—does not make it Kansas law.

---

## Constitutional Engineering Relationship

```text
Constitutional-Engineering
        ↓
Legislative-Manager
        ↓
Legislative Projects
        ↓
Engineered Legislative Artifacts
```

**Constitutional-Engineering** establishes architecture, policy, standards, workflows, and Office-level governance.

**Legislative-Manager** performs legislative engineering under that governance.

Legislative projects live here as production work packages. Engineered legislative artifacts are produced from those projects according to Kansas legislative standards and Office approval gates.

---

## Legislative Engineering Lifecycle

```text
Need Identified
    ↓
Project Specification
    ↓
Authority / Control Research
    ↓
Definitions
    ↓
Constitutional / Statutory Engineering
    ↓
Fiscal Analysis
    ↓
Engineering Review
    ↓
Human Acceptance
    ↓
Publication Package
```

Later stages may include legal review, public review, and approved publication through a separately controlled publication surface. Lifecycle progression remains subject to Human Engineer approval.

---

## Repository Structure

| Directory | What you should expect |
|---|---|
| [`certifications/`](certifications/) | Manager certification records documenting that Legislative Manager meets Engineering Office readiness requirements for its declared scope. |
| [`kansas-standards/`](kansas-standards/) | The Kansas Legislative Engineering Library (KLS-001 through KLS-006). These are the binding engineering rules for Kansas packages. |
| [`poc/`](poc/) | Proof-of-concept materials validating that the KLS library can operate together as a complete package family without drafting real legislation. |
| [`projects/`](projects/) | Production legislative projects. Each project contains specifications and, over time, engineered artifact packages for a real subject. |
| [`prompts/`](prompts/) | Operating prompts and agent instructions used by Legislative Manager and related declared manager surfaces. |
| [`specifications/`](specifications/) | System-level Kansas engineering specifications that define architecture for Kansas constitutional and legislative engineering. |
| [`templates/`](templates/) | Jurisdiction-organized template surfaces (Federal, State, County, City, School) for future package placement and reusable structure. |

---

## Kansas Legislative Engineering Library

Kansas legislative packages in this repository are governed by the KLS library:

| Standard | Description |
|---|---|
| [KLS-001](kansas-standards/KLS-001-Kansas-Bill-Engineering-Standard.md) — Kansas Bill Engineering Standard | Rules for engineering Kansas bill packages before and during statutory drafting work. |
| [KLS-002](kansas-standards/KLS-002-Kansas-Constitutional-Amendment-Engineering-Standard.md) — Kansas Constitutional Amendment Engineering Standard | Rules for constitutional amendment packages (`CAP`), including exact targeting and ratification-process documentation without simulating outcomes. |
| [KLS-003](kansas-standards/KLS-003-Kansas-Statutory-Revision-Engineering-Standard.md) — Kansas Statutory Revision Engineering Standard | Rules for revising existing statutes, including dependency analysis, cross-references, and renumbering/repeal discipline. |
| [KLS-004](kansas-standards/KLS-004-Kansas-Fiscal-Note-Engineering-Standard.md) — Kansas Fiscal Note Engineering Standard | Rules for fiscal-note package structure, assumptions, uncertainty disclosure, and node-impact mapping without inventing data. |
| [KLS-005](kansas-standards/KLS-005-Kansas-Legislative-Definitions-Engineering-Standard.md) — Kansas Legislative Definitions Engineering Standard | Rules for definition ownership, reuse, conflict detection, and version history across legislative packages. |
| [KLS-006](kansas-standards/KLS-006-Kansas-Legislative-Publication-Package-Engineering-Standard.md) — Kansas Legislative Publication Package Engineering Standard | Rules for assembling complete publication packages while preserving member identity and completeness-before-publication discipline. |

---

## Current Production Project

### PRJ-001 — Kansas Property Tax Elimination

PRJ-001 is the first real production Government Engineering project managed through this repository.

**Status:** Engineering Phase — Pre-Draft

**Project specification:**

[projects/PRJ-001-Kansas-Property-Tax-Elimination/SPEC-002-Kansas-Property-Tax-Elimination.md](projects/PRJ-001-Kansas-Property-Tax-Elimination/SPEC-002-Kansas-Property-Tax-Elimination.md)

No operative bill text has yet been authorized under the project specification.

The current phase defines objectives, scope, stakeholders, constitutional and statutory impact domains, required artifacts, control affinities, review gates, risks, and the roadmap. Drafting of operative legislative or constitutional language requires later explicit authorization.

---

## PRJ-001 Planned Artifact Family

| Artifact ID | Role |
|---|---|
| `KS-CONST-CAP-001` | Constitutional Amendment Package |
| `KS-STAT-BILL-001` | Kansas Bill |
| `KS-STAT-AMD-001` | Statutory Revision Package |
| `KS-STAT-MAP-001` | Statutory Dependency / Cross-Reference Map |
| `KS-FISC-NOTE-001` | Fiscal Note Package |
| `KS-DEF-REG-001` | Legislative Definition Register |
| `KS-AUTH-MAP-001` | Authority Map |
| `KS-CTRL-MAP-001` | Control Traceability Map |
| `KS-NODE-MAP-001` | Government Node Impact Map |
| `KS-PUB-COMP-001` | Legislative Publication Package |

These identifiers describe the planned package family. They are engineering identities, not enacted law.

---

## AGCL / NBBF / CDT Relationship

Legislative-Manager references three related control systems without assuming ownership of their control documents:

**AGCL**  
Provides governing liberty, property-rights, authority-limits, transparency, and related control affinities used when legislative packages implicate those structures.

**NBBF**  
Provides node-based fiscal and budgeting affinities used when packages affect government nodes, fiscal authority boundaries, exit conditions, or sunset/renewal mechanics.

**CDT**  
Provides future constitutional-digital-twin metadata and relationship-traceability affinities so engineered packages remain model-ready without depending on a completed runtime.

Control ownership remains with the respective control-document repositories. Legislative-Manager may cite and map; it does not redefine or absorb those controls.

---

## Traceability

Intended engineering chain:

```text
Source Authority
    ↓
Control Document
    ↓
Engineering Requirement
    ↓
Project Specification
    ↓
Legislative Artifact
    ↓
Verification
    ↓
Human Acceptance
```

Traceability matters because legislative engineering must remain attributable. Reviewers should be able to answer:

- what authority is claimed
- which controls apply
- which requirement produced the artifact
- what was verified
- who accepted progression

Where authority is unknown or conflicted, the unknown is recorded rather than invented.

---

## AI Governance

- AI assists engineering.
- AI does not own authority.
- AI does not approve.
- AI does not invent legal authority.
- Unknowns must be identified.
- Human approval gates control progression.

AI may prepare structures, maps, drafts under authorization, and reports. AI may not grant Human Acceptance, publication approval, or legal enactment.

---

## Repository Status

| Field | Value |
|---|---|
| Baseline | 1.0 |
| Branch | `main` |
| Repository | Private Engineering Repository |
| Primary Manager | Legislative Manager (`MGR-LEG`) |
| Current Production Project | PRJ-001 — Kansas Property Tax Elimination |

---

## How to Navigate

**To understand the engineering rules:**  
→ [`kansas-standards/`](kansas-standards/)

**To see the current real project:**  
→ [`projects/PRJ-001-Kansas-Property-Tax-Elimination/`](projects/PRJ-001-Kansas-Property-Tax-Elimination/)

**To understand Kansas system architecture:**  
→ [`specifications/`](specifications/)

**To review proof-of-concept validation:**  
→ [`poc/`](poc/)

**To inspect manager certification:**  
→ [`certifications/`](certifications/)

---

## Publication Boundary

This repository is the engineering factory.

Approved public-facing legislative material may later be released through a separately controlled publication surface.

Internal engineering artifacts and public legislative presentation shall remain distinguishable. Packaging for publication under KLS-006 does not, by itself, enact law or authorize public release.

---

## Disclaimer

This repository contains engineering and policy-development artifacts.

Nothing contained here is enacted Kansas law merely because it exists, is committed, or is published.

Legal enactment occurs only through the applicable constitutional and legislative processes.

---

## Version History

| Version | Date | Summary |
|---|---|---|
| 1.0.0 | 2026-08-08 | Initial Legislative-Manager repository front door. |
