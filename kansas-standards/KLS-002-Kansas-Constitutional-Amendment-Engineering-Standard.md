# KLS-002 — Kansas Constitutional Amendment Engineering Standard

**Document ID:** KLS-002  
**Title:** Kansas Constitutional Amendment Engineering Standard  
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
**Related Kansas Standard:** KLS-001 — Kansas Bill Engineering Standard  
**Governing Prompt:** Legislative Manager Operating Manual  
**Jurisdiction:** State of Kansas  
**Status:** Draft  
**Version:** 1.0.0  
**Effective Date:** 2026-08-08  

---

## 1. Purpose

This document establishes the canonical engineering standard governing the creation, maintenance, review, publication, and lifecycle of Kansas constitutional amendment packages engineered by the Legislative Manager.

It exists to ensure that every Kansas constitutional amendment package (`CAP`) is:

1. Engineered before operative amendatory text is drafted  
2. Metadata-complete and versioned  
3. Exact in article and section targeting  
4. Explicit in distinguishing existing constitutional language from proposed language  
5. Free of fabricated constitutional authority  
6. Compatible with AGCL, NBBF, and CDT reference boundaries  
7. Publication-ready in structure before Human Engineer approval  
8. Documented for ratification workflow without simulating ratification  
9. Suitable for future CDT and UNBKE integration without hard runtime dependency  

KLS-002 does not draft constitutional amendments and does not invent legal authority.

---

## 2. Scope

### 2.1 In Scope

This standard applies to Kansas constitutional amendment packages and related engineering records under Legislative Manager, including:

1. Constitutional Amendment Packages (`CAP`) at layer `KS-CONST`  
2. Amendatory, additive, repeal, and restructuring proposals affecting Kansas Constitution loci  
3. Companion manifests, metadata, conflict maps, and traceability records for those packages  
4. Engineering review, publication packaging, lifecycle control, and ratification-process documentation for the above  

### 2.2 Out of Scope

This standard does not:

1. Draft constitutional amendment text, ratify amendments, or declare constitutional meaning as settled law without cited source  
2. Simulate elections, petition thresholds, legislative adoption votes, or canvassing outcomes  
3. Govern ordinary Kansas bill packages as primary subject matter (see KLS-001)  
4. Govern county/city/school charter packages as primary subject matter  
5. Modify Engineering Office ARCH/POL/STD/WF documents  
6. Modify AGCL, NBBF, CDT, or KLS-001  
7. Require UNBKE or any specific drafting tool  

### 2.3 Relationship to Other Authorities

```
ARCH-001 / ARCH-002 / ARCH-003 / ARCH-004
        ↓
POL-001 / WF-001 / STD-008 / STD-014 / STD-015
        ↓
SPEC-001 (Kansas Constitutional Engineering Specification)
        ↓
KLS-002 (this standard)
        ↓
Kansas constitutional amendment packages (CAP) under Legislative Manager
```

KLS-001 governs Kansas bill / statutory packages.  
KLS-002 governs Kansas constitutional amendment packages.  
A statutory bill shall not be used to disguise a constitutional amendment.  
Where KLS-002 and SPEC-001 both apply, both are binding.  
Where conflict appears, stop and escalate to the Human Engineer.

---

## 3. Authority

1. KLS-002 is issued under Constitutional Engineering Office authority and owned by Legislative Manager.  
2. KLS-002 is subordinate to ARCH-001 through ARCH-004, POL-001, WF-001, STD-008, and SPEC-001.  
3. The Kansas Constitution remains the supreme in-state legal source for Kansas constitutional content.  
4. AGCL, NBBF, and CDT remain owned by their control repositories; KLS-002 authorizes reference, not ownership.  
5. AI may prepare CAP packages under authorized work; AI never owns the packages and never grants Human Engineer approval.  
6. AI shall not fabricate constitutional citations, article/section targets, or ratification outcomes.  
7. Production use proceeds through WF-001 authorization gates.  
8. Constitutional amendment packages are higher-risk artifacts and warrant heightened Human Engineer checkpoints.

---

## 4. Constitutional Amendment Package Architecture

### 4.1 Engineer-Before-Draft Rule

Every Kansas CAP shall be engineered before operative amendatory text is drafted. Required sequence:

1. Confirm authorizing CWC-CE / CEP  
2. Assign identity, layer `KS-CONST`, type `CAP`, version, and placement  
3. Complete constitutional metadata  
4. Identify exact article/section targets (or expressly mark unresolved targets as blocking)  
5. Build existing-vs-proposed distinction method  
6. Map constitutional compatibility, conflicts, and control references  
7. Document ratification pathway applicable to the proposal class (without simulating outcomes)  
8. Only then draft authorized amendatory language  

### 4.2 Logical Package Structure

```
Constitutional Amendment Package (CAP)
├── Identity / Manifest
├── Engineering Summary
├── Amendment Class
│   ├── Amendment / Addition / Repeal / Restructuring / Composite
├── Target Map
│   ├── Article targets
│   ├── Section targets
│   └── Subsection/clause targets when applicable
├── Authority & Compatibility Map
│   ├── Superior/related constitutional provisions
│   ├── AGCL / NBBF / CDT references as applicable
├── Existing Constitution
├── Proposed Constitution
│   ├── Amendatory text
│   ├── Additions
│   └── Repeals / strikethroughs
├── Effect / Conflict Analysis
├── Ratification Pathway Record (documented, not simulated)
├── Definitions (if required)
├── Cross-Reference Map
├── CDT Metadata
├── Traceability Block
├── Review Records
├── Publication Package (when prepared)
└── Version History
```

### 4.3 Recommended Repository Placement

Per SPEC-001, Kansas constitutional packages should be placed under:

```text
Legislative-Manager/templates/State/Kansas/
```

or a successor Kansas state constitutional tree authorized under approved work.  
Exact subdirectory creation occurs only under authorized CWC-CE / CEP scope.

### 4.4 Package Completeness Rule

A CAP is structurally incomplete if any required logical component in Section 4.2 is missing for its lifecycle state, except where a component is expressly marked `Not applicable` with justification.

### 4.5 Disguised Amendment Prohibition

Ordinary bill packages under KLS-001 shall not be used to enact or present constitutional change.  
If the true subject is constitutional text, engineer a `CAP` under this standard.

---

## 5. Constitutional Metadata Requirements

Every Kansas CAP shall include complete metadata.

### 5.1 Required Metadata Fields

| Field | Required | Description |
|---|---|---|
| Package ID | Yes | Unique CAP identifier |
| Title | Yes | Official engineering title |
| Artifact Type | Yes | `CAP` |
| Layer ID | Yes | `KS-CONST` |
| Jurisdiction | Yes | `Kansas` |
| Version | Yes | Semantic version `MAJOR.MINOR.PATCH` |
| Lifecycle State | Yes | STD-008 state |
| Status Date | Yes | Date of current lifecycle state |
| Authorizing CWC-CE | Yes for production work | Governing work card |
| Governing CEP / CER | Conditional | Required when implemented through CEP work |
| Amendment Class | Yes | Amendment / Addition / Repeal / Restructuring / Composite |
| Exact Targets | Yes | Article and section (and deeper loci when applicable) |
| Existing vs Proposed Method | Yes | Distinction method used |
| Related Constitutional Provisions | Yes | Superior/adjacent provisions implicated |
| Ratification Pathway Class | Yes | Documented pathway type; outcome not simulated |
| Ratification Status | Yes | Engineering status only (see Section 16) |
| AGCL References | Conditional | Required when AGCL-applicable controls are implicated |
| NBBF References | Conditional | Required when fiscal/node budget constitutional effects are implicated |
| CDT Metadata | Yes | Minimum relationship metadata for twin readiness |
| Steward / Owning Manager | Yes | Legislative Manager; Human Engineer remains approving authority |
| Publication Readiness | Yes | `Not ready` / `Structurally ready` / `Approved for publication` |
| Uncertainty Flags | Yes if any | Explicit unresolved items |

### 5.2 Metadata Integrity Rules

1. Required fields shall not be blank.  
2. Unknown targets or pathways shall be marked unresolved and escalated, not invented.  
3. Metadata and body content shall not contradict each other.  
4. Ratification Status shall never imply a completed popular/legislative ratification unless independently verified source authority records that fact and Human Engineer accepts that representation.  
5. Lifecycle state shall match actual review posture.

---

## 6. Amendment Numbering Conventions

### 6.1 Package Identifier

Recommended Kansas CAP identifier pattern:

```text
KS-CONST-CAP-NNN
```

