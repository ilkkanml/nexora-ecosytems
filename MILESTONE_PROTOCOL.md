# Milestone Protocol

## Purpose

Milestones prevent scope drift and protect project identity, legal boundaries, security, budget, and completion discipline.

## Rule 1 — One Main Goal

Each milestone must have one main goal.

No milestone should mix unrelated backend, frontend, Android, game, legal, reseller, payment, and deployment work unless explicitly approved by the Studio Director and owner.

## Rule 2 — Completion Criteria Required

A milestone is not complete unless completion rules are verified.

Do not mark work as passed because it is planned.

## Rule 3 — No Silent Scope Expansion

New features must be logged as one of:

- approved now
- scheduled later
- rejected
- needs review

## Rule 4 — Cross-Repo Changes Require Direction Lock

If a change affects more than one repo, it must be documented here before implementation.

## Rule 5 — Legal / Product Gate Required

Every milestone must pass its project-specific boundary test.

For Nexora media player projects:

> Does this preserve Nexora as a legal media player ecosystem?

For Studio OS projects:

> Does this preserve owner approval, minimal departments, token discipline, and controlled execution?

If the answer is no, the milestone fails.

## Rule 6 — Production Safety

No production release without:

- product boundary review
- security review
- build validation
- rollback plan
- version record
- known limitations record
- owner approval

## Rule 7 — Decision Ownership

Important decisions are made by the owner and recorded in `DECISION_LOG.md`.

Implementation should follow approved decisions, not invent product direction silently.

## Rule 8 — Department Use

Do not call departments just to appear busy.

Use the smallest useful expert set.

Default path:

1. Studio Director evaluates.
2. One department answers if enough.
3. Roundtable only if cross-domain risk exists.
4. QA / Security checks if the result touches code, data, auth, legal scope, or deployment.
5. Memory / Documentation records accepted output.

## Rule 9 — Three-Fail Stop

After three failed attempts on the same issue:

- stop blind retries
- record failure
- identify last safe checkpoint
- ask Director for redesign, rollback, or manual inspection

## Final Rule

A milestone should reduce uncertainty and move the project closer to release. If it only creates more documents without enabling action, it must be simplified.