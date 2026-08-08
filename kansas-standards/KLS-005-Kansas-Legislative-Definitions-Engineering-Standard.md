# KLS-005 — Kansas Legislative Definitions Engineering Standard

**Document ID:** KLS-005  
**Title:** Kansas Legislative Definitions Engineering Standard  
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
**Related Kansas Standards:** KLS-001; KLS-002; KLS-003; KLS-004  
**Governing Prompt:** Legislative Manager Operating Manual  
**Jurisdiction:** State of Kansas  
**Status:** Draft  
**Version:** 1.0.0  
**Effective Date:** 2026-08-08  

---

## 1. Purpose

This document establishes the canonical engineering standard governing the creation, maintenance, revision, traceability, publication, and lifecycle of definitions used throughout Kansas legislative engineering artifacts under Legislative Manager.

It exists to ensure that every Kansas legislative definition:

1. Has one authoritative meaning within its declared scope  
2. Reuses existing controlling definitions when appropriate rather than silently duplicating them  
3. Preserves version history across changes  
4. Detects and escalates conflicts instead of hiding them  
5. Distinguishes existing legal definitions from newly proposed definitions  
6. Remains compatible with constitutional and control-document boundaries  
7. Supports future CDT and UNBKE integration without hard runtime dependency  

KLS-005 does not draft definitions for any specific bill and does not invent legal authority.

---

## 2. Scope

### 2.1 In Scope

This standard applies to definition engineering for Kansas legislative artifacts, including definitions used in or accompanying:

1. Kansas bill packages under KLS-001  
2. Kansas constitutional amendment packages under KLS-002, when definitional terms are introduced or altered  
3. Kansas statutory revision packages under KLS-003  
4. Kansas fiscal note packages under KLS-004, when fiscal terms require engineered definitions  
5. Standalone Kansas definition registers, glossaries, and definition maps under Legislative Manager  
6. Cross-reference, conflict-detection, reuse, and versioning records for the above  

### 2.2 Out of Scope

This standard does not:

1. Draft definitions for any specific bill, CAP, revision, or fiscal note  
2. Determine Kansas political or legal policy outcomes  
3. Replace KLS-001/002/003/004 package architecture for parent artifacts  
4. Govern non-Kansas jurisdictions unless expressly authorized by later standards  
5. Modify KLS-001 through KLS-004, Engineering Office documents, AGCL, NBBF, or CDT  
6. Require UNBKE or any specific terminology tool  

### 2.3 Relationship to Other Authorities

```
ARCH-001 / ARCH-002 / ARCH-003 / ARCH-004
        ↓
POL-001 / WF-001 / STD-008 / STD-014 / STD-015
        ↓
SPEC-001
        ↓
KLS-001 / KLS-002 / KLS-003 / KLS-004  (parent artifacts)
        ↓
KLS-005 (definition engineering for terms used across those artifacts)
```

Definitions are engineering-controlled semantic units.  
They do not, by themselves, enact law.  
Where a parent package standard and KLS-005 both apply, both are binding.  
Conflicts escalate to the Human Engineer.

---

## 3. Authority

1. KLS-005 is issued under Constitutional Engineering Office authority and owned by Legislative Manager.  
2. KLS-005 is subordinate to ARCH-001 through ARCH-004, POL-001, WF-001, STD-008, and SPEC-001.  
3. Existing Kansas constitutional and statutory definitions remain legal source authority when cited; this standard governs engineering handling of those definitions and proposed changes.  
4. AGCL, NBBF, and CDT remain owned by their control repositories; KLS-005 authorizes reference, not ownership.  
5. AI may prepare definition records under authorized work; AI never owns definitions and never grants Human Engineer approval.  
6. AI shall not invent controlling definitions, fabricate citations to existing definitional loci, or silently resolve conflicts.  
7. Production use proceeds through WF-001 authorization gates.

---

## 4. Definition Architecture

### 4.1 Engineer-Before-Draft Rule

Definition work shall be engineered before proposed definitional text is finalized for review:

1. Confirm authorizing CWC-CE / CEP and parent artifact linkage (if any)  
2. Identify the term and intended scope  
3. Search for existing controlling definitions  
4. Classify the action (reuse / cite / adapt / propose new / revise existing)  
5. Record identity, version, and lifecycle state  
6. Run conflict detection  
7. Only then draft or revise authorized definition text  

### 4.2 Logical Definition Record Structure

```
Definition Record
├── Identity
├── Term / Aliases
├── Scope Declaration
├── Classification
├── Existing Definition Analysis (when applicable)
├── Proposed / Authoritative Definition Text
├── Reuse / Inheritance Links
├── Cross-Reference Map
├── Conflict Log
├── Version History
├── Constitutional Compatibility
├── Control Integration (AGCL / NBBF / CDT)
├── CDT Metadata
├── Traceability Block
└── Review / Publication Status
```

### 4.3 Definition Set / Register Architecture

A Kansas package may contain:

1. Inline Definitions section (package-local)  
2. Linked Definition Register entries (reusable across packages)  
3. Hybrid model with inline short forms pointing to register IDs  

Either model is conforming if every defined term has one authoritative definition within its declared scope and unresolved conflicts are escalated.

### 4.4 One-Authority-Within-Scope Rule

Every defined term shall have one authoritative definition within its scope.  
Multiple contextual senses require either:

- distinct scoped terms, or  
- expressly engineered sense qualifiers with non-overlapping scope declarations  

Silent dual meanings inside one scope are nonconforming.

---

## 5. Definition Identity

### 5.1 Required Identity Fields

| Field | Required | Description |
|---|---|---|
| Definition ID | Yes | Stable unique identifier |
| Term | Yes | Canonical term string |
| Normalized Term Key | Yes | Case/spacing-normalized key for matching |
| Aliases | Conditional | Alternate labels explicitly mapped to the same Definition ID |
| Jurisdiction | Yes | `Kansas` |
| Scope Type | Yes | Constitutional / statutory / package-local / chapter / act / fiscal / other |
| Scope Locus | Yes | Exact locus or package ID bounding authority of the definition |
| Layer ID | Yes | Typically `KS-CONST` or `KS-STAT` (or authorized) |
| Parent Artifact ID | Conditional | Required when definition is introduced by a package |
| Status / Lifecycle State | Yes | Per Section 6 |
| Version | Yes | Semantic version of the definition record |
| Owning Manager | Yes | Legislative Manager |

### 5.2 Identifier Pattern

Recommended Definition ID pattern:

```text
KS-DEF-NNN
```

Scoped package-local temporary IDs may be used during Draft if mapped to a stable `KS-DEF-NNN` before Approved, or expressly retained as package-local with unique package-qualified identity:

```text
{ParentPackageID}::DEF-NNN
```

### 5.3 Identity Rules

1. Definition IDs are never reused for a different term sense.  
2. Term renames that preserve meaning keep the Definition ID and record alias history.  
3. Meaning splits create new Definition IDs and supersession links.  
4. Aliases do not create separate authoritative definitions.

---

## 6. Definition Lifecycle

Definitions follow STD-008-aligned lifecycle states, specialized for semantic units:

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

### 6.1 State Meanings

| State | Meaning |
|---|---|
| Proposed | Term need identified; authoritative text not yet engineered |
| Draft | Active engineering of definition text/scope/links |
| Engineering Review | Identity, reuse, conflict, cross-reference, and metadata review |
| Legal Review | Compatibility with cited legal sources and parent artifact authority |
| Public Review | Only when required by authorizing work or Human Engineer direction |
| Approved | Human Engineer authorization for use/publication path |
| Published | Released through approved publication channel as part of package or register |
| Superseded | Replaced by successor Definition ID/version |
| Archived | Historical retention only |

### 6.2 Lifecycle Rules

1. A definition in Draft shall not be treated as controlling.  
2. Approved/Published package text that includes definitions still depends on Human Engineer package approvals under WF-001.  
3. Supersession shall record successor Definition ID/version.  
4. AI may recommend transitions; AI may not self-approve Approved or Published.

---

## 7. Definition Classification

Every definition record shall declare a primary class:

| Class | Code | Meaning |
|---|---|---|
| Existing Controlling Definition | `DEF-EXIST` | Already established in cited Kansas authority; referenced, not rewritten |
| Reused Existing Definition | `DEF-REUSE` | Package adopts existing controlling definition by citation |
| Adapted Existing Definition | `DEF-ADAPT` | Uses existing definition with scoped modification; requires conflict analysis |
| New Proposed Definition | `DEF-NEW` | No suitable existing controlling definition identified |
| Revised Definition | `DEF-REV` | Changes an existing definitional locus through authorized revision engineering |
| Fiscal/Technical Definition | `DEF-FISC` | Specialized term for fiscal-note or technical engineering use; still scope-bound |
| Temporary Working Definition | `DEF-TEMP` | Draft-only working sense; cannot reach Approved without reclassification |

### 7.1 Classification Rules

1. Prefer `DEF-EXIST` / `DEF-REUSE` over `DEF-NEW` when a suitable controlling definition exists.  
2. `DEF-ADAPT` and `DEF-REV` require Existing-vs-New analysis and conflict detection.  
3. `DEF-TEMP` is nonconforming in Approved/Published packages.  
4. Misclassification to avoid reuse analysis is nonconforming.

---

## 8. Definition Versioning

### 8.1 Versioning Mandate

Definition changes shall preserve version history.

### 8.2 Semantic Versioning

| Change Class | Version Impact | Meaning |
|---|---|---|
| MAJOR | Meaning change, scope expansion/narrowing that alters applicability, or split/merge | Incompatible semantic change |
| MINOR | Additive aliases, compatible cross-reference expansions, non-meaning clarifications expressly labeled as nonsubstantive pending review | Compatible expansion |
| PATCH | Typos, formatting, citation cleanup with no semantic change | Non-semantic cleanup |

### 8.3 Version History Requirements

Each definition record shall retain:

1. Prior version number  
2. Change summary  
3. Change class (MAJOR/MINOR/PATCH)  
4. Authorizing artifact (CWC-CE/CEP as applicable)  
5. Supersedes / superseded-by links  
6. Conflict outcomes associated with the change  

### 8.4 Version Rules

1. Silent overwrites of prior definition text are nonconforming.  
2. Meaning changes require MAJOR version increment and review gates.  
3. Package-local copies that diverge from a register entry are either new scoped definitions or nonconforming forks.

---

## 9. Definition Reuse Rules

### 9.1 Reuse Mandate

Existing definitions shall be reused when appropriate rather than duplicated.

### 9.2 Reuse Decision Sequence

1. Search parent package definition sections  
2. Search Kansas statutory/constitutional definitional loci relevant to the chapter/act/article  
3. Search Legislative Manager definition register entries for Kansas  
4. If suitable controlling definition exists, cite/reuse it  
5. If unsuitable, document why reuse fails before proposing new/adapted text  

### 9.3 Reuse Outcomes

| Outcome | Required Action |
|---|---|
| Exact reuse | Cite existing locus / Definition ID; do not restate unless restatement is expressly authorized and identical |
| Scoped reuse | Cite existing definition and declare identical adoption within package scope |
| Adaptation required | Create `DEF-ADAPT` with explicit delta from existing definition |
| New definition required | Create `DEF-NEW` with documented reuse failure basis |
| Unresolved | Mark `[EXISTING DEFINITION SEARCH UNRESOLVED]` and escalate |

### 9.4 Anti-Duplication Rules

1. Copy-paste of an existing definition under a new ID without citation is nonconforming.  
2. Near-duplicate definitions with no scoped distinction are conflict candidates.  
3. Restatement for readability shall be labeled restatement and yield to the cited authoritative locus if divergence appears.

---

## 10. Cross-Reference Rules

### 10.1 Cross-Reference Map Mandate

Every definition record shall maintain cross-references to:

1. Authoritative source locus (for existing definitions)  
2. Parent package sections using the term  
3. Related definitions (parent/child/see-also)  
4. Amendment/revision actions affecting the definition  
5. Fiscal-note term usage when linked to KLS-004 packages  
6. AGCL/NBBF/CDT references when applicable  

### 10.2 Cross-Reference Integrity States

