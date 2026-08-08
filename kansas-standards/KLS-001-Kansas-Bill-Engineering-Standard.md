# KLS-001 — Kansas Bill Engineering Standard

**Document ID:** KLS-001  
**Title:** Kansas Bill Engineering Standard  
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
**Governing Prompt:** Legislative Manager Operating Manual  
**Jurisdiction:** State of Kansas  
**Status:** Draft  
**Version:** 1.0.0  
**Effective Date:** 2026-08-08  

---

## 1. Purpose

This document establishes the canonical engineering standard governing the creation, maintenance, revision, review, publication, and lifecycle of all Kansas bill packages engineered by the Legislative Manager.

It exists to ensure that every Kansas bill package is:

1. Engineered before operative text is drafted  
2. Metadata-complete and versioned  
3. Fully traceable to constitutional and statutory authority  
4. Explicit about existing law versus proposed law  
5. Compatible with AGCL, NBBF, and CDT reference boundaries  
6. Publication-ready in structure before Human Engineer approval  
7. Suitable for future CDT and UNBKE integration without hard runtime dependency  

KLS-001 does not draft legislation and does not invent legal authority.

---

## 2. Scope

### 2.1 In Scope

This standard applies to all Kansas bill packages and closely related statutory packages engineered under Legislative Manager, including:

1. New bill packages (`BILL`)  
2. Statutory amendment packages that revise existing Kansas Statutes (`AMD` affecting `KS-STAT`)  
3. Repeal packages removing statutory authority within Kansas bill/statutory engineering  
4. Companion engineering manifests, metadata, and traceability records for those packages  
5. Review, publication packaging, and lifecycle control of the above  

### 2.2 Out of Scope

This standard does not:

1. Draft bill text, enact law, or determine Kansas political outcomes  
2. Govern constitutional amendment packages as primary subject matter (see future Kansas constitutional standards; CAP work remains under SPEC-001 and Operating Manual rules)  
3. Govern county/city/school charter packages as primary subject matter  
4. Modify Engineering Office ARCH/POL/STD/WF documents  
5. Modify AGCL, NBBF, or CDT control documents  
6. Require UNBKE or any specific legislative drafting tool  

### 2.3 Relationship to Other Authorities

```
ARCH-001 / ARCH-002 / ARCH-003 / ARCH-004
        ↓
POL-001 / WF-001 / STD-008 / STD-014 / STD-015
        ↓
SPEC-001 (Kansas Constitutional Engineering Specification)
        ↓
KLS-001 (this standard)
        ↓
Kansas bill packages under Legislative Manager
```

Where KLS-001 and SPEC-001 both apply, both are binding.  
Where conflict appears, stop and escalate to the Human Engineer.  
Office architecture, policy, standards, and workflow remain superior to manager-local Kansas standards.

---

## 3. Authority

1. KLS-001 is issued under Constitutional Engineering Office authority and owned by Legislative Manager.  
2. KLS-001 is subordinate to ARCH-001 through ARCH-004, POL-001, WF-001, STD-008, and SPEC-001.  
3. Kansas constitutional and statutory law remain the legal source of governing truth for Kansas content.  
4. AGCL, NBBF, and CDT remain owned by their control repositories; KLS-001 authorizes reference, not ownership.  
5. AI may prepare Kansas bill packages under authorized work; AI never owns the packages and never grants Human Engineer approval.  
6. Production use of this standard proceeds through WF-001 authorization gates.

---

## 4. Kansas Legislative Layers

Kansas bill engineering shall respect SPEC-001 constitutional layer order. Higher layers constrain lower layers.

```
Kansas Constitution          (KS-CONST)
      ↓
Kansas Statutes              (KS-STAT)   ← primary layer for bill packages
      ↓
Kansas Administrative Regulations (KS-KAR)
      ↓
County / City / School instruments
```

### 4.1 Bill Layer Rule

Kansas bill packages are primarily `KS-STAT` artifacts.  
A bill may implement, reference, or be constrained by `KS-CONST`, but shall not silently redefine constitutional text.  
If a package’s true subject is constitutional amendment, it shall be engineered as a `CAP` package under SPEC-001, not disguised as an ordinary bill.

### 4.2 Layer Conflict Rule

