# KLS-003 — Kansas Statutory Revision Engineering Standard

**Document ID:** KLS-003  
**Title:** Kansas Statutory Revision Engineering Standard  
**Classification:** Kansas Legislative Engineering Standard  
**Authority:** Constitutional Engineering Office  
**Owning Manager:** Legislative Manager (`MGR-LEG`)  
**Governing Architecture:** ARCH-001 — Constitutional Engineering Architecture  
**Governing Manager Architecture:** ARCH-002 — Engineering Manager Architecture  
**Governing Ownership Architecture:** ARCH-003 — Engineering Ownership Architecture  
**Governing Interface Architecture:** ARCH-004 — Engineering Interface Architecture  
**Governing Policy:** POL-001 — Engineering Office Governance Policy  
**Governing Workflow:** WF-001 — Engineering Office Operating Workflow  
**Governing Lifecycle Standard:** STD-008 — Legislative Lifecycle Standard  
**Governing Specification:** SPEC-001 — Kansas Constitutional Engineering Specification  
**Related Kansas Standards:** KLS-001 — Kansas Bill Engineering Standard; KLS-002 — Kansas Constitutional Amendment Engineering Standard  
**Governing Prompt:** Legislative Manager Operating Manual  
**Jurisdiction:** State of Kansas  
**Status:** Draft  
**Version:** 1.0.0  
**Effective Date:** 2026-08-08  

---

## 1. Purpose

This document establishes the canonical engineering standard governing revisions to existing Kansas statutes engineered by the Legislative Manager.

It exists to ensure that every Kansas statutory revision package:

1. Analyzes existing law before revising it  
2. Identifies downstream impacts and dependencies  
3. Preserves or expressly updates cross-reference integrity  
4. Keeps renumbering fully traceable  
5. Coordinates repeals with dependency analysis  
6. Maintains structural integrity across affected statutory loci  
7. Remains compatible with constitutional and control-document boundaries  
8. Supports future CDT and UNBKE integration without hard runtime dependency  

KLS-003 does not draft legislation and does not invent legal authority.

---

## 2. Scope

### 2.1 In Scope

This standard applies to Kansas statutory revision engineering under Legislative Manager, including:

1. Revision packages amending existing Kansas Statutes (`KS-STAT`)  
2. Composite revision packages combining amendments, repeals, renumbering, and conforming cross-reference updates  
3. Dependency, cross-reference, and impact-analysis records for those revisions  
4. Review, publication packaging, version management, and lifecycle control of the above  

Artifact types commonly used under this standard:

| Type | Use under KLS-003 |
|---|---|
| `AMD` | Primary statutory amendment/revision actions |
| `BILL` | Carrier package when revision is introduced as a bill under KLS-001 |
| `ACT` | Enacted/enactment-ready representation when authorized |
| `MAP` | Dependency and cross-reference maps |

### 2.2 Out of Scope

This standard does not:

1. Draft bill/amendment text, enact law, or determine Kansas political outcomes  
2. Govern constitutional amendment packages as primary subject matter (see KLS-002)  
3. Replace KLS-001 for new-law bill package architecture when a revision is carried as a bill; both may apply  
4. Govern county/city/school charter packages as primary subject matter  
5. Modify KLS-001, KLS-002, Engineering Office documents, AGCL, NBBF, or CDT  
6. Require UNBKE or any specific drafting tool  

### 2.3 Relationship to Other Authorities

```
ARCH-001 / ARCH-002 / ARCH-003 / ARCH-004
        ↓
POL-001 / WF-001 / STD-008 / STD-014 / STD-015
        ↓
SPEC-001 (Kansas Constitutional Engineering Specification)
        ↓
KLS-001 (bills) / KLS-003 (statutory revisions) / KLS-002 (constitutional amendments)
        ↓
Kansas statutory revision packages under Legislative Manager
```

Where a revision is packaged as a Kansas bill, KLS-001 and KLS-003 both bind.  
Where conflict appears among applicable Kansas standards, stop and escalate to the Human Engineer.  
Office architecture, policy, standards, and workflow remain superior to manager-local Kansas standards.

---

## 3. Authority

