# KLS-004 — Kansas Fiscal Note Engineering Standard

**Document ID:** KLS-004  
**Title:** Kansas Fiscal Note Engineering Standard  
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
**Related Kansas Standards:** KLS-001; KLS-002; KLS-003  
**Governing Prompt:** Legislative Manager Operating Manual  
**Jurisdiction:** State of Kansas  
**Status:** Draft  
**Version:** 1.0.0  
**Effective Date:** 2026-08-08  

---

## 1. Purpose

This document establishes the canonical engineering standard governing the creation, review, traceability, publication, and lifecycle of Kansas fiscal note packages associated with legislative and constitutional engineering artifacts under Legislative Manager.

It exists to ensure that every Kansas fiscal note package:

1. Identifies assumptions for every fiscal estimate  
2. Separates revenue effects from expenditure effects  
3. Identifies node-level impacts where applicable  
4. Distinguishes measured data from projections  
5. Preserves traceability to supporting data sources  
6. Identifies unknown values rather than inventing them  
7. Integrates AGCL and NBBF references without claiming control ownership  
8. Supports future CDT and UNBKE integration without hard runtime dependency  

KLS-004 does not prepare a fiscal note for any specific bill and does not invent fiscal data or legal authority.

---

## 2. Scope

### 2.1 In Scope

This standard applies to Kansas fiscal note engineering packages associated with:

1. Kansas bill packages under KLS-001  
2. Kansas constitutional amendment packages under KLS-002 when fiscal effects are implicated  
3. Kansas statutory revision packages under KLS-003 when fiscal effects are implicated  
4. Related legislative engineering artifacts under SPEC-001 that require fiscal-effect documentation  
5. Companion assumptions registers, data-source logs, node-impact maps, and uncertainty/sensitivity records  

### 2.2 Out of Scope

This standard does not:

1. Prepare or approve a fiscal note for any specific bill, amendment, or revision  
2. Enact appropriations, set tax rates, or determine Kansas budget policy outcomes  
3. Replace Budget Manager domain ownership when that manager is Active for primary budget engineering  
4. Modify KLS-001, KLS-002, KLS-003, Engineering Office documents, AGCL, NBBF, or CDT  
5. Own NBBF controls or redefine NBBF concepts  
6. Require UNBKE or any specific estimating tool/vendor  

### 2.3 Relationship to Other Authorities

```
ARCH-001 / ARCH-002 / ARCH-003 / ARCH-004
        ↓
POL-001 / WF-001 / STD-008 / STD-014 / STD-015
        ↓
SPEC-001
        ↓
KLS-001 / KLS-002 / KLS-003  (parent legislative artifacts)
        ↓
KLS-004 (fiscal note packages linked to parent artifacts)
        ↓
NBBF references (control affinity; no ownership transfer)
```

Fiscal notes are companion engineering artifacts.  
They do not replace parent bill/CAP/revision packages and do not themselves enact fiscal law.  
Where Budget Manager is Active and scope is primarily budget-architecture engineering, Legislative Manager shall coordinate through defined interfaces and shall not absorb NBBF ownership.

---

## 3. Authority

1. KLS-004 is issued under Constitutional Engineering Office authority and owned by Legislative Manager for Kansas fiscal-note engineering associated with legislative artifacts.  
2. KLS-004 is subordinate to ARCH-001 through ARCH-004, POL-001, WF-001, STD-008, and SPEC-001.  
3. NBBF controls remain owned by NBBF-Control-Documents.  
4. AGCL and CDT controls remain owned by their respective repositories.  
5. AI may prepare fiscal note packages under authorized work; AI never owns the packages and never grants Human Engineer approval.  
6. AI shall not invent measured data, fabricate citations to fiscal sources, or present projections as measured facts.  
7. Production use proceeds through WF-001 authorization gates.  
8. Unknown values shall be identified and escalated rather than invented.

---

## 4. Fiscal Note Package Architecture

