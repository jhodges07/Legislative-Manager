# SPEC-003 — Kansas One-Hour Posting Rule

**Document ID:** SPEC-003 (provisional — confirm numbering with the Constitutional Engineering Office)  
**Title:** Kansas One-Hour Posting Rule  
**Classification:** Engineering Specification  
**Authority:** Constitutional Engineering Office  
**Owning Manager:** Legislative Manager (`MGR-LEG`)  
**Project ID:** PRJ-002  
**Governing Work Card:** `[PENDING — NO CWC-CE ISSUED]`  
**Governing Architecture:** ARCH-001; ARCH-002; ARCH-003; ARCH-004  
**Governing Policy:** POL-001  
**Governing Workflow:** WF-001  
**Governing Lifecycle:** STD-008  
**Governing Kansas Specification:** SPEC-001  
**Related Project:** None (independent of PRJ-001)  
**Jurisdiction:** State of Kansas  
**Status:** Proposed — Engineering Phase (Pre-Draft), awaiting CWC-CE  
**Version:** 0.3.0  
**Date:** 2026-10-31  

---

## 1. Purpose

This specification engineers **PRJ-002 — Kansas One-Hour Posting Rule**: a package family that would require the exact text of Kansas legislative measures to be publicly posted, in a permanent and verifiable repository, for at least one hour before official action, and would let public bodies use such repositories without violating the Kansas Open Meetings Act.

It defines objectives, scope, stakeholders, impacts, required artifacts, control affinities, review gates, risks and assumptions.

**This specification does not draft legislation.**  
**This specification does not draft constitutional language.**  
**This specification does not draft joint-rule text.**  
**This specification does not produce fiscal estimates.**  
**This specification does not publish.**

Concept material (non-operative model language) exists outside this repository in a Human Engineer working document and the Runtime-Republic Training course *The One-Hour Rule*. That material is reference input only. It is not an engineered artifact of this project and shall not be copied into a package until drafting is authorized (Section 7.2).

---

## 2. Objectives

### 2.1 Primary Engineering Objective

Establish a lifecycle-controlled package family that can later support Human Engineer-authorized drafting of Kansas instruments so that no bill, amendment, substitute, committee report or conference committee report is acted on unless its exact text has been publicly posted for at least one hour.

### 2.2 Supporting Objectives

1. Separate the three instrument layers: joint rule (`RES`), statute (`BILL` / `AMD`) and constitutional amendment (`CAP`)  
2. Identify all constitutional, statutory and legislative-rule impact surfaces before any operative text is drafted  
3. Engineer an Open Meetings Act safe harbor for communication in a public, permanently logged repository  
4. Engineer definitions (repository, version, version identifier, posted, official action) before drafting uses them  
5. Engineer fiscal-note structure for repository operation without inventing estimates  
6. Preserve ownership boundaries for AGCL, NBBF and CDT  

### 2.3 Human Engineer Decisions Already Recorded (2026-10-30)

| Decision | Effect on engineering |
|---|---|
| A two-thirds vote may skip the one-hour wait, but text must still be posted before the vote | Emergency path is a requirement for every layer |
| Legislature and Governor first; local bodies opt in | Local subdivisions are opt-in impact nodes, not mandatory targets |
| Sequence: joint rule, then statute, then constitutional amendment | Artifact roadmap follows this order |

### 2.4 Non-Objectives

1. Determine Kansas political outcomes  
2. Mandate any private vendor or platform  
3. Quantify costs in this phase  
4. Ratify, enact, adopt or publish anything  

---

## 3. Scope

### 3.1 In Scope (Pre-Draft Phase)

1. Project engineering definition for PRJ-002  
2. Identification of required artifacts and governing KLS standards  
3. Constitutional, statutory and joint-rule impact mapping  
4. AGCL / NBBF / CDT reference obligations  
5. Review-gate plan, risks, assumptions and roadmap  

### 3.2 Jurisdictional Scope

| Scope Element | Inclusion |
|---|---|
| Kansas Constitution | Impact analysis in scope; amendatory text out of scope |
| Kansas Statutes Annotated (open meetings, open records, legislative publication) | Impact identification in scope; bill text out of scope |
| Joint Rules of the Kansas Senate and House | Impact identification in scope; rule text out of scope |
| Counties, cities, school districts | Opt-in impact mapping only |
| Federal law | Out of scope |