If a proposed bill conflicts with a higher Kansas layer or applicable control document:

1. Report the conflict  
2. Do not advance to Approved or Published until resolved or expressly deferred by Human Engineer authority  
3. Do not invent a reconciliation that creates new policy  

---

## 5. Bill Package Architecture

### 5.1 Engineer-Before-Draft Rule

Every Kansas bill package shall be engineered before operative bill text is drafted. Required engineering sequence:

1. Confirm authorizing CWC-CE / CEP  
2. Assign identity, layer, type, version, and placement  
3. Complete metadata  
4. Map constitutional authority and affected statutes  
5. Establish traceability and control references  
6. Distinguish existing law from proposed law loci  
7. Only then draft authorized bill language  

### 5.2 Logical Package Structure

Every Kansas bill package shall implement the following logical architecture:

```
Bill Package
├── Identity / Manifest
├── Engineering Summary
├── Authority Map
│   ├── Constitutional authority
│   ├── Affected statutes
│   └── Control references (AGCL / NBBF / CDT as applicable)
├── Traceability Block
├── Definitions (as required)
├── Existing Law Extracts / Citations
├── Proposed Law
│   ├── New sections
│   ├── Amendments
│   └── Repeals
├── Effective Date Provisions
├── Cross-Reference Map
├── CDT Metadata
├── Review Records
├── Publication Package (when prepared)
└── Version History
```

### 5.3 Recommended Repository Placement

Per SPEC-001, Kansas statewide statutory/bill packages should be placed under:

```text
Legislative-Manager/templates/State/Kansas/
```

or a successor Kansas state tree authorized under approved work.  
Exact subdirectory creation occurs only under authorized CWC-CE / CEP scope.

### 5.4 Package Completeness Rule

A package is structurally incomplete if any required logical component in Section 5.2 is missing for its lifecycle state, except where a component is expressly marked `Not applicable` with justification.

---

## 6. Bill Metadata Requirements

Every Kansas bill package shall include complete metadata.

### 6.1 Required Metadata Fields

| Field | Required | Description |
|---|---|---|
| Package ID | Yes | Unique package identifier |
| Title | Yes | Official engineering title of the bill package |
| Artifact Type | Yes | `BILL` or authorized statutory equivalent |
| Layer ID | Yes | `KS-STAT` unless expressly authorized otherwise |
| Jurisdiction | Yes | `Kansas` |
| Version | Yes | Semantic version `MAJOR.MINOR.PATCH` |
| Lifecycle State | Yes | STD-008 state |
| Status Date | Yes | Date of current lifecycle state |
| Authorizing CWC-CE | Yes for production work | Governing work card |
| Governing CEP / CER | Conditional | Required when implemented through Cursor/manager CEP work |
| Constitutional Authority | Yes | Governing Kansas constitutional locus/loci |
| Affected Statutes | Yes | Exact K.S.A. sections/chapters affected, or explicit `None — new law` with placement plan |
| Existing vs Proposed Distinction | Yes | Clear separation method used in package |
| Effective Date Posture | Yes | Proposed/contingent/known effective-date rule |
| AGCL References | Conditional | Required when AGCL-applicable controls are implicated |
| NBBF References | Conditional | Required when fiscal/node budget scope is implicated |
| CDT Metadata | Yes | Minimum relationship metadata for twin readiness |
| Steward / Owning Manager | Yes | Legislative Manager; Human Engineer remains approving authority |
| Publication Readiness | Yes | `Not ready` / `Structurally ready` / `Approved for publication` |
| Uncertainty Flags | Yes if any | Explicit unresolved items |

### 6.2 Metadata Integrity Rules

1. Metadata shall not be left blank for required fields.  
2. Unknown values shall be marked unresolved and escalated, not invented.  
3. Metadata and body content shall not contradict each other.  
4. Lifecycle state in metadata shall match the package’s actual review posture.

---

## 7. Bill Numbering Conventions

### 7.1 Package Identifier

Recommended Kansas bill package identifier pattern:

```text
KS-STAT-BILL-NNN
```

Examples:

- `KS-STAT-BILL-001`
- `KS-STAT-BILL-014`

Rules:

1. `NNN` is a zero-padded sequential integer within the Kansas bill series under Legislative Manager.  
2. Numbers are not reused for different bill subjects.  
3. Superseding packages receive a new version and, when subject identity changes materially, a new package ID under Human Engineer direction.  
4. Filename convention: `{Package-ID}-{Short-Title}.md` or approved equivalent package folder name.

### 7.2 Internal Section Numbering

Within a package:

1. Engineering sections use decimal numbering consistent with TMP-001 style where practical.  
2. Proposed statutory section numbering shall either:
   - cite existing K.S.A. numbers being amended/repealed, or  
   - mark proposed new numbering as `[PROPOSED K.S.A. ___]` until verified  
3. Do not invent final K.S.A. numbers as if assigned by official codifiers unless source authority supports them or they are expressly provisional.

### 7.3 Version Numbering

| Change Class | Version Impact | Meaning |
|---|---|---|
| MAJOR | Breaking package redesign or subject replacement | Incompatible structural/identity change |
| MINOR | Additive sections, new affected statutes, compatible expansion | Backward-compatible engineering expansion |
| PATCH | Clarifications, typo fixes, non-semantic cleanup | No semantic legal-engineering change |

---

## 8. Required Bill Sections

Unless an approved exception is recorded, every Kansas bill package shall contain the following sections:

| Section | Purpose |
|---|---|
| 1. Purpose | Engineering purpose of the package |
| 2. Scope | What the bill package covers and excludes |
| 3. Authority Map | Constitutional authority and statutory targets |
| 4. Metadata Summary | Required metadata condensed for reviewers |
| 5. Definitions | Defined terms used in proposed law, if any |
| 6. Existing Law | Cited current law extracts/references |
| 7. Proposed Law | New text, amendments, and repeals |
| 8. Effective Date | Effective-date engineering rules for the package |
| 9. Cross-References | Internal/external reference map |
| 10. Control Integration | AGCL/NBBF/CDT applicability |
| 11. Traceability | Full trace block |
| 12. Review Record | Engineering/legal/public review status |
| 13. Publication Record | Publication readiness and approvals |
| 14. Version History | Package revision history |

### 8.1 Proposed Law Subsection Order

Inside Proposed Law, use this order when multiple action types exist:

1. New sections  
2. Amendments  
3. Repeals  

### 8.2 Distinguishing Existing Law from Proposed Law

Every package shall use an explicit distinction method, such as:

- separate sections for Existing Law and Proposed Law, and/or  
- amendatory markup conventions clearly explained in-package, and/or  
- side-by-side current-vs-proposed blocks  

Ambiguous blended text that does not show what is current versus proposed is nonconforming.

---

## 9. Amendment Structure

### 9.1 Amendment Rule

Every amendment shall identify the exact affected section.

### 9.2 Required Amendment Fields

| Field | Requirement |
|---|---|
| Target citation | Exact K.S.A. section/subsection/paragraph when known |
| Target title/catchline | If known |
| Amendment type | Insert / strike / rewrite / renumber / transfer / other |
| Current text reference | Citation and/or quoted extract of current law |
| Proposed text | Exact proposed language |
| Continuity notes | What remains unchanged |
| Uncertainty | Any unverified locus marked explicitly |

### 9.3 Amendment Engineering Pattern

```text
AMENDMENT A-NNN
Target: K.S.A. __-____
Type: [insert|strike|rewrite|renumber|transfer]
Current Law: ...
Proposed Law: ...
Effect Summary: ...
```

### 9.4 Amendment Prohibitions

1. Do not amend “the law generally” without section-level targets.  
2. Do not silently change meaning while calling a change “nonsubstantive” without Human Engineer acknowledgment.  
3. Do not invent the current text of a statute; cite source or mark `[CITATION/TEXT NEEDED]`.

---

## 10. Repeal Structure

### 10.1 Repeal Rule

Every repeal shall identify the authority being removed.

### 10.2 Required Repeal Fields

| Field | Requirement |
|---|---|
| Repealed citation | Exact K.S.A. section(s) or other statutory authority being removed |
| Authority being removed | Description of the legal authority/function eliminated |
| Repeal type | Full repeal / partial repeal / repeal-and-replace |
| Replacement | Successor provision ID if repeal-and-replace |
| Savings / transition | Transition, savings, or grandfather issues if known or flagged |
| Dependency check | Known dependent statutes/regulations impacted |
| Uncertainty | Explicit unresolved dependency risks |