| State | Meaning |
|---|---|
| Valid | Reference resolves to intended locus/record |
| Updated | Reference changed to preserve integrity after revision/renumber |
| Broken-Risk | Likely invalid if proposed changes are adopted |
| Orphaned | Points to repealed/removed definitional authority |
| Unresolved | Cannot verify; flagged for review |

### 10.3 Cross-Reference Rules

1. Terms used operatively in a package should point to Definition IDs or exact cited loci.  
2. Broken-risk and orphaned references require response actions or documented deferral.  
3. Renumbering of definitional statutes shall preserve old→new aliases under KLS-003 principles.  
4. Cross-references do not transfer ownership of foreign controls or documents.

---

## 11. Conflict Detection

### 11.1 Conflict Mandate

Conflicting definitions shall be identified and escalated.

### 11.2 Conflict Types

| Type | Meaning |
|---|---|
| Dual-authority conflict | Two authoritative definitions claim the same term within overlapping scope |
| Adaptation conflict | Proposed adaptation contradicts cited existing definition without express revision path |
| Package fork conflict | Package-local definition diverges from register/controlling locus while claiming identity |
| Alias collision | Distinct Definition IDs share aliases in overlapping scope |
| Hierarchical conflict | Narrower/local definition unlawfully overrides broader controlling definition without authorization |
| Control conflict | Proposed definition conflicts with applicable AGCL/NBBF constraints |

### 11.3 Conflict Record Fields

| Field | Requirement |
|---|---|
| Conflict ID | Stable ID (example: `DC-NNN`) |
| Term / Definition IDs | Involved records |
| Conflict type | From Section 11.2 |
| Scope overlap | Description of overlapping applicability |
| Evidence | Citations/extracts demonstrating conflict |
| Proposed resolution options | Engineering options only; no silent choice |
| Status | Open / Escalated / Resolved / Deferred |
| Human Engineer decision | Required for Resolved when material |

### 11.4 Conflict Rules

1. Do not silently pick a winner among conflicting definitions.  
2. Open material conflicts block Approved/Published for affected packages unless Human Engineer expressly accepts residual conflict posture.  
3. “Harmonizing” edits that change legal meaning are revisions and must be engineered as such.  
4. Absence of search for existing definitions is itself an engineering defect when conflicts later appear.

---

## 12. Existing-vs-New Definition Rules

### 12.1 Distinction Mandate

Packages shall distinguish existing controlling definitions from newly proposed definitions.

### 12.2 Required Analysis for Existing Definitions

| Field | Requirement |
|---|---|
| Existing citation | Exact constitutional/statutory locus |
| Current text source | Cited authority |
| Current text extract | Quoted or precisely referenced |
| Scope of existing definition | As stated or inferred with uncertainty flags |
| Suitability determination | Reuse / adapt / revise / unsuitable |

### 12.3 Required Analysis for New Definitions

| Field | Requirement |
|---|---|
| Reuse failure basis | Why existing definitions are insufficient |
| Proposed text | Exact proposed definition |
| Scope declaration | Where the new definition controls |
| Conflict search result | No conflict / conflicts listed / unresolved |
| Temporary vs durable intent | `DEF-TEMP` not permitted at Approved |

### 12.4 Existing-vs-New Rules

1. Do not invent existing definitional text.  
2. Do not present new definitions as already enacted.  
3. Revising an existing definition requires revision engineering under KLS-003 when statutory, or KLS-002 when constitutional.  
4. Ambiguous blended text that does not show existing versus proposed definitional language is nonconforming.

---

## 13. Constitutional Compatibility

### 13.1 Requirement

Definition engineering shall assess constitutional compatibility when:

1. Definitions appear in or affect `KS-CONST` packages  
2. Statutory definitions implicate constitutional terms or constraints  
3. Proposed definitions would functionally alter constitutional meaning without CAP process  

### 13.2 Compatibility Rules

1. Statutory definitions shall not be used to disguise constitutional amendment.  
2. Constitutional definitional changes route to KLS-002.  
3. If compatibility cannot be assessed, mark `[CONSTITUTIONAL REVIEW REQUIRED]` and escalate.  
4. Do not fabricate constitutional meaning.