### 4.1 Engineer-Before-Estimate Rule

Every Kansas fiscal note shall be engineered before numeric estimates are finalized for review:

1. Confirm authorizing CWC-CE / CEP  
2. Link parent legislative artifact identity (bill/CAP/revision)  
3. Establish package identity, version, and lifecycle state  
4. Build Assumptions Register  
5. Identify data sources and classify measured vs projected inputs  
6. Structure separate revenue and expenditure analyses  
7. Perform node impact analysis where applicable  
8. Record uncertainty/sensitivity  
9. Only then finalize estimate tables for Human Engineer review  

### 4.2 Logical Package Structure

```
Fiscal Note Package
├── Identity / Manifest
├── Parent Artifact Linkage
├── Engineering Summary
├── Fiscal Scope Statement
├── Revenue Analysis
├── Expenditure Analysis
├── Net Effect Summary (derived; not a substitute for separated analyses)
├── Node Impact Analysis
├── Assumptions Register
├── Data Source Log
├── Uncertainty and Sensitivity Analysis
├── Control Integration (AGCL / NBBF / CDT)
├── CDT Metadata
├── Traceability Block
├── Review Records
├── Publication Package (when prepared)
└── Version History
```

### 4.3 Identity Pattern

Recommended fiscal note package identifier pattern:

```text
KS-STAT-FISC-NNN
```

For constitutional-parent notes, an authorized variant may be used if clearly linked:

```text
KS-CONST-FISC-NNN
```

Rules:

1. Every fiscal note shall link to one primary parent artifact ID/version.  
2. Companion notes for multiple parents require either separate packages or an explicit multi-parent map approved in metadata.  
3. Filename convention: `{Package-ID}-{Short-Title}.md` or approved equivalent package folder name.

### 4.4 Recommended Repository Placement

Place under the Kansas state engineering tree authorized by SPEC-001, for example:

```text
Legislative-Manager/templates/State/Kansas/
```

or a successor fiscal-notes subdirectory created only under authorized CWC-CE / CEP scope.

### 4.5 Separation Rule

Revenue and expenditure effects shall be analyzed in separate sections before any netting summary.  
A net-only fiscal note with no separated analyses is nonconforming.

---

## 5. Revenue Analysis

### 5.1 Purpose

Revenue Analysis identifies estimated effects on revenues attributable to the parent artifact.

### 5.2 Required Revenue Fields

| Field | Requirement |
|---|---|
| Revenue category | Tax, fee, fine, federal receipt, other receipt, forgone revenue, etc. |
| Direction | Increase / decrease / shift / indeterminate |
| Amounting basis | Point estimate, range, or qualitative-only |
| Amount / range | Numeric values only when supported; otherwise `[UNKNOWN]` |
| Timing | Fiscal year(s) / effective periods affected |
| Incidence note | Who pays/receives at engineering level of known detail |
| Measured vs projected | Classification per Section 9 |
| Assumption links | IDs from Assumptions Register |
| Data source links | IDs from Data Source Log |
| Uncertainty links | IDs from Uncertainty/Sensitivity records |
| Node links | Node IDs when node-level revenue impacts apply |

### 5.3 Revenue Analysis Rules

1. Do not net revenue into expenditure lines.  
2. Forgone revenue is a revenue-side effect and shall be labeled as such.  
3. Transfers that are not new revenue shall be identified as shifts, not inflated as new receipts, unless source authority supports otherwise.  
4. If revenue effect cannot be estimated, record `[REVENUE EFFECT UNKNOWN]` with reasons; do not invent a number.  
5. Distinguish one-time from recurring revenue effects when known.

---

## 6. Expenditure Analysis

### 6.1 Purpose

Expenditure Analysis identifies estimated effects on expenditures/costs attributable to the parent artifact.

### 6.2 Required Expenditure Fields