### 10.3 Repeal Engineering Pattern

```text
REPEAL R-NNN
Target: K.S.A. __-____
Type: [full|partial|repeal-and-replace]
Authority Removed: ...
Replacement: [none|package section/citation]
Dependencies / Risks: ...
```

### 10.4 Repeal Prohibitions

1. Do not repeal by vague subject description alone.  
2. Do not omit successor/transition analysis when repeal-and-replace is intended.  
3. Do not assume dependent regulations automatically fall without recording the issue for review.

---

## 11. Effective Date Rules

### 11.1 Effective Date Requirement

Every Kansas bill package shall state an effective-date posture.

### 11.2 Allowed Effective-Date Postures

| Posture | Meaning |
|---|---|
| Publication / statutory default | Relies on Kansas default effective-date rules; cite basis or mark for legal review |
| Fixed date | States a specific proposed effective date |
| Contingent | Effective upon stated condition/event |
| Staged | Different provisions take effect on different dates |
| Retroactive proposed | Explicitly flagged; requires heightened Human Engineer / legal review |
| Unresolved | `[EFFECTIVE DATE UNRESOLVED]` — blocks Approved/Published |

### 11.3 Effective Date Engineering Rules

1. Effective-date text in Proposed Law and metadata shall match.  
2. Staged effective dates shall map to exact sections.  
3. Retroactivity shall never be hidden.  
4. If legal default rules are uncertain, escalate rather than invent.

---

## 12. Definitions Rules

### 12.1 When Definitions Are Required

Definitions are required when:

1. Proposed law introduces specialized terms  
2. Terms are used in a sense narrower/broader than ordinary meaning  
3. Cross-chapter consistency depends on defined terms  

### 12.2 Definition Engineering Rules

1. Definitions shall be grouped in a dedicated Definitions section unless jurisdiction style expressly requires otherwise and that choice is recorded.  
2. Each definition shall have a stable term label.  
3. Definitions shall not hide operative mandates better placed in substantive sections.  
4. Circular definitions are nonconforming.  
5. If a term already has a controlling Kansas statutory definition, cite it rather than silently redefining it.  
6. Proposed redefinitions of existing defined terms shall be treated as amendments to those definitional loci.

---

## 13. Cross-Reference Rules

### 13.1 Cross-Reference Map Requirement

Every package shall maintain a cross-reference map covering:

1. Internal package references  
2. Cited Kansas constitutional provisions  
3. Cited or affected K.S.A. sections  
4. Related regulations if known/material  
5. Related bill packages / companion packages  
6. AGCL / NBBF / CDT identifiers when applicable  

### 13.2 Cross-Reference Integrity Rules

1. Every cross-reference shall resolve to a real target or be marked unresolved.  
2. Broken or speculative references shall not be presented as verified.  
3. When renumbering/repeal affects references, update the map in the same package version.  
4. Cross-references do not transfer ownership of foreign documents or controls.

---

## 14. Constitutional Compatibility Requirements

### 14.1 Constitutional Authority Identification

Every Kansas bill package shall identify governing constitutional authority, including at minimum:

1. Relevant Kansas constitutional article/section loci when known  
2. Statement of why the bill is within that authority, as an engineering rationale  
3. Any known constitutional constraints or conflict risks  

### 14.2 Compatibility Checks

Before Engineering Review completion, verify:

1. Package is not a disguised constitutional amendment  
2. Proposed duties do not facially contradict identified superior constitutional constraints known to the package  
3. Local/state authority boundaries implicated by the bill are identified or flagged  
4. Conflicts are reported, not silently normalized  

### 14.3 Escalation Rule

If constitutional compatibility cannot be assessed from available authority, mark `[CONSTITUTIONAL REVIEW REQUIRED]` and escalate.  
Do not fabricate constitutional doctrine.

---

## 15. AGCL Control Integration

| Topic | Rule |
|---|---|
| Role | AGCL provides structural control framework relevant to liberty, authority limits, transparency, and related controls |
| Requirement | Assess AGCL applicability for every Kansas bill package |
| When required to cite | When package scope implicates AGCL-applicable controls |
| Ownership | AGCL remains owned by AGCL-Control-Documents |
| Method | Reference control identifiers; do not fork AGCL text into conflicting manager-owned “shadow controls” |
| Conflict | Report conflicts between proposed bill content and applicable AGCL controls |