---

## 14. AGCL Integration

| Topic | Rule |
|---|---|
| Role | AGCL provides structural control framework relevant to liberty, authority limits, transparency, and related controls |
| Requirement | Assess AGCL applicability for definition records that implicate AGCL-relevant concepts |
| When required to cite | When definition scope implicates AGCL-applicable controls |
| Ownership | AGCL remains owned by AGCL-Control-Documents |
| Method | Reference control identifiers; do not fork AGCL definitions into shadow controls |
| Conflict | Report conflicts between proposed definitions and applicable AGCL controls |

References do not imply ownership.

---

## 15. NBBF Integration

| Topic | Rule |
|---|---|
| Role | NBBF provides node-based budget and fiscal authority boundary controls |
| Requirement | Assess whether definitions implicate fiscal/node budget concepts |
| When required to cite | When defining fiscal terms, node terms, fund terms, or budget-authority terms used in legislative/fiscal packages |
| Ownership | NBBF remains owned by NBBF-Control-Documents |
| Method | Prefer referencing NBBF terminology where applicable rather than creating conflicting manager-local fiscal definitions |
| Coordination | When Budget Manager is Active, escalate fiscal-definition conflicts through defined interfaces |
| Conflict | Report conflicts; do not invent NBBF-compatible meaning |

If NBBF applicability is uncertain for a fiscal definition, record `[NBBF APPLICABILITY UNRESOLVED]` and escalate.

---

## 16. CDT Metadata

Every Kansas definition record shall include CDT-ready metadata sufficient for future twin modeling.

### 16.1 Minimum CDT Metadata

| Field | Requirement |
|---|---|
| Jurisdiction | `Kansas` |
| Definition ID / Version | Stable identifiers |
| Term / normalized key / aliases | Explicit |
| Scope type and locus | Explicit applicability boundary |
| Layer ID | `KS-CONST` / `KS-STAT` / authorized |
| Classification | `DEF-*` class |
| Existing-source edge | Citation link when existing |
| Parent artifact edge | Package introducing/using the definition |
| Reuse edges | Links to reused/adapted source definitions |
| Conflict edges | Links to open/resolved `DC-NNN` records |
| Cross-reference edges | Usage and related-definition links |
| Control links | AGCL/NBBF/CDT as applicable |
| Lifecycle state | Current state |
| Supersession link | Prior/successor IDs/versions |

### 16.2 CDT / UNBKE Readiness Rules

1. Identifiers shall be stable and unique.  
2. Scope and reuse/conflict relationships shall be explicit, not only narrative.  
3. Definition records shall remain operable without CDT runtime or UNBKE.  
4. Future UNBKE indexing shall be additive; do not hard-depend on UNBKE.  
5. Do not invent relationship edges to appear complete.

---

## 17. Traceability Requirements

### 17.1 Required Trace Elements

| Trace Element | Requirement |
|---|---|
| Definition ID, term, scope, version | Required |
| Classification | Required |
| Existing definition citation or reuse-failure basis | Required for non-temporary records advancing to review |
| Parent artifact linkage | Required when package-introduced |
| Cross-reference map | Required |
| Conflict detection result | Required |
| Version history | Required after first change |
| Constitutional compatibility posture | Required when implicated; otherwise explicit non-applicability basis |
| Governing CWC-CE | Required for production work |
| Governing ECR / CEP / CER | Conditional per WF-001 |
| Standards applied | At minimum STD-008 and KLS-005; parent KLS standards as applicable |
| Control references | AGCL/NBBF/CDT as applicable |
| Review/publication status | Required for Approved/Published path |

### 17.2 Traceability Rule

A definition lacking identity, scope, authoritative-within-scope posture, conflict posture, and version/lifecycle state is incomplete and shall not enter Approved status.

---

## 18. Engineering Review Requirements

### 18.1 Review Gates

Definition records and definition-bearing packages follow applicable STD-008 review states.

| Review | Focus |
|---|---|
| Engineering Review | Identity uniqueness, reuse analysis, existing-vs-new clarity, conflict detection, cross-references, versioning, CDT metadata |
| Legal Review | Compatibility with cited legal definitional authority and parent artifact constraints |
| Public Review | Only when required by authorizing work or Human Engineer direction |