| Field | Requirement |
|---|---|
| Expenditure category | Operating, capital, personnel, benefits, grants, debt service, IT, other |
| Direction | Increase / decrease / shift / indeterminate |
| Amounting basis | Point estimate, range, or qualitative-only |
| Amount / range | Numeric values only when supported; otherwise `[UNKNOWN]` |
| Timing | Fiscal year(s) / ramp-up / sunset periods |
| Fund / account note | If known; otherwise unresolved |
| Implementing entity | Agency/unit if known |
| Measured vs projected | Classification per Section 9 |
| Assumption links | Assumptions Register IDs |
| Data source links | Data Source Log IDs |
| Uncertainty links | Uncertainty/Sensitivity IDs |
| Node links | Node IDs when node-level expenditure impacts apply |

### 6.3 Expenditure Analysis Rules

1. Do not hide expenditure effects inside revenue narrative.  
2. Cost avoidance shall be labeled distinctly and not treated as cash revenue.  
3. Mandates on local units shall be identified even when state General Fund impact appears zero.  
4. If expenditure effect cannot be estimated, record `[EXPENDITURE EFFECT UNKNOWN]` with reasons; do not invent a number.  
5. Distinguish one-time from recurring expenditure effects when known.

---

## 7. Node Impact Analysis

### 7.1 Node Impact Mandate

Node-level impacts shall be identified where applicable, especially when NBBF-relevant fiscal/node budget architecture is implicated.

### 7.2 Node Impact Record Fields

| Field | Requirement |
|---|---|
| Node ID / label | Stable node identifier or explicit unresolved marker |
| Node type | State / county / city / school / agency / fund-node / other |
| Impact channel | Revenue / expenditure / authority boundary / transfer / reporting |
| Direction and magnitude posture | Linked to revenue/expenditure lines or qualitative |
| NBBF control references | When applicable |
| Parent artifact linkage | Parent package section/provision causing impact |
| Assumption / source / uncertainty links | Required when quantified |
| Status | Identified / Quantified / Qualitative only / Unresolved |

### 7.3 Node Impact Rules

1. If parent artifact affects multiple jurisdictions or budget nodes, list each material node or document aggregation method and residual risk.  
2. “Statewide only” summaries are insufficient when local-node mandates are material and identifiable.  
3. Do not invent node IDs; if unknown, mark `[NODE UNRESOLVED]`.  
4. Node Impact Analysis does not transfer NBBF ownership to Legislative Manager.  
5. When Budget Manager is Active, node-architecture conflicts escalate through defined interfaces.

---

## 8. Assumptions Register

### 8.1 Assumptions Mandate

Every fiscal estimate shall identify its assumptions.

### 8.2 Required Assumption Fields

| Field | Requirement |
|---|---|
| Assumption ID | Stable ID (example: `A-NNN`) |
| Statement | Precise assumption text |
| Applies to | Revenue / expenditure / node lines affected |
| Basis | Why assumption is used |
| Classification | Behavioral / timing / rate / population / inflation / compliance / other |
| Measured vs projected dependency | Whether assumption rests on measured data, projection, or both |
| Sensitivity | High / medium / low / unknown |
| Status | Active / Retired / Replaced |
| Replacement | Successor assumption ID if replaced |

### 8.3 Assumptions Rules

1. An estimate without linked assumptions is nonconforming.  
2. Hidden assumptions in narrative prose are insufficient; register entries are required.  
3. If an assumption is speculative, label it speculative and escalate confidence limits.  
4. Changing an assumption in a later package version shall preserve prior assumption history through version management.  
5. Do not invent “consensus” assumptions without stated basis.

---

## 9. Data Source Requirements

### 9.1 Data Source Mandate

Every estimate shall preserve traceability to supporting data.

### 9.2 Required Data Source Fields