Examples:

- `KS-CONST-CAP-001`
- `KS-CONST-CAP-007`

Rules:

1. `NNN` is a zero-padded sequential integer within the Kansas CAP series under Legislative Manager.  
2. Numbers are not reused for different constitutional subjects.  
3. Material subject replacement generally requires a new package ID under Human Engineer direction; refinements use semantic versioning.  
4. Filename convention: `{Package-ID}-{Short-Title}.md` or approved equivalent package folder name.

### 6.2 Internal Amendment Unit Numbering

Within a package, number discrete amendatory actions:

```text
CA-NNN
```

Each `CA-NNN` unit shall bind to exact article/section targets.

### 6.3 Version Numbering

| Change Class | Version Impact | Meaning |
|---|---|---|
| MAJOR | Target set redesign, amendment class change, or incompatible restructuring | Breaking engineering identity/structure change |
| MINOR | Additive targets, compatible analysis expansions | Backward-compatible expansion |
| PATCH | Clarifications, typo fixes, non-semantic cleanup | No semantic constitutional-engineering change |

### 6.4 Provisional Citation Rule

Proposed new article/section numbers shall be marked `[PROPOSED Art. __ § __]` until verified or expressly designated as proposed numbering.  
Do not present provisional numbering as already existing constitutional numbering.

---

## 7. Existing Constitution vs Proposed Constitution Rules

### 7.1 Distinction Mandate

Existing constitutional language shall always be distinguished from proposed language.

### 7.2 Required Distinction Method

Every CAP shall use an explicit method, such as:

1. Separate `Existing Constitution` and `Proposed Constitution` sections, and/or  
2. Side-by-side current-vs-proposed blocks per target, and/or  
3. Amendatory markup with a legend explaining strike/insert/rewrite conventions  

Ambiguous blended text that does not show what is current versus proposed is nonconforming.

### 7.3 Existing Constitution Rules

1. Existing text shall be cited to exact article/section loci.  
2. Quoted existing text shall come from identified source authority or be marked `[CONSTITUTIONAL TEXT NEEDED]`.  
3. Do not invent current constitutional wording.  
4. If only a partial extract is shown, state that it is partial and identify omitted context risks.

### 7.4 Proposed Constitution Rules

1. Proposed text shall be clearly labeled as proposed.  
2. Each proposed change shall map to a `CA-NNN` unit and exact target.  
3. Placeholders shall use explicit flags (`[PROPOSED]`, `[VERIFY]`, `[CITATION NEEDED]`).  
4. Never present proposed language as ratified or presently operative constitution text.

---

## 8. Article and Section Targeting Rules

### 8.1 Exact Targeting Mandate

Every amendment shall identify the exact constitutional article and section.  
Where the change operates below section level, also identify subsection, clause, or paragraph when known.

### 8.2 Required Target Fields per Amendatory Unit

| Field | Requirement |
|---|---|
| Article | Exact article designation |
| Section | Exact section designation |
| Deeper locus | Subsection/clause/paragraph when applicable |
| Catchline / title | If known |
| Action type | Amend / add / repeal / renumber / transfer / restructure |
| Current text reference | Citation and/or extract |
| Proposed text | Exact proposed language or structured proposal |
| Collateral targets | Other articles/sections necessarily affected |
| Uncertainty | Unresolved targeting marked explicitly |

### 8.3 Targeting Pattern

```text
CA-NNN
Article: ...
Section: ...
Deeper Locus: [none|...]
Action: [amend|add|repeal|renumber|transfer|restructure]
Current Constitution: ...
Proposed Constitution: ...
Collateral Targets: ...
```

### 8.4 Multi-Target and Restructuring Rules

1. Composite packages may contain multiple `CA-NNN` units; each unit still requires exact targets.  
2. Restructuring that renumbers or relocates provisions shall include a before/after target map.  
3. “Global constitutional modernization” without article/section targets is nonconforming.  
4. If a target cannot yet be identified, record `[TARGET UNRESOLVED]` and block Approved/Published until resolved or expressly deferred by Human Engineer.

---

## 9. Constitutional Compatibility Requirements

### 9.1 Compatibility Purpose

Constitutional amendment packages must analyze compatibility with remaining constitutional structure and identified constraints—not merely append isolated text.

### 9.2 Required Compatibility Analysis

