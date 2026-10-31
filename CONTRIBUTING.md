# Contributing to Legislative Manager

Thank you for helping. This repository engineers Kansas legislative packages in the open.
The first group project is **PRJ-002 — Kansas One-Hour Posting Rule**: no bill or amendment
is acted on unless its exact text has been public for at least one hour.

Nothing here is law, and nothing here becomes a draft until the Human Engineer authorizes it.

## How to join (SPEC-003 §18)

1. **Learn the goal.** Read the free Runtime-Republic Training courses
   [*The One-Hour Rule*](https://github.com/jhodges07/Runtime-Republic-Training/tree/main/Courses/one-hour-rule)
   (Lessons 01–05) and
   [*Reading the Draft*](https://github.com/jhodges07/Runtime-Republic-Training/tree/main/Courses/reading-the-draft)
   (Lessons 01–02).
2. **Take the Readiness Check.** Ask the Human Engineer for the form: short quizzes on the
   lessons, plus three written questions in your own words. You can disagree with the draft
   and still pass; the check rewards understanding.
3. **Move up by doing good work.**

| Level | You may | How you get there |
|---|---|---|
| 1. Reviewer | Comment on the model language document | Pass the Readiness Check |
| 2. Contributor | Open issues here | Useful, sourced review comments at Level 1 |
| 3. Proposer | Open pull requests | Useful issues at Level 2 |

This repository is public, so anyone can read it. Issues and pull requests from people
not yet at Level 2 or 3 may be closed without review.

## Ground rules

- **The Human Engineer decides.** Only he merges, approves or moves a project forward.
- **Cite everything.** Every legal or factual claim needs a source: K.S.A. section,
  constitutional article, legislative rule, Attorney General opinion or court case, with a link.
- **No drafting yet.** PRJ-002 is in its engineering phase. Research, questions and review
  are welcome; operative bill text is not, until the Human Engineer authorizes drafting.
- **If you hold public office:** your comments about official business may be public records
  under the Kansas Open Records Act, and discussion among a majority of your public body
  belongs in a noticed meeting, not here (Kansas Open Meetings Act).

## Using an AI assistant

You are welcome to use Claude or another assistant. It follows the same rule you do:
it may draft and review, never approve. To set up Claude:

1. Create a Claude Project (any plan, including Free).
2. Paste the **Contributor** section of
   [`prompts/PRJ-002-Claude-Project-Instructions.md`](prompts/PRJ-002-Claude-Project-Instructions.md)
   into the Project's instructions.
3. Link this repository in the Project's knowledge (GitHub), so your Claude reads the same
   specifications and standards everyone else does.

Your Claude also reads [`CLAUDE.md`](CLAUDE.md) when it works directly in this repository.

## How to propose a change (Level 3)

1. Create a branch named `proposal/<short-name>`.
2. Make one logical change per commit, with a plain message.
3. Open a pull request using the template, and link the issue it answers.