### 3.3 Phase Boundary

This specification authorizes nothing by itself. A CWC-CE is required to activate this phase, and later CWC-CEs are required for drafting, citation verification, estimating and publication.

---

## 4. Stakeholders

| Stakeholder | Role in PRJ-002 |
|---|---|
| Human Engineer | Final approval authority for all gates |
| Legislative Manager (`MGR-LEG`) | Owning manager; package engineering |
| Budget Manager (`MGR-BDG`) | Declared peer for repository operating-cost structure |
| Publication Manager (`MGR-PUB`) | Declared peer for later publication handoff |
| Kansas Legislature (institutional) | Future adopting body for joint rules and statute; proposing body for the amendment |
| Office of Revisor of Statutes | Likely repository operator under a future statute; drafting conventions |
| Governor | Affected by presentment and signature requirements |
| Attorney General | KOMA and KORA enforcement and opinions |
| Counties, cities, school districts | Opt-in adopters |
| Kansas taxpayers and the public | Readers of posted text; not drafting authority |
| AGCL / NBBF / CDT control stewards | Control ownership remains in their repositories |

---

## 5. Constitutional Impacts

### 5.1 Impact Posture

A joint rule can be suspended by vote, and each house determines its own rules. A binding, non-suspendable requirement on the Legislature therefore presumes a **Constitutional Amendment Package (`CAP`)** under KLS-002.

### 5.2 Constitutional Impact Domains (Identification Only)

| Domain | Engineering Note | Citation Status |
|---|---|---|
| Each house determines the rules of its proceedings | Limits statute-only enforcement against internal legislative steps | Kansas Const. art. 2, § 8 — located; exact text to be verified in authorized research |
| Presentment, signature and veto timing | Statute requiring posting before presentment may interact with the ten-day presentment rule | Kansas Const. art. 2, § 14 — located; interaction `[TO BE VERIFIED]` |
| Amendment and ratification pathway | Two-thirds of members elected (or appointed) and qualified in each house, then majority of electors voting | Kansas Const. art. 14, § 1 — located; document pathway, do not simulate outcomes |
| Placement of new section | Target article and section number | `[TO BE VERIFIED]` |

### 5.3 Constitutional Engineering Rules for PRJ-002

1. CAP work shall not be disguised as a bill or joint rule.  
2. No constitutional language shall be drafted in this phase.  
3. Existing vs proposed constitutional language distinction is mandatory before drafting.  

---

## 6. Statutory and Legislative-Rule Impacts

### 6.1 Statutory Impact Domains (Identification Only)

| Domain | Likely Artifact Action | Citation Status |
|---|---|---|
| Open Meetings Act — definition of "meeting" | Amend to add repository safe harbor | K.S.A. 75-4317a — located |
| Open Meetings Act — coverage, notice, serial communications | Conforming analysis; KOMA covers the Legislature unless its rules provide otherwise | K.S.A. 75-4318(b), (f) — located via KLRD summary; text `[TO BE VERIFIED]` |
| Open Records Act — public records, retention | Amend or new section: repository content as permanent public record | K.S.A. 45-215 et seq.; 45-217 — located; retention loci `[TO BE VERIFIED]` |
| Revisor of Statutes duties | New section: repository operation | `[TO BE VERIFIED]` |
| Enrollment and presentment statutes | New or amended section: posted-version match before presentment | `[TO BE VERIFIED]` |
| Local governing body authority | New section: opt-in adoption | `[TO BE VERIFIED]` |

### 6.2 Legislative-Rule Impact Domains

| Domain | Likely Action | Citation Status |
|---|---|---|
| Joint Rule 1 — amending and suspending joint rules | Conforming change if posting rule is to resist suspension | 2025–2026 Joint Rules — located |
| Joint Rule 3(f) — conference report copies 30 minutes before consideration; two-thirds of members present may dispense | Replace or extend with posting requirement | 2025–2026 Joint Rules — located |
| Joint Rule 4(k) — bill-consideration deadline, suspendable by majority | Context only; not a posting rule | 2025–2026 Joint Rules — located |
| House and Senate rules | Conforming analysis | `[TO BE VERIFIED]` |

### 6.3 Engineering Rules