| Field | Requirement |
|---|---|
| Source ID | Stable ID (example: `DS-NNN`) |
| Source name | Document, dataset, system, or authority |
| Publisher / steward | If known |
| Date / vintage | As-of date or version |
| Access reference | Citation, path, or locator |
| Data class | Measured data / projection / mixed / qualitative authority |
| Used by | Estimate lines / assumptions supported |
| Limitations | Coverage gaps, latency, definitional mismatches |
| Verification status | Verified / Unverified / Unresolvable |

### 9.3 Measured Data vs Projections

Fiscal notes shall distinguish measured data from projections.

| Class | Meaning |
|---|---|
| Measured data | Observed/reported historical or current values from identified sources |
| Projection | Forward estimate derived from models, trends, assumptions, or scenarios |
| Mixed | Combines measured baselines with projected deltas; both parts must be separable |
| Qualitative authority | Non-numeric authoritative statement used to bound effects |

### 9.4 Data Source Rules

1. Presenting a projection as measured data is nonconforming.  
2. Unsourced numbers are nonconforming.  
3. If no reliable source exists, record `[DATA SOURCE UNAVAILABLE]` and keep the estimate qualitative or unknown.  
4. Do not fabricate datasets, reports, or citations.  
5. Source limitations shall be stated when material to confidence.

---

## 10. Uncertainty and Sensitivity Analysis

### 10.1 Unknown Values Mandate

Unknown values shall be identified rather than invented.

### 10.2 Uncertainty Record Fields

| Field | Requirement |
|---|---|
| Uncertainty ID | Stable ID (example: `U-NNN`) |
| Subject | Estimate line / node / assumption affected |
| Nature | Data gap / behavioral uncertainty / timing uncertainty / legal contingency / other |
| Effect on estimate | Directional impact if known |
| Range / scenario | If quantifiable; otherwise qualitative |
| Mitigation | Additional data needed / legal review / deferral |
| Status | Open / Accepted residual / Closed |

### 10.3 Sensitivity Analysis Requirements

Where quantified estimates are presented, provide at least one of:

1. Low/central/high scenarios, or  
2. Key-assumption toggles showing estimate response, or  
3. Explicit statement that sensitivity cannot be quantified, with reasons  

### 10.4 Uncertainty Rules

1. Point estimates with high sensitivity and no uncertainty disclosure are nonconforming.  
2. Legal contingencies (for example pending constitutional questions) shall be listed when material.  
3. Do not collapse uncertainty into false precision.  
4. Accepted residual uncertainty requires Human Engineer acknowledgment to reach Approved when material.

---

## 11. AGCL Integration

| Topic | Rule |
|---|---|
| Role | AGCL provides structural control framework relevant to liberty, authority limits, transparency, and related controls |
| Requirement | Assess whether fiscal-note content or parent artifact implicates AGCL-applicable controls (including transparency/authority-boundary concerns) |
| When required to cite | When package scope implicates AGCL-applicable controls |
| Ownership | AGCL remains owned by AGCL-Control-Documents |
| Method | Reference control identifiers; do not fork AGCL |
| Conflict | Report conflicts; escalate rather than invent reconciliation |

References do not imply ownership.

---

## 12. NBBF Integration

| Topic | Rule |
|---|---|
| Role | NBBF provides node-based budget and fiscal authority boundary controls |
| Affinity | Primary fiscal-control affinity for Kansas fiscal note packages |
| Requirement | Assess NBBF applicability for every Kansas fiscal note |
| When required to cite | When revenues, expenditures, node impacts, transfers, or fiscal authority boundaries are estimated or discussed |
| Ownership | NBBF remains owned by NBBF-Control-Documents |
| Method | Reference NBBF controls; align node impact records to NBBF concepts without redefining them |
| Coordination | When Budget Manager is Active, coordinate budget-architecture conflicts through defined interfaces |
| Conflict | Report fiscal-control conflicts; do not invent NBBF-compliant estimates |

If NBBF applicability is uncertain, record `[NBBF APPLICABILITY UNRESOLVED]` and escalate.  
KLS-004 authorizes fiscal-note engineering references to NBBF; it does not authorize Legislative Manager ownership of NBBF.