Before Engineering Review completion, each CAP shall address:

1. Relationship to superior or interdependent Kansas constitutional provisions  
2. Whether the proposal creates internal contradiction risks  
3. Whether statutory/regulatory dependencies will be orphaned or overbroad if the amendment were adopted (engineering dependency note; not a prediction of political outcome)  
4. Whether the package improperly mixes ordinary statutory policy into constitutional form without authorization  
5. Known conflict risks with applicable AGCL controls  

### 9.3 Compatibility Outcomes

| Outcome | Meaning |
|---|---|
| Compatible (engineering assessment) | No unresolved structural conflicts identified from available authority |
| Conditional | Conflicts/risks identified; mitigation or Human Engineer decision required |
| Conflict Reported | Material conflict recorded; escalation required |
| Unevaluable | Insufficient authority/text; `[CONSTITUTIONAL REVIEW REQUIRED]` |

### 9.4 Non-Fabrication Rule

Constitutional authority and constitutional meaning shall never be fabricated.  
Escalate contested interpretation rather than choosing a silent winner.

---

## 10. AGCL Integration

| Topic | Rule |
|---|---|
| Role | AGCL provides structural control framework relevant to liberty, authority limits, transparency, and related controls |
| Affinity | Primary control affinity for constitutional/structural packages where AGCL-applicable controls apply |
| Requirement | Assess AGCL applicability for every Kansas CAP |
| When required to cite | When package scope implicates AGCL-applicable controls |
| Ownership | AGCL remains owned by AGCL-Control-Documents |
| Method | Reference control identifiers; do not fork AGCL into shadow manager-owned controls |
| Conflict | Report conflicts between proposed constitutional text and applicable AGCL controls |

AGCL does not replace the Kansas Constitution.  
References do not imply ownership.

---

## 11. NBBF Integration

| Topic | Rule |
|---|---|
| Role | NBBF provides node-based budget and fiscal authority boundary controls |
| Requirement | Assess whether the constitutional proposal implicates fiscal/node budget architecture |
| When required to cite | When taxation, appropriations architecture, fiscal mandates, debt limits, or node budget authority are in constitutional scope |
| Ownership | NBBF remains owned by NBBF-Control-Documents |
| Method | Reference NBBF controls; coordinate with Budget Manager boundaries when that manager is Active |
| Conflict | Report fiscal-control conflicts; do not invent NBBF-compliant constitutional meaning |

If fiscal applicability is uncertain, record `[NBBF APPLICABILITY UNRESOLVED]` and escalate.

---

## 12. CDT Metadata Requirements

Every Kansas CAP shall include CDT-ready metadata sufficient for future twin modeling.

### 12.1 Minimum CDT Metadata

| Field | Requirement |
|---|---|
| Jurisdiction | `Kansas` |
| Layer ID | `KS-CONST` |
| Artifact Type | `CAP` |
| Package ID / Version | Stable identifiers |
| Target nodes | Exact article/section (and deeper) targets |
| Relationship edges | Amend / add / repeal / renumber / transfer links |
| Compatibility links | Related constitutional provisions analyzed |
| Control links | AGCL/NBBF/CDT references as applicable |
| Ratification pathway class | Documented pathway type |
| Lifecycle state | Current STD-008 state |
| Supersession link | Prior/successor package IDs when applicable |

### 12.2 CDT / UNBKE Readiness Rules

1. Identifiers shall be stable and unique.  
2. Target and relationship edges shall be explicit, not only narrative.  
3. Packages shall remain operable without CDT runtime or UNBKE.  
4. Future UNBKE indexing shall be additive; do not hard-depend on UNBKE.  
5. Ratification outcomes shall not be invented to satisfy twin completeness.

---

## 13. Traceability Requirements

### 13.1 Required Trace Elements

| Trace Element | Requirement |
|---|---|
| Exact article/section targets | Required |
| Existing vs proposed distinction method | Required |
| Source for existing constitutional text | Required or expressly flagged unresolved |
| Related constitutional provisions | Required |
| Amendment class and CA units | Required |
| Governing CWC-CE | Required for production work |
| Governing ECR / CEP / CER | Conditional per WF-001 |
| Standards applied | At minimum STD-008 and KLS-002; others as applicable |
| Control references | AGCL/NBBF/CDT as applicable |
| Ratification pathway record | Required (documented, not simulated) |
| Review outcomes | Engineering/legal/public as applicable |
| Publication approvals | When published |
| Uncertainty/conflict log | Required when any unresolved item exists |