1. KLS-003 is issued under Constitutional Engineering Office authority and owned by Legislative Manager.  
2. KLS-003 is subordinate to ARCH-001 through ARCH-004, POL-001, WF-001, STD-008, and SPEC-001.  
3. Kansas constitutional and statutory law remain the legal source of governing truth for Kansas content.  
4. AGCL, NBBF, and CDT remain owned by their control repositories; KLS-003 authorizes reference, not ownership.  
5. AI may prepare revision packages under authorized work; AI never owns the packages and never grants Human Engineer approval.  
6. AI shall not fabricate existing statutory text, citations, dependency conclusions, or cross-reference validity.  
7. Production use proceeds through WF-001 authorization gates.

---

## 4. Revision Package Architecture

### 4.1 Existing-Law-First Rule

Existing law shall be analyzed before revision.  
No operative revision drafting shall begin until the Existing Law Analysis (Section 6) is established for each primary target.

### 4.2 Engineer-Before-Draft Sequence

1. Confirm authorizing CWC-CE / CEP  
2. Assign identity, layer `KS-STAT`, revision classification, version, and placement  
3. Complete Existing Law Analysis for primary targets  
4. Complete Dependency Analysis and Cross-Reference Integrity map  
5. Define repeal coordination and renumbering plan where applicable  
6. Record constitutional/control applicability  
7. Only then draft authorized revision language  

### 4.3 Logical Package Structure

```
Statutory Revision Package
├── Identity / Manifest
├── Engineering Summary
├── Revision Classification
├── Existing Law Analysis
├── Dependency Analysis
├── Cross-Reference Integrity Map
├── Revision Actions
│   ├── Amendments
│   ├── Conforming updates
│   ├── Renumbering map
│   └── Repeals / repeal-and-replace
├── Proposed Law (existing vs proposed distinction)
├── Version Management Record
├── Constitutional Compatibility
├── Control Integration (AGCL / NBBF / CDT)
├── CDT Metadata
├── Traceability Block
├── Review Records
├── Publication Package (when prepared)
└── Version History
```

### 4.4 Recommended Repository Placement

Per SPEC-001, Kansas statewide statutory packages should be placed under:

```text
Legislative-Manager/templates/State/Kansas/
```

or a successor Kansas state tree authorized under approved work.  
Exact subdirectory creation occurs only under authorized CWC-CE / CEP scope.

### 4.5 Carrier Package Rule

When a revision is introduced through a bill package:

1. KLS-001 governs bill package architecture and bill-specific requirements  
2. KLS-003 governs revision analysis, dependency, cross-reference, renumbering, and repeal coordination  
3. The bill package shall either embed or clearly reference the KLS-003 analysis artifacts  

---

## 5. Revision Classification

Every revision package shall declare one primary class and may declare secondary classes.

| Class | Code | Meaning |
|---|---|---|
| Substantive Amendment | `REV-SUB` | Changes legal duties, rights, powers, prohibitions, or scope |
| Clarifying / Nonsubstantive | `REV-CLAR` | Purports to clarify without changing legal effect; still requires impact analysis |
| Conforming Amendment | `REV-CONF` | Updates text solely to conform to another primary change |
| Repeal | `REV-REP` | Removes statutory authority in whole or part |
| Repeal-and-Replace | `REV-RR` | Removes and substitutes authority |
| Renumbering / Reorganization | `REV-REN` | Relocates or renumbers without intended substantive change, unless combined with other classes |
| Composite Revision | `REV-COMP` | Combination of two or more classes |

### 5.1 Classification Rules

1. Classification shall reflect actual engineering intent, not convenience.  
2. A package labeled `REV-CLAR` that changes legal effect is misclassified and nonconforming.  
3. Composite packages shall list each included class and map each action unit to a class.  
4. Constitutional change shall not be classified as statutory revision; use KLS-002.

### 5.2 Action Unit Identifiers

Number discrete revision actions:

```text
SR-NNN
```

Each `SR-NNN` unit shall identify exact affected statutory locus, class, and linked dependency/cross-reference impacts.

---

## 6. Existing Law Analysis

### 6.1 Analysis Mandate

Existing law shall be analyzed before revision.

### 6.2 Required Analysis Fields per Primary Target