1. Existing-law analysis precedes revision drafting (KLS-003).  
2. No bill, amendatory or joint-rule text shall be drafted in this phase.  
3. Unknown loci shall be marked unresolved, not invented.  

---

## 7. Required Engineering Artifacts

All IDs below are **project production identifiers** for PRJ-002. They are not enactments.

| Artifact ID | Type | Layer / Class | Governing Standard | Current Target State |
|---|---|---|---|---|
| `[LAYER TBD]-RES-002` | `RES` | Joint rule resolution; layer not defined in SPEC-001 | SPEC-001 / KLS family | Proposed |
| `KS-STAT-BILL-002` | `BILL` | `KS-STAT` | KLS-001 | Proposed |
| `KS-STAT-AMD-002` | `AMD` | `KS-STAT` | KLS-003 | Proposed |
| `KS-STAT-MAP-002` | `MAP` | `KS-STAT` | KLS-003 | Proposed |
| `KS-CONST-CAP-002` | `CAP` | `KS-CONST` | KLS-002 | Proposed |
| `KS-DEF-REG-002` | Definition Register | Companion | KLS-005 | Proposed |
| `KS-FISC-NOTE-002` | Fiscal Note Package | Companion | KLS-004 | Proposed (structure only) |
| `KS-AUTH-MAP-002` | `MAP` | Authority / layer map | SPEC-001 | Required |
| `KS-CTRL-MAP-002` | `MAP` | AGCL / NBBF / CDT control map | SPEC-001 | Required |
| `KS-NODE-MAP-002` | `MAP` | Opt-in local-node map | KLS-004 / NBBF affinity | Required |
| `KS-PUB-COMP-002` | `PUB-COMP` | Publication Package | KLS-006 | Not assembled |

### 7.1 Artifact Relationship Graph

```text
[LAYER TBD]-RES-002 (joint rule)       — first in sequence; suspendable
        │
        ▼
KS-STAT-BILL-002 (KLS-001)             — repository, Governor, KOMA, KORA, local opt-in
        ├── carries ▶ KS-STAT-AMD-002 (KLS-003: K.S.A. 75-4317a and others)
        ├── uses ▶ KS-STAT-MAP-002, KS-DEF-REG-002, KS-AUTH-MAP-002, KS-CTRL-MAP-002, KS-NODE-MAP-002
        └── companion ▶ KS-FISC-NOTE-002 (KLS-004)
        │
        ▼
KS-CONST-CAP-002 (KLS-002)             — last in sequence; not suspendable by rule

All members (when ready) ▶ KS-PUB-COMP-002 (KLS-006) — publication not authorized
```

### 7.2 Engineer-Before-Draft Rule

No operative RES / BILL / AMD / CAP text may be drafted until:

1. A CWC-CE activates this specification  
2. A later CWC-CE / CEP expressly authorizes drafting  
3. Authority map and affected-loci research are provisionally complete or expressly deferred by the Human Engineer  
4. A definition register scaffold exists for the terms in Section 2.2(4)  

---

## 8. Required KLS Standards

| Standard | Requirement in PRJ-002 |
|---|---|
| KLS-001 | Mandatory for `KS-STAT-BILL-002` |
| KLS-002 | Mandatory for `KS-CONST-CAP-002` |
| KLS-003 | Mandatory for `KS-STAT-AMD-002` and `KS-STAT-MAP-002` |
| KLS-004 | Mandatory: repository operation has fiscal effects; estimates forbidden in this phase |
| KLS-005 | Mandatory for `KS-DEF-REG-002` |
| KLS-006 | Mandatory for later `KS-PUB-COMP-002`; no publication |
| — | No KLS standard governs joint-rule resolutions; gap recorded in Section 15 |

---

## 9. Required AGCL Controls

AGCL controls remain owned by **AGCL-Control-Documents**. PRJ-002 may reference, not redefine. Control titles below are as listed in SPEC-002; exact clause citations shall be completed in `KS-CTRL-MAP-002` under later authorized work.

| Control | Title | Why Required for PRJ-002 |
|---|---|---|
| `00G` | Transparency and Public Ledger Control | Core affinity: public, permanent, verifiable record of legislative text |
| `00H` | Constitutional Compatibility Control | Joint rule, statute and CAP must remain constitutionally coherent |
| `00I` | Enforcement and Remedy Control | Effect of acting on unposted text must be explicit |
| `00J` | Amendment and Version Control | Version identifiers and supersession of posted text |
| `00F` | Uncertainty and Black-Swan Stress Control | Emergency path and repository outage handling |