### 13.2 Traceability Rule

A Kansas CAP lacking exact targets (or blocking unresolved-target flags), existing-vs-proposed distinction, version, and lifecycle state is incomplete and shall not enter Approved status.

---

## 14. Engineering Review Requirements

### 14.1 Review Gates

Kansas CAPs shall pass through applicable STD-008 review states before approval:

| Review | Focus |
|---|---|
| Engineering Review | Structure, metadata, exact targeting, existing-vs-proposed clarity, traceability, interface/ownership conformance, ratification pathway documentation |
| Legal Review | Constitutional compatibility against declared sources; amendatory exactness; pathway/legal-process questions |
| Public Review | Only when required by authorizing work or Human Engineer direction |

### 14.2 Engineering Review Minimum Checks

1. Engineer-before-draft sequence followed  
2. Artifact type is `CAP` and layer is `KS-CONST`  
3. Exact article/section targets present for every CA unit  
4. Existing constitution distinguished from proposed constitution  
5. No fabricated constitutional authority or text  
6. Compatibility analysis completed or escalated  
7. AGCL/NBBF/CDT applicability assessed  
8. CDT metadata present  
9. Ratification pathway documented without simulated outcomes  
10. Publication readiness accurately stated  
11. No disguised statutory bill used in place of CAP  
12. No out-of-scope repository modifications  

### 14.3 Review Outcomes

`Pass` / `Partial` / `Fail` / `Not performed`  
Unperformed review shall not be reported as complete.  
Constitutional packages with material unresolved targets default to Fail or Partial; they shall not be treated as Pass.

---

## 15. Publication Requirements

1. Every CAP shall be structurally publication-ready before approval for publication.  
2. Publication-ready means:
   - required architecture/metadata complete for Approved posture  
   - exact targets complete or expressly Human-Engineer-deferred  
   - existing-vs-proposed distinction clear  
   - traceability complete  
   - ratification pathway documented  
   - unresolved items closed or expressly accepted as open but non-blocking  
   - no fabricated authorities or simulated ratification outcomes presented as fact  
3. Legislative Manager may prepare publication packages; Legislative Manager may not self-publish.  
4. Only Human Engineer-approved artifacts enter public channels under WF-001.  
5. Draft/in-review/failed/partial packages are not published unless expressly authorized as such.  
6. Publication of an engineering CAP is not ratification and does not amend the Kansas Constitution by itself.

---

## 16. Ratification Workflow

### 16.1 Documentation Mandate

Ratification workflow shall be documented but not simulated.

### 16.2 Purpose of this Section

This section records the engineering representation of the pathway by which a proposed Kansas constitutional amendment would be pursued under applicable Kansas process classes.  
It does not execute, predict, or invent ratification results.

### 16.3 Required Ratification Pathway Record

Every CAP shall include a Ratification Pathway Record containing:

| Field | Requirement |
|---|---|
| Pathway Class | Documented class (examples below) |
| Governing Process References | Cited Kansas constitutional/statutory process loci when known |
| Required Steps (engineering list) | Ordered process steps as understood from cited authority |
| Evidence Needed for Status Changes | What source records would be required to update status |
| Current Engineering Status | Status value from Section 16.5 |
| Outcome Fields | Remain empty/`Not occurred` unless verified by source authority |
| Uncertainty | Explicit gaps in process understanding |

### 16.4 Illustrative Pathway Classes

Use only when supported by cited authority or mark as unresolved:

1. Legislative referral pathway  
2. Initiative / petition pathway (if applicable under cited authority)  
3. Convention-related pathway (if applicable under cited authority)  
4. Other pathway expressly identified by cited Kansas authority  
5. `[PATHWAY UNRESOLVED]` — blocking for Approved/Published unless Human Engineer defers

Do not invent a pathway class to satisfy completeness.

### 16.5 Ratification Engineering Status Values

| Status | Meaning |
|---|---|
| Pathway Documented | Process class and steps recorded; no claim of progress beyond engineering |
| Referred / Submitted (verified) | Only if source authority confirms and Human Engineer accepts |
| Before Voters (verified) | Only if source authority confirms |
| Adopted / Ratified (verified) | Only if source authority confirms |
| Rejected / Failed (verified) | Only if source authority confirms |
| Not Simulated | Default reminder state annotation when no external process has occurred |
| Unresolved | Pathway or status cannot be honestly stated |