| Field | Requirement |
|---|---|
| Target citation | Exact K.S.A. chapter/section/subsection/paragraph when known |
| Catchline / title | If known |
| Current text source | Cited source authority for current law |
| Current text extract | Quoted or precisely referenced current law |
| Operative function summary | Engineering summary of what the provision currently does |
| Defined terms relied upon | Local or imported definitions affecting meaning |
| Known related provisions | Sibling/parent/child statutory relationships |
| Uncertainty | `[CITATION/TEXT NEEDED]` or equivalent when incomplete |

### 6.3 Existing Law Rules

1. Do not invent current statutory text.  
2. Partial extracts shall be labeled partial and note omitted-context risk.  
3. If current text cannot be verified, mark unresolved and escalate; do not draft as if verified.  
4. Existing Law Analysis is required for every primary amended or repealed target.  
5. Conforming-only targets may use a lighter extract if the primary analysis is complete and the conforming link is explicit; uncertainty must still be flagged.

### 6.4 Existing vs Proposed Distinction

Revision packages shall distinguish existing law from proposed law using explicit methods consistent with KLS-001 Section 8.2 when packaged as bills, including separate sections, side-by-side blocks, and/or marked amendatory legend.

---

## 7. Dependency Analysis

### 7.1 Downstream Impact Mandate

Every statutory change shall identify downstream impacts.

### 7.2 Dependency Categories

| Category | Examples |
|---|---|
| Internal statutory dependents | Provisions that cite, incorporate, or rely on the target |
| Definitional dependents | Provisions using definitions being changed |
| Procedural dependents | Process/trigger provisions keyed to the target |
| Enforcement / penalty dependents | Sanction or enforcement chains linked to the target |
| Regulatory dependents | KAR or agency rules likely keyed to the target (when known) |
| Fiscal / node dependents | Budget or fiscal-authority linkages when in scope |
| Cross-package dependents | Other open engineering packages relying on the target |
| External program dependents | Known program structures that assume the current rule |

### 7.3 Required Dependency Record Fields

| Field | Requirement |
|---|---|
| Source action (`SR-NNN`) | Revision unit creating the impact |
| Dependent locus | Exact citation or explicit unresolved marker |
| Dependency type | Category from Section 7.2 |
| Impact hypothesis | What may break, orphan, broaden, or narrow |
| Required response | Amend / repeal / renumber / note only / escalate |
| Status | Identified / Updated in-package / Deferred / Unresolved |
| Evidence basis | Why the dependency is believed to exist |

### 7.4 Dependency Rules

1. “No dependencies” is acceptable only after documented search/analysis effort and remaining residual-risk note.  
2. Unknown dependency scope shall be recorded as residual risk, not hidden.  
3. Deferred dependency responses require Human Engineer acknowledgment to reach Approved.  
4. Do not invent dependent citations.

---

## 8. Cross-Reference Integrity

### 8.1 Integrity Mandate

Cross-references shall remain valid or be explicitly updated.

### 8.2 Cross-Reference Map Requirements

Every revision package shall maintain a cross-reference integrity map covering:

1. References inside primary targets  
2. External provisions that reference primary targets  
3. References affected by renumbering  
4. References affected by repeal  
5. Internal package references among `SR-NNN` units  
6. Related constitutional, regulatory, and control references when material  

### 8.3 Integrity States

| State | Meaning |
|---|---|
| Valid | Reference still resolves correctly after revision |
| Updated | Reference changed in-package to preserve integrity |
| Broken-Risk | Likely invalid if revision adopted; response required |
| Orphaned | Points to repealed/removed authority |
| Unresolved | Cannot verify; flagged for review |

### 8.4 Integrity Rules

1. Every broken-risk or orphaned reference shall have an explicit response action or documented deferral.  
2. Speculative references shall not be presented as verified.  
3. When renumbering occurs, old→new reference mapping is mandatory.  
4. Cross-reference updates that alter legal meaning are substantive and shall be classified accordingly.  
5. Cross-references do not transfer ownership of foreign documents or controls.

---

## 9. Repeal Coordination

### 9.1 Repeal Mandate

Repeals shall include dependency analysis.

### 9.2 Required Repeal Coordination Fields