---

## 10. Required NBBF Controls

NBBF controls remain owned by **NBBF-Control-Documents**.

| NBBF Concern | Requirement in PRJ-002 |
|---|---|
| Node-scoped budgeting | Identify the node that funds and operates the repository |
| Authority boundaries | Opt-in local nodes retain their own authority |
| Transparency of burdens | Operating cost disclosed in `KS-FISC-NOTE-002`; no estimates in this phase |

---

## 11. Required CDT Mappings

CDT controls remain owned by **CDT-Control-Documents**. PRJ-002 requires CDT-ready metadata, not CDT runtime.

| Node Type | Example Nodes |
|---|---|
| Constitutional locus | Art. 2 § 8; Art. 2 § 14; Art. 14 § 1; new section (TBD) |
| Statutory locus | K.S.A. 75-4317a; 75-4318; 45-215 et seq. |
| Legislative-rule locus | Joint Rules 1, 3(f) |
| Artifact | RES, BILL, AMD, MAP, CAP, DEF, FISC, PUB |
| Version-of edge | Each posted text version to its measure |

---

## 12. Required Publication Artifacts

Publication is out of scope. `KS-PUB-COMP-002` requires a manifest, member freeze list, enactment disclaimer and Human Acceptance record before any future Published state.

---

## 13. Required Review Gates

| Gate | Authority | Required Before |
|---|---|---|
| HG-0 CWC-CE activation | Human Engineer | Any engineering under this SPEC |
| HG-1 CWC-CE for drafting | Human Engineer | Operative RES / BILL / AMD / CAP text |
| Engineering Review | Legislative Manager | Legal Review |
| Legal Review | Designated legal reviewer + Human Engineer oversight | Approved |
| Fiscal estimate authorization | Human Engineer (+ Budget Manager when Active) | Quantified fiscal values |
| HG-3 Human Acceptance | Human Engineer | Lifecycle advancement |
| Publication Approval | Human Engineer | Published state |

---

## 14. Risks

| Risk ID | Risk | Severity | Mitigation |
|---|---|---|---|
| R-001 | Joint rule suspended by vote when inconvenient | High | Sequence to statute and CAP; record suspension rule in `KS-AUTH-MAP-002` |
| R-002 | Statute unenforceable against internal legislative steps (art. 2 § 8) | High | CAP remains mandatory |
| R-003 | Presentment requirement conflicts with art. 2 § 14 timing | Medium | Verify before drafting Governor provisions |
| R-004 | Dependence on a single private platform | High | Require state-owned official repository; outside copies never control |
| R-005 | Repository outage blocks lawful action | Medium | Engineer outage and emergency handling with `00F` affinity |
| R-006 | KOMA safe harbor read as permitting deliberation without notice | High | Limit safe harbor to public, logged, non-binding communication; legal review |
| R-007 | Invented citations or estimates enter packages | High | Forbidden; unknowns recorded |
| R-008 | Concept material treated as approved text | Medium | Section 1 boundary; engineer-before-draft rule |

---

## 15. Assumptions and Open Items

1. Human Engineer intends PRJ-002 as a real Kansas package family.  
2. All three layers (joint rule, statute, constitutional amendment) are required until verified otherwise.  
3. **Open:** SPEC-001 defines no layer ID for joint-rule resolutions; Human Engineer to decide the layer and ID for `RES-002`.  
4. **Open:** No KLS standard governs joint-rule resolutions; decide whether one is needed.  
5. **Open:** SPEC number and governing CWC-CE to be issued by the Constitutional Engineering Office.  
6. **Open:** Hashing or version-identifier method to be named in law or by reference.  
7. UNBKE is not required.  

---

## 16. Roadmap