### 16.6 Non-Simulation Rules

1. Do not fabricate vote counts, petition signatures, election dates, or canvassing results.  
2. Do not mark a CAP as ratified because the engineering package is Approved or Published.  
3. Do not run mock ratification workflows that could be mistaken for official process records.  
4. Hypothetical examples, if used in discussion, shall be labeled hypothetical and excluded from package status fields.  
5. Status transitions beyond Pathway Documented require cited external authority evidence plus Human Engineer acceptance.

---

## 17. Lifecycle States

Kansas CAPs follow STD-008:

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

### 17.1 State Meanings for Kansas CAPs

| State | Meaning |
|---|---|
| Proposed | Constitutional need/concept captured; identity may exist; operative amendatory draft not required yet |
| Draft | Active engineering and authorized drafting underway |
| Engineering Review | Structure/metadata/targeting/traceability/pathway documentation under review |
| Legal Review | Compatibility and process/authority review against declared sources |
| Public Review | Stakeholder/public package issued when required |
| Approved | Human Engineer authorization for publication path of the engineering package |
| Published | Engineering package released through approved publication channel |
| Superseded | Replaced by successor CAP version/ID |
| Archived | Historical retention only |

### 17.2 Lifecycle Clarifications

1. Approved / Published refer to the engineering package, not constitutional ratification.  
2. Ratification Status is tracked separately under Section 16 and shall not be collapsed into STD-008 states.  
3. AI may recommend transitions; AI may not self-approve Approved or Published.  
4. Failed reviews return the package to Draft or remain in review with recorded defects.  
5. Supersession shall record successor identity.

---

## 18. Quality Checklist

Before presenting a Kansas CAP for Human Engineer review or approval, verify:

| # | Check | Required |
|---|---|---|
| 1 | Authorizing CWC-CE / CEP identified for production work | Yes |
| 2 | Engineer-before-draft sequence completed | Yes |
| 3 | Package ID, title, type `CAP`, layer `KS-CONST`, version present | Yes |
| 4 | Complete constitutional metadata present | Yes |
| 5 | Every amendatory unit identifies exact article and section | Yes |
| 6 | Existing constitution distinguished from proposed constitution | Yes |
| 7 | No fabricated constitutional authority or text | Yes |
| 8 | Compatibility analysis completed or escalated | Yes |
| 9 | AGCL applicability assessed; cited when required | Yes |
| 10 | NBBF applicability assessed; cited when required | Yes |
| 11 | CDT metadata present | Yes |
| 12 | Traceability block complete | Yes |
| 13 | Ratification pathway documented | Yes |
| 14 | Ratification outcomes not simulated or invented | Yes |
| 15 | Lifecycle state correct; Approved/Published not conflated with ratification | Yes |
| 16 | Publication readiness accurately declared | Yes |
| 17 | Uncertainty escalated rather than hidden | Yes |
| 18 | Package supports future CDT/UNBKE mapping without hard dependency | Yes |
| 19 | Package is not a disguised KLS-001 statutory bill | Yes |

Any failed required check blocks a claim of completion.

---

## 19. Conformance

1. Conformance to KLS-002 is mandatory for Kansas constitutional amendment packages engineered by Legislative Manager after this standard’s Effective Date, subject to Human Engineer activation/acceptance of this Draft if required by Office practice.  
2. Nonconformance is an engineering defect and shall be corrected before Approved/Published states.  
3. Exceptions require explicit Human Engineer approval and shall record reason, scope, duration/terminal condition, approver, and date.  
4. An exception never authorizes fabricated constitutional authority, simulated ratification, false verification, or undisclosed scope expansion.  
5. Conformance does not require UNBKE.  
6. KLS-001 remains the standard for Kansas bills; conflicts in package classification escalate to the Human Engineer.  
7. Reserved Office standards remain superior or complementary when Active; conflicts escalate.

---

## 20. Version History

| Version | Date | Summary |
|---|---|---|
| 1.0.0 | 2026-08-08 | Initial Kansas Constitutional Amendment Engineering Standard establishing canonical engineering rules for Kansas CAP packages, including documented non-simulated ratification workflow. |