---

## 13. CDT Metadata

Every Kansas fiscal note package shall include CDT-ready metadata sufficient for future twin modeling.

### 13.1 Minimum CDT Metadata

| Field | Requirement |
|---|---|
| Jurisdiction | `Kansas` |
| Artifact class | Fiscal note |
| Package ID / Version | Stable identifiers |
| Parent artifact link | Parent bill/CAP/revision ID + version |
| Revenue nodes/lines | Identifiers for revenue analysis units |
| Expenditure nodes/lines | Identifiers for expenditure analysis units |
| Node impact edges | Links to affected fiscal/jurisdictional nodes |
| Assumption edges | Links from estimates to `A-NNN` |
| Data source edges | Links from estimates/assumptions to `DS-NNN` |
| Uncertainty edges | Links to `U-NNN` |
| Control links | AGCL/NBBF/CDT references as applicable |
| Measured vs projected flags | Explicit on estimate inputs |
| Lifecycle state | Current STD-008 state |
| Supersession link | Prior/successor package IDs when applicable |

### 13.2 CDT / UNBKE Readiness Rules

1. Identifiers shall be stable and unique.  
2. Estimate-to-assumption-to-source edges shall be explicit.  
3. Packages shall remain operable without CDT runtime or UNBKE.  
4. Future UNBKE indexing shall be additive; do not hard-depend on UNBKE.  
5. Do not invent numeric edges to appear complete.

---

## 14. Traceability Requirements

### 14.1 Required Trace Elements

| Trace Element | Requirement |
|---|---|
| Parent artifact ID/version | Required |
| Separated revenue analysis | Required (or explicit `No revenue effect` with basis) |
| Separated expenditure analysis | Required (or explicit `No expenditure effect` with basis) |
| Assumptions Register | Required for every quantified estimate |
| Data Source Log | Required for every sourced value |
| Measured vs projected classification | Required |
| Node Impact Analysis | Required where applicable; otherwise explicit non-applicability basis |
| Uncertainty/sensitivity records | Required for quantified estimates and material unknowns |
| Governing CWC-CE | Required for production work |
| Governing ECR / CEP / CER | Conditional per WF-001 |
| Standards applied | At minimum STD-008 and KLS-004; parent KLS-001/002/003 as applicable |
| Control references | AGCL/NBBF/CDT as applicable |
| Review outcomes | Engineering/legal/public as applicable |
| Publication approvals | When published |

### 14.2 Traceability Rule

A fiscal note lacking parent linkage, assumptions for estimates, measured-vs-projected classification, and lifecycle/version identity is incomplete and shall not enter Approved status.  
Unknowns left unstated are nonconforming.

---

## 15. Engineering Review Requirements

### 15.1 Review Gates

Fiscal note packages follow applicable STD-008 states:

```
Proposed → Draft → Engineering Review → Legal Review → Public Review
 → Approved → Published → Superseded → Archived
```

| Review | Focus |
|---|---|
| Engineering Review | Architecture completeness, separated revenue/expenditure analyses, assumptions, sources, node impacts, uncertainty, CDT metadata, NBBF/AGCL reference integrity |
| Legal Review | Authority/process questions tied to parent artifact and any claimed mandatory fiscal-note legal posture, against declared sources |
| Public Review | Only when required by authorizing work or Human Engineer direction |

### 15.2 Engineering Review Minimum Checks

1. Parent artifact linked  
2. Revenue and expenditure analyzed separately  
3. Every estimate linked to assumptions  
4. Measured data distinguished from projections  
5. Unknowns explicitly identified  
6. Data sources present for sourced values  
7. Node impacts identified where applicable  
8. Uncertainty/sensitivity disclosed for quantified estimates  
9. AGCL/NBBF/CDT applicability assessed  
10. No invented numbers or fabricated sources  
11. Publication readiness accurately stated  
12. No out-of-scope repository modifications  