| Field | Requirement |
|---|---|
| Repealed citation | Exact authority removed |
| Authority removed | Function/power/duty eliminated |
| Repeal type | Full / partial / repeal-and-replace |
| Replacement | Successor provision if any |
| Dependency analysis link | Required Section 7 record set |
| Cross-reference integrity link | Required Section 8 updates/flags |
| Savings / transition issues | Known or flagged unresolved |
| Regulatory follow-on risks | Known/likely KAR impacts flagged when identifiable |

### 9.3 Repeal Coordination Rules

1. A repeal without dependency analysis is nonconforming.  
2. Repeal-and-replace shall map removed authority to successor authority.  
3. Partial repeals shall identify exact text/authority removed.  
4. Do not assume dependent regulations automatically conform; record the follow-on risk.  
5. Coordinated conforming amendments should be included in the same package when practical; otherwise explicitly schedule/defer them with Human Engineer acknowledgment.

---

## 10. Renumbering Rules

### 10.1 Traceability Mandate

Renumbering shall preserve traceability.

### 10.2 Required Renumbering Map Fields

| Field | Requirement |
|---|---|
| Old citation | Pre-revision locus |
| New citation | Post-revision locus or `[PROPOSED NEW LOCUS]` |
| Action unit | `SR-NNN` |
| Reason | Reorganization / gap-fill / chapter transfer / other |
| Substantive change flag | `None intended` or description of accompanying substantive change |
| Reference update list | All in-package reference updates tied to the renumber |
| Historical alias | Old citation retained as trace alias |

### 10.3 Renumbering Rules

1. Every renumbered locus shall retain an old→new trace alias in package metadata/CDT edges.  
2. Renumbering without a map is nonconforming.  
3. Provisional new numbers shall be marked proposed until verified.  
4. If renumbering is accompanied by substantive edits, classify as composite (`REV-REN` + `REV-SUB` or other).  
5. Do not reuse old numbers for unrelated new subjects inside the same package without explicit Human Engineer-approved alias handling.  
6. Supersession and version history shall remain reconcilable after renumbering.

---

## 11. Version Management

### 11.1 Package Versioning

Revision packages use semantic versioning `MAJOR.MINOR.PATCH`:

| Change Class | Version Impact | Meaning |
|---|---|---|
| MAJOR | Target set redesign, classification overhaul, or incompatible restructuring | Breaking package identity/structure change |
| MINOR | Additive targets, dependency expansions, compatible conforming sets | Backward-compatible expansion |
| PATCH | Clarifications, typo fixes, non-semantic cleanup | No semantic revision-engineering change |

### 11.2 Identity Pattern

Recommended revision package identifier pattern:

```text
KS-STAT-AMD-NNN
```

When carried primarily as a bill, the KLS-001 bill ID may be primary and the revision ID recorded as linked analysis identity.  
Either model is acceptable if traceability between carrier and revision analysis is explicit.

### 11.3 Version Management Record Requirements

1. Prior package/version superseded  
2. Change summary by `SR-NNN`  
3. Renumber aliases introduced/changed  
4. Dependency/cross-reference closure status since prior version  
5. Residual unresolved items carried forward  

### 11.4 Baseline Integrity

Do not silently overwrite prior revision analysis.  
Superseded versions remain auditable.

---

## 12. Constitutional Compatibility

### 12.1 Requirement

Every statutory revision package shall identify governing constitutional authority and assess compatibility risks relevant to the revision.

### 12.2 Required Checks

1. Package remains statutory (`KS-STAT`) and is not a disguised constitutional amendment  
2. Proposed revisions do not facially contradict identified superior constitutional constraints known to the package  
3. Authority for the statutory scheme remains identified or flagged unresolved  
4. Conflicts are reported, not silently normalized  

### 12.3 Escalation

If constitutional compatibility cannot be assessed from available authority, mark `[CONSTITUTIONAL REVIEW REQUIRED]` and escalate.  
Do not fabricate constitutional doctrine.  
If the true subject is constitutional text, stop and route to KLS-002.

---

## 13. AGCL Integration

| Topic | Rule |
|---|---|
| Role | AGCL provides structural control framework relevant to liberty, authority limits, transparency, and related controls |
| Requirement | Assess AGCL applicability for every Kansas statutory revision package |
| When required to cite | When revision scope implicates AGCL-applicable controls |
| Ownership | AGCL remains owned by AGCL-Control-Documents |
| Method | Reference control identifiers; do not fork AGCL into shadow controls |
| Conflict | Report conflicts between proposed revisions and applicable AGCL controls |