| Phase | Output | Gate |
|---|---|---|
| 0 — Proposed (this document) | Project specification | HG-0 CWC-CE activation |
| 1 — Pre-Draft engineering | Authority, control and node maps; definition register scaffold; verified citations | Engineering Review |
| 2 — Authorized drafting: joint rule | `RES-002` | HG-1 |
| 3 — Authorized drafting: statute | `KS-STAT-BILL-002`, `KS-STAT-AMD-002`, fiscal note structure | HG-1 |
| 4 — Authorized drafting: constitutional amendment | `KS-CONST-CAP-002` | HG-1 |
| 5 — Review and publication package | `KS-PUB-COMP-002` | Legal Review, HG-3, Publication Approval |

---

## 17. Sources Located (Not Yet Verified Under Authorized Research)

- [Kansas Legislature Joint Rules, 2025–2026](https://www.kslegislature.gov/li/s/pdf/joint_rules.pdf)  
- [KLRD: Kansas Open Meetings Act](https://klrd.gov/kansas-open-meetings-act/)  
- [K.S.A. 75-4317a](https://law.justia.com/codes/kansas/2017/chapter-75/article-43/section-75-4317a/)  
- [Kansas Constitution, Article 14, Section 1](https://ksrevisor.gov/kanconst/093_014_0001.html)  
- [Kansas Constitution, Article 2 (Ballotpedia)](https://ballotpedia.org/Article_2,_Kansas_Constitution)  
- [Revisor of Statutes KOMA and KORA memo, 2025-01-21](https://kslegislature.gov/li/b2025_26/committees/ctte_h_trnsprt_1/documents/testimony/20250121_02.pdf)  

---

## 18. Contributor Readiness and Access

Outside contributors (reviewers who are not the Human Engineer) are admitted to PRJ-002 work only after showing that they understand the project's goal, and then in stages. This section governs who may read, comment on, or propose changes to PRJ-002 material. It grants no drafting authority; Section 7.2 and Section 13 still govern drafting.

### 18.1 Readiness Check

A person is ready for Level 1 access when they pass both parts:

| Part | Requirement | Scored by |
|---|---|---|
| A. Lesson quizzes | At least 3 of 4 correct on each of: Runtime-Republic Training, *The One-Hour Rule* Lessons 01–05 and *Reading the Draft* Lessons 01–02 | The quiz form, automatically |
| B. Explain it back | A pass on three written questions: (1) the problem PRJ-002 solves and why a joint rule alone cannot fix it; (2) the four safe-harbor conditions and why votes stay out of the repository; (3) one real weakness in the draft and a proposed fix | Human Engineer, using the scoring guide kept with the Readiness Check form |

Part B rewards understanding, not agreement: a candidate may disagree with the draft and still pass. The answer keys and scoring guide are kept with the Human Engineer's Readiness Check form, not in this repository.

### 18.2 Access Levels

| Level | May | Granted by | Requires |
|---|---|---|---|
| 1. Reviewer | Read the model language document and comment on its clauses | Human Engineer shares the document | Readiness Check passed |
| 2. Contributor | Open issues (Review Comment or Proposed Change template); reading needs no grant because this repository is public | Human Engineer records the person's GitHub username at Level 2 | Level 1, plus useful, sourced review comments |
| 3. Proposer | Propose changes by branch and pull request | Human Engineer grants GitHub write access | Level 2, plus useful issues |

At every level the contributor proposes and the Human Engineer decides. Only the Human Engineer merges, approves, or advances lifecycle state (WF-001, STD-008).

### 18.3 Conditions

1. A person who holds public office is told before Level 1 that their comments about official business may be public records under the Kansas Open Records Act, and that discussion among a majority of one public body belongs in a noticed meeting.
2. Access is reviewed when a contributor's work stops meeting the level's standard; the Human Engineer may lower or remove it.
3. AI assistants used by contributors follow the same rule: they may draft and review, never approve.
4. Each grant and removal is recorded by the Human Engineer, with name, level and date.
5. This repository is public by design. Issues and pull requests from people not recorded at Level 2 or 3 may be closed by the Human Engineer without review.

## Version History

| Version | Date | Summary |
|---|---|---|
| 0.1.0 | 2026-10-30 | Proposed project specification for PRJ-002; awaiting CWC-CE. No operative text. |
| 0.2.0 | 2026-10-30 | Added Section 18, Contributor Readiness and Access (Human Engineer's direction). No operative text. |
| 0.3.0 | 2026-10-31 | Section 18: Level 2 redefined for a public repository (no read grant; recorded username may open issues); Condition 5 added (Human Engineer's direction). No operative text. |
