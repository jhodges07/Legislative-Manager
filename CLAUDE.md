# Legislative Manager — AI Assistant Rules

Read before any work in this repository. These rules apply to every AI assistant
(Claude, ChatGPT, Cursor, Copilot or other) used by the Human Engineer or by a contributor.

The binding operating manual is `prompts/LegislativeManager.md` (PROMPT-MGR-LEG-001).
If anything here conflicts with it, the manual wins. Office architecture, policy and
standards (ARCH, POL, STD, WF) live in the Constitutional-Engineering repository.

## Who decides
- James A. Hodges is the Human Engineer. Only he approves, merges, issues work cards
  (CWC-CE) or advances any lifecycle state (STD-008).
- AI may draft and review. AI never approves, and silence is never approval.
- Contributors propose; the Human Engineer decides (SPEC-003 §18).

## Before any work
1. Identify which project the task belongs to (`projects/PRJ-NNN-*`) and read its SPEC.
2. Check the SPEC's gates. If the required CWC-CE is not issued, stop and say so.
3. Read the KLS standards the task touches (`kansas-standards/`).

## Engineer before draft
- No operative bill, amendment, joint-rule or constitutional text may be written until
  the project's SPEC says drafting is authorized (PRJ-002: SPEC-003 §7.2 and §13, gates HG-0 and HG-1).
- Until then, allowed work is research, review comments, authority and dependency maps,
  definition scaffolds and questions — clearly labeled as non-operative.
- Concept or model language from outside this repository (Human Engineer working documents,
  the Runtime-Republic Training course *The One-Hour Rule*) is reference input only.
  Never copy it into a package before drafting is authorized.

## Sources and authority
- Cite the source for every legal or factual claim: statute (K.S.A.), constitutional article,
  legislative rule, Attorney General opinion or court case, with a link.
- Never invent authority, citations, fiscal numbers or definitions. Unknowns are marked as
  unknown and escalated to the Human Engineer.
- AGCL, NBBF and CDT are referenced, never rewritten. Their own repositories own their rules.

## Public-record caution
- Anything written here is public. A contributor who holds public office must not use this
  repository to deliberate with a majority of their own public body (Kansas Open Meetings Act;
  SPEC-003 §18.3).

## Changes
- Work on a branch named `proposal/<short-name>` and open a pull request; never push to `main`.
- One logical change per commit, with a plain message saying what changed and why.
- Use the issue templates for review comments and proposed changes.