References do not imply ownership.

---

## 14. NBBF Integration

| Topic | Rule |
|---|---|
| Role | NBBF provides node-based budget and fiscal authority boundary controls |
| Requirement | Assess whether the revision implicates fiscal/node budget architecture |
| When required to cite | When appropriations, fiscal mandates, fees, node budget structures, or fiscal authority boundaries are revised |
| Ownership | NBBF remains owned by NBBF-Control-Documents |
| Method | Reference NBBF controls; respect Budget Manager domain boundaries when Active |
| Conflict | Report fiscal-control conflicts; do not invent NBBF-compliant meaning |

If fiscal applicability is uncertain, record `[NBBF APPLICABILITY UNRESOLVED]` and escalate.

---

## 15. CDT Metadata

Every Kansas statutory revision package shall include CDT-ready metadata sufficient for future twin modeling.

### 15.1 Minimum CDT Metadata

| Field | Requirement |
|---|---|
| Jurisdiction | `Kansas` |
| Layer ID | `KS-STAT` |
| Artifact Type | `AMD` / linked `BILL` / related type |
| Package ID / Version | Stable identifiers |
| Target nodes | Exact statutory loci revised |
| Revision edges | Amend / repeal / renumber / conform links |
| Dependency edges | Downstream impacted nodes |
| Cross-reference edges | Valid / updated / orphaned states |
| Renumber aliases | Old→new citation aliases |
| Control links | AGCL/NBBF/CDT references as applicable |
| Lifecycle state | Current STD-008 state |
| Supersession link | Prior/successor package IDs when applicable |

### 15.2 CDT / UNBKE Readiness Rules

1. Identifiers and aliases shall be stable and unique.  
2. Dependency and renumber relationships shall be explicit, not only narrative.  
3. Packages shall remain operable without CDT runtime or UNBKE.  
4. Future UNBKE indexing shall be additive; do not hard-depend on UNBKE.  
5. Do not invent dependency edges to appear complete.

---

## 16. Traceability Requirements

### 16.1 Required Trace Elements

| Trace Element | Requirement |
|---|---|
| Existing Law Analysis for primary targets | Required |
| Exact affected statutory loci | Required |
| Revision classification and `SR-NNN` units | Required |
| Dependency analysis | Required |
| Cross-reference integrity map | Required |
| Repeal dependency coordination when repeals exist | Required |
| Renumber aliases when renumbering exists | Required |
| Existing vs proposed distinction method | Required |
| Constitutional authority / compatibility posture | Required |
| Governing CWC-CE | Required for production work |
| Governing ECR / CEP / CER | Conditional per WF-001 |
| Standards applied | At minimum STD-008 and KLS-003; KLS-001 when bill-carried; others as applicable |
| Control references | AGCL/NBBF/CDT as applicable |
| Version/supersession links | Required when replacing prior packages |
| Uncertainty/conflict log | Required when any unresolved item exists |

### 16.2 Traceability Rule

A statutory revision package lacking existing-law analysis, exact targets, dependency analysis, version identity, and lifecycle state is incomplete and shall not enter Approved status.  
Renumbering without old→new aliases is incomplete.

---

## 17. Engineering Review Requirements

### 17.1 Review Gates

Revision packages follow applicable STD-008 states:

```
Proposed → Draft → Engineering Review → Legal Review → Public Review
 → Approved → Published → Superseded → Archived
```

| Review | Focus |
|---|---|
| Engineering Review | Existing-law analysis, classification accuracy, dependency/cross-reference integrity, renumber aliases, repeal coordination, metadata/CDT completeness |
| Legal Review | Authority/compatibility and legal-effect risks against declared sources |
| Public Review | Only when required by authorizing work or Human Engineer direction |

### 17.2 Engineering Review Minimum Checks

1. Existing law analyzed before revision drafting  
2. Every change identifies downstream impacts or documented residual-risk basis  
3. Cross-references valid, updated, or explicitly flagged with response  
4. Renumbering preserves old→new traceability  
5. Repeals include dependency analysis  
6. Existing vs proposed distinction clear  
7. Constitutional compatibility assessed or escalated  
8. AGCL/NBBF/CDT applicability assessed  
9. CDT metadata present  
10. No fabricated citations or invented current-law text  
11. Publication readiness accurately stated  
12. No out-of-scope repository modifications  