AGCL integration is reference-based under ARCH-004.  
References do not imply ownership under ARCH-003.

---

## 16. NBBF Fiscal Integration

| Topic | Rule |
|---|---|
| Role | NBBF provides node-based budget and fiscal authority boundary controls |
| Requirement | Assess whether the bill implicates fiscal/node budget architecture |
| When required to cite | When appropriations, fiscal mandates, node budget structures, or fiscal authority boundaries are in scope |
| Ownership | NBBF remains owned by NBBF-Control-Documents |
| Method | Reference NBBF controls; coordinate with Budget Manager domain boundaries when that manager is Active |
| Conflict | Report fiscal-control conflicts; do not invent NBBF-compliant meaning |

If fiscal applicability is uncertain, record `[NBBF APPLICABILITY UNRESOLVED]` and escalate.

---

## 17. CDT Metadata Requirements

Every Kansas bill package shall include CDT-ready metadata sufficient for future twin modeling.

### 17.1 Minimum CDT Metadata

| Field | Requirement |
|---|---|
| Jurisdiction | `Kansas` |
| Layer ID | `KS-STAT` (or authorized) |
| Artifact Type | `BILL` / related type |
| Package ID / Version | Stable identifiers |
| Authority relationships | Constitutional authority and affected statutory nodes |
| Amendment/repeal edges | Exact targets as relationship edges |
| Effective-date node | Effective-date posture |
| Control links | AGCL/NBBF/CDT references as applicable |
| Lifecycle state | Current STD-008 state |
| Supersession link | Prior/successor package IDs when applicable |

### 17.2 CDT / UNBKE Readiness Rules

1. Identifiers shall be stable and unique.  
2. Relationships shall be explicit, not only narrative.  
3. Packages shall remain operable without CDT runtime or UNBKE.  
4. Future UNBKE indexing shall be additive; do not hard-depend on UNBKE.

---

## 18. Traceability Requirements

### 18.1 Required Trace Elements

| Trace Element | Requirement |
|---|---|
| Source constitutional authority | Required |
| Affected statutes | Required (or explicit new-law placement plan) |
| Layer ID / artifact identity / version | Required |
| Existing vs proposed distinction method | Required |
| Governing CWC-CE | Required for production work |
| Governing ECR / CEP / CER | Conditional per WF-001 |
| Standards applied | At minimum STD-008 and KLS-001; others as applicable |
| Control references | AGCL/NBBF/CDT as applicable |
| Review outcomes | Engineering/legal/public as applicable |
| Publication approvals | When published |
| Uncertainty/conflict log | Required when any unresolved item exists |

### 18.2 Traceability Rule

A Kansas bill package lacking constitutional authority identification, affected-statute identification (or explicit new-law plan), version, and lifecycle state is incomplete and shall not enter Approved status.

---

## 19. Engineering Review Requirements

### 19.1 Review Gates

Kansas bill packages shall pass through applicable STD-008 review states before approval:

| Review | Focus |
|---|---|
| Engineering Review | Structure, metadata completeness, numbering, traceability, existing-vs-proposed clarity, interface/ownership conformance |
| Legal Review | Constitutional/statutory compatibility against declared source authority; amendment/repeal exactness; effective-date legality questions |
| Public Review | Only when required by authorizing work or Human Engineer direction |

### 19.2 Engineering Review Minimum Checks

1. Engineer-before-draft sequence followed  
2. Required sections present  
3. Metadata complete  
4. Exact amendment targets present  
5. Exact repeal authorities present  
6. Effective-date posture stated  
7. Cross-references resolve or are flagged  
8. AGCL/NBBF/CDT applicability assessed  
9. CDT metadata present  
10. No invented citations presented as verified  
11. Publication readiness accurately stated  
12. No out-of-scope repository modifications  

### 19.3 Review Outcomes

`Pass` / `Partial` / `Fail` / `Not performed`  
Unperformed review shall not be reported as complete.

---

## 20. Publication Requirements