### 15.3 Review Outcomes

`Pass` / `Partial` / `Fail` / `Not performed`  
Unperformed review shall not be reported as complete.  
Invented precision or missing assumptions defaults to Fail.

---

## 16. Publication Requirements

1. Every fiscal note package shall be structurally publication-ready before approval for publication.  
2. Publication-ready means:
   - parent linkage complete  
   - separated revenue/expenditure analyses complete or expressly non-applicable with basis  
   - assumptions and sources complete for presented estimates  
   - unknowns disclosed  
   - measured vs projected labels accurate  
   - unresolved items closed or expressly accepted as open but non-blocking by Human Engineer  
   - no fabricated data  
3. Legislative Manager may prepare publication packages; Legislative Manager may not self-publish.  
4. Only Human Engineer-approved artifacts enter public channels under WF-001.  
5. Draft/in-review/failed/partial packages are not published unless expressly authorized as such.  
6. Publication of a fiscal note does not enact appropriations, taxes, or budget law.  
7. Fiscal notes shall not be presented as guaranteeing future fiscal outcomes.

---

## 17. Quality Checklist

Before presenting a Kansas fiscal note package for Human Engineer review or approval, verify:

| # | Check | Required |
|---|---|---|
| 1 | Authorizing CWC-CE / CEP identified for production work | Yes |
| 2 | Parent legislative/constitutional artifact linked by ID/version | Yes |
| 3 | Package identity, version, lifecycle state present | Yes |
| 4 | Revenue effects analyzed separately (or explicit non-applicability basis) | Yes |
| 5 | Expenditure effects analyzed separately (or explicit non-applicability basis) | Yes |
| 6 | Every fiscal estimate identifies its assumptions | Yes |
| 7 | Unknown values identified rather than invented | Yes |
| 8 | Measured data distinguished from projections | Yes |
| 9 | Data sources traced for sourced values | Yes |
| 10 | Node-level impacts identified where applicable | Yes |
| 11 | Uncertainty/sensitivity disclosed for quantified estimates | Yes |
| 12 | AGCL applicability assessed; cited when required | Yes |
| 13 | NBBF applicability assessed; cited when required | Yes |
| 14 | CDT metadata present | Yes |
| 15 | Traceability block complete | Yes |
| 16 | No fabricated sources, numbers, or false precision | Yes |
| 17 | Publication readiness accurately declared | Yes |
| 18 | Package supports future CDT/UNBKE mapping without hard dependency | Yes |
| 19 | NBBF ownership not claimed; Budget Manager boundaries respected | Yes |

Any failed required check blocks a claim of completion.

---

## 18. Conformance

1. Conformance to KLS-004 is mandatory for Kansas fiscal note packages engineered by Legislative Manager after this standard’s Effective Date, subject to Human Engineer activation/acceptance of this Draft if required by Office practice.  
2. Nonconformance is an engineering defect and shall be corrected before Approved/Published states.  
3. Exceptions require explicit Human Engineer approval and shall record reason, scope, duration/terminal condition, approver, and date.  
4. An exception never authorizes invented data, hidden assumptions, false verification, or undisclosed scope expansion.  
5. Conformance does not require UNBKE.  
6. Parent artifact standards (KLS-001/002/003) remain independently mandatory for those artifacts.  
7. NBBF and Budget Manager boundaries remain binding; KLS-004 does not expand Legislative Manager into NBBF ownership.  
8. Reserved Office standards remain superior or complementary when Active; conflicts escalate.

---

## 19. Version History

| Version | Date | Summary |
|---|---|---|
| 1.0.0 | 2026-08-08 | Initial Kansas Fiscal Note Engineering Standard establishing separated revenue/expenditure analysis, assumptions register, data-source and uncertainty rules, node impact analysis, and AGCL/NBBF/CDT integration for Kansas fiscal note packages. |