### 17.3 Review Outcomes

`Pass` / `Partial` / `Fail` / `Not performed`  
Unperformed review shall not be reported as complete.  
Missing dependency or cross-reference handling for material changes defaults to Fail or Partial.

---

## 18. Publication Requirements

1. Every revision package shall be structurally publication-ready before approval for publication.  
2. Publication-ready means:
   - existing-law analysis complete for primary targets  
   - dependency and cross-reference integrity handled or expressly Human-Engineer-deferred  
   - renumber aliases complete when renumbering exists  
   - repeal coordination complete when repeals exist  
   - traceability complete  
   - unresolved items closed or expressly accepted as open but non-blocking  
   - no fabricated authorities  
3. Legislative Manager may prepare publication packages; Legislative Manager may not self-publish.  
4. Only Human Engineer-approved artifacts enter public channels under WF-001.  
5. Draft/in-review/failed/partial packages are not published unless expressly authorized as such.  
6. Publication of an engineering revision package does not itself enact law.

---

## 19. Quality Checklist

Before presenting a Kansas statutory revision package for Human Engineer review or approval, verify:

| # | Check | Required |
|---|---|---|
| 1 | Authorizing CWC-CE / CEP identified for production work | Yes |
| 2 | Existing law analyzed before revision drafting | Yes |
| 3 | Package identity, layer `KS-STAT`, classification, version present | Yes |
| 4 | Exact affected statutory loci identified | Yes |
| 5 | Downstream impacts identified for every statutory change | Yes |
| 6 | Dependency records complete or residual risk documented | Yes |
| 7 | Cross-references valid, updated, or explicitly handled | Yes |
| 8 | Repeals include dependency analysis | Yes when repeals exist |
| 9 | Renumbering includes old→new aliases and reference updates | Yes when renumbering exists |
| 10 | Existing law distinguished from proposed law | Yes |
| 11 | Version/supersession management recorded | Yes |
| 12 | Constitutional compatibility assessed or escalated | Yes |
| 13 | AGCL applicability assessed; cited when required | Yes |
| 14 | NBBF applicability assessed; cited when required | Yes |
| 15 | CDT metadata present | Yes |
| 16 | Traceability block complete | Yes |
| 17 | Lifecycle state correct; no unauthorized Approved/Published | Yes |
| 18 | Publication readiness accurately declared | Yes |
| 19 | No invented current-law text or fabricated citations | Yes |
| 20 | Uncertainty escalated rather than hidden | Yes |
| 21 | Package supports future CDT/UNBKE mapping without hard dependency | Yes |
| 22 | If bill-carried, KLS-001 requirements also satisfied or linked | Yes when applicable |
| 23 | Not a disguised constitutional amendment (KLS-002 route if needed) | Yes |

Any failed required check blocks a claim of completion.

---

## 20. Conformance

1. Conformance to KLS-003 is mandatory for Kansas statutory revision packages engineered by Legislative Manager after this standard’s Effective Date, subject to Human Engineer activation/acceptance of this Draft if required by Office practice.  
2. Nonconformance is an engineering defect and shall be corrected before Approved/Published states.  
3. Exceptions require explicit Human Engineer approval and shall record reason, scope, duration/terminal condition, approver, and date.  
4. An exception never authorizes fabricated current law, hidden broken cross-references, false verification, or undisclosed scope expansion.  
5. Conformance does not require UNBKE.  
6. When revision work is bill-carried, conformance to both KLS-001 and KLS-003 is required.  
7. Constitutional subject matter remains under KLS-002; misrouting is nonconformance.  
8. Reserved Office standards remain superior or complementary when Active; conflicts escalate.

---

## 21. Version History

| Version | Date | Summary |
|---|---|---|
| 1.0.0 | 2026-08-08 | Initial Kansas Statutory Revision Engineering Standard establishing existing-law-first revision methodology, dependency analysis, cross-reference integrity, repeal coordination, renumbering traceability, and CDT/UNBKE readiness rules. |