1. Every package shall be structurally publication-ready before approval for publication.  
2. Publication-ready means:
   - required sections complete for Approved posture  
   - metadata complete  
   - traceability complete  
   - unresolved items either closed or expressly accepted by Human Engineer as open but non-blocking  
   - no fabricated authorities  
3. Legislative Manager may prepare publication packages; Legislative Manager may not self-publish.  
4. Only Human Engineer-approved artifacts enter public channels under WF-001.  
5. Draft/in-review/failed/partial packages are not published unless expressly authorized as such.  
6. Publication does not transfer ownership of AGCL/NBBF/CDT or create enacted-law status by itself.

---

## 21. Lifecycle States

Kansas bill packages follow STD-008:

```
Proposed
  → Draft
  → Engineering Review
  → Legal Review
  → Public Review
  → Approved
  → Published
  → Superseded
  → Archived
```

### 21.1 State Meanings for Kansas Bills

| State | Meaning |
|---|---|
| Proposed | Need/concept captured; package identity may exist; operative draft not required yet |
| Draft | Active engineering and authorized drafting underway |
| Engineering Review | Structure/metadata/traceability under review |
| Legal Review | Authority/compatibility review against declared sources |
| Public Review | Stakeholder/public package issued when required |
| Approved | Human Engineer authorization for publication path |
| Published | Released through approved publication channel |
| Superseded | Replaced by successor package version/ID |
| Archived | Historical retention only |

### 21.2 Transition Rules

1. Lifecycle transitions require Human Engineer authorization where WF-001 / STD-008 require it.  
2. AI may recommend transitions; AI may not self-approve Approved or Published.  
3. Failed reviews return the package to Draft or remain in review with recorded defects.  
4. Supersession shall record successor identity.

---

## 22. Quality Checklist

Before presenting a Kansas bill package for Human Engineer review or approval, verify:

| # | Check | Required |
|---|---|---|
| 1 | Authorizing CWC-CE / CEP identified for production work | Yes |
| 2 | Engineer-before-draft sequence completed | Yes |
| 3 | Package ID, title, type, layer, version present | Yes |
| 4 | Complete metadata present | Yes |
| 5 | Governing constitutional authority identified | Yes |
| 6 | Affected statutes identified (or explicit new-law plan) | Yes |
| 7 | Existing law distinguished from proposed law | Yes |
| 8 | Every amendment identifies exact affected section | Yes |
| 9 | Every repeal identifies authority being removed | Yes |
| 10 | Effective-date posture stated and consistent | Yes |
| 11 | Definitions conform to Section 12 when used | Yes |
| 12 | Cross-reference map complete or unresolved items flagged | Yes |
| 13 | Constitutional compatibility assessed or escalated | Yes |
| 14 | AGCL applicability assessed; cited when required | Yes |
| 15 | NBBF applicability assessed; cited when required | Yes |
| 16 | CDT metadata present | Yes |
| 17 | Traceability block complete | Yes |
| 18 | Lifecycle state correct; no unauthorized Approved/Published | Yes |
| 19 | Publication readiness accurately declared | Yes |
| 20 | No invented legal authority or fabricated citations | Yes |
| 21 | Uncertainty escalated rather than hidden | Yes |
| 22 | Package supports future CDT/UNBKE mapping without hard dependency | Yes |

Any failed required check blocks a claim of completion.

---

## 23. Conformance

1. Conformance to KLS-001 is mandatory for Kansas bill packages engineered by Legislative Manager after this standard’s Effective Date, subject to Human Engineer activation/acceptance of this Draft if required by Office practice.  
2. Nonconformance is an engineering defect and shall be corrected before Approved/Published states.  
3. Exceptions require explicit Human Engineer approval and shall record reason, scope, duration/terminal condition, approver, and date.  
4. An exception never authorizes fabricated authority, false verification, or undisclosed scope expansion.  
5. Conformance does not require UNBKE.  
6. Reserved Office standards (including STD-007 when activated) remain superior or complementary as applicable; conflicts escalate.

---

## 24. Version History

| Version | Date | Summary |
|---|---|---|
| 1.0.0 | 2026-08-08 | Initial Kansas Bill Engineering Standard establishing canonical engineering rules for Kansas bill packages under Legislative Manager. |