### 18.2 Engineering Review Minimum Checks

1. One authoritative definition within declared scope  
2. Existing definitions searched and reused when appropriate  
3. Conflicts identified and escalated (none silently resolved)  
4. Existing vs new definition language distinguished  
5. Version history preserved for changes  
6. Cross-references valid or expressly handled  
7. Constitutional routing correct (KLS-002 when constitutional)  
8. AGCL/NBBF/CDT applicability assessed  
9. No fabricated existing definitions  
10. Publication readiness accurately stated  

### 18.3 Review Outcomes

`Pass` / `Partial` / `Fail` / `Not performed`  
Unperformed review shall not be reported as complete.  
Open material conflicts default to Fail or Partial.

---

## 19. Publication Requirements

1. Definition records included in publication packages shall be structurally publication-ready before approval for publication.  
2. Publication-ready means:
   - identity/scope/version complete  
   - authoritative-within-scope rule satisfied  
   - reuse/conflict posture complete or expressly Human-Engineer-deferred  
   - existing-vs-new distinction clear  
   - version history intact  
   - no fabricated authorities  
3. Legislative Manager may prepare publication packages; Legislative Manager may not self-publish.  
4. Only Human Engineer-approved artifacts enter public channels under WF-001.  
5. Draft/in-review/failed/partial definition sets are not published unless expressly authorized as such.  
6. Publication of engineered definitions does not itself enact law.

---

## 20. Quality Checklist

Before presenting Kansas definition engineering work for Human Engineer review or approval, verify:

| # | Check | Required |
|---|---|---|
| 1 | Authorizing CWC-CE / CEP identified for production work | Yes |
| 2 | Definition ID, term, normalized key, scope, version present | Yes |
| 3 | One authoritative definition within declared scope | Yes |
| 4 | Existing definitions searched; reused when appropriate | Yes |
| 5 | Reuse failure documented before new definition (when new) | Yes |
| 6 | Existing vs new definition distinguished | Yes |
| 7 | Conflicts identified and escalated (not silently resolved) | Yes |
| 8 | Cross-references valid, updated, or expressly handled | Yes |
| 9 | Version history preserved for changes | Yes |
| 10 | Lifecycle state correct; no unauthorized Approved/Published | Yes |
| 11 | Constitutional compatibility assessed or correctly routed | Yes |
| 12 | AGCL applicability assessed; cited when required | Yes |
| 13 | NBBF applicability assessed; cited when required | Yes |
| 14 | CDT metadata present | Yes |
| 15 | Traceability block complete | Yes |
| 16 | No fabricated existing definitions or citations | Yes |
| 17 | Publication readiness accurately declared | Yes |
| 18 | Supports future CDT/UNBKE mapping without hard dependency | Yes |
| 19 | No specific bill definitions drafted under this CWC unless separately authorized | Yes for this standard’s own deliverable posture |

Any failed required check blocks a claim of completion.

---

## 21. Conformance

1. Conformance to KLS-005 is mandatory for Kansas legislative definition engineering performed by Legislative Manager after this standard’s Effective Date, subject to Human Engineer activation/acceptance of this Draft if required by Office practice.  
2. Nonconformance is an engineering defect and shall be corrected before Approved/Published states of affected packages/records.  
3. Exceptions require explicit Human Engineer approval and shall record reason, scope, duration/terminal condition, approver, and date.  
4. An exception never authorizes fabricated definitions, hidden conflicts, false verification, or undisclosed scope expansion.  
5. Conformance does not require UNBKE.  
6. Parent artifact standards remain independently mandatory.  
7. Conflicting definitions left unresolved without escalation are nonconformance.  
8. Reserved Office standards remain superior or complementary when Active; conflicts escalate.

---

## 22. Version History

| Version | Date | Summary |
|---|---|---|
| 1.0.0 | 2026-08-08 | Initial Kansas Legislative Definitions Engineering Standard establishing definition identity, lifecycle, classification, reuse, conflict detection, versioning, and CDT/UNBKE readiness rules. |
