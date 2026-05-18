# Roadmap

## Current Phase

Studio OS foundation setup is complete.

Runtime MVP implementation is active in the separate runtime repository.

Current runtime phase:

```text
Phase 9 — Validation Gate and Build Fixes
Validation result pending
Deployment locked
```

No product project is active.

No paid hosting resources have been created.

## Status Values

- NOT_STARTED
- IN_PROGRESS
- PASSED
- FAILED
- LOCKED

## Milestone 0 — Foundation Standard

Status: PASSED

Goal:

Create the clean standard for the studio before implementation.

Result:

Foundation document set is complete and clean.

## Milestone 1 — Data Model Review

Status: PASSED

Goal:

Review and approve the MVP database model for Studio OS.

Result:

MVP data model is accepted for runtime implementation.

## Milestone 2 — Workflow Review

Status: PASSED

Goal:

Review and approve the first working studio loop.

Result:

The first Studio OS operating workflow is accepted for runtime implementation.

## Milestone 3 — Hosting Decision

Status: PASSED

Goal:

Choose the permanent runtime target.

Result:

Render Managed Platform is approved as the first Studio OS runtime hosting direction.

Pricing and selected tiers must be rechecked before paid resources are created.

## Milestone 4 — Implementation Repository Decision

Status: PASSED

Goal:

Decide where the first Studio OS implementation will live.

Result:

Separate runtime repository direction is approved.

Approved runtime repository:

`ilkkanml/nexora-studio-os-runtime`

## Milestone 5 — Runtime MVP Planning

Status: PASSED

Goal:

Plan the first working Studio OS runtime after hosting and repository decisions are approved.

Result:

Runtime MVP plan is owner-approved.

## Milestone 6 — Runtime Repository Setup

Status: PASSED

Goal:

Create the approved runtime repository and prepare the basic project structure.

Result:

Runtime repository exists and contains no product project code.

Repository:

`ilkkanml/nexora-studio-os-runtime`

## Milestone 7 — Runtime Foundation Implementation

Status: PASSED

Goal:

Implement the first runtime foundation.

Result:

Runtime repository includes:

- Next.js owner-only shell
- Prisma schema foundation
- Director workflow classifier
- permanent role registry
- controlled role-call foundation
- memory and decision acceptance foundation
- model routing foundation
- Render preparation template

## Milestone 8 — Safety Hardening

Status: PASSED

Goal:

Add safety hardening before deployment.

Result:

Runtime includes:

- secret redaction helper
- owner-only production middleware gate
- task approval and model route approval split
- unconfigured model route blocking
- workflow simulation foundation
- validation checklist foundation

## Milestone 9 — Validation Gate and Lean Workflow

Status: IN_PROGRESS

Goal:

Validate runtime readiness before deployment and prevent unnecessary workflow bloat.

Current runtime work includes:

- validation gate runner
- static preflight checks
- validation report output
- GitHub Actions validation artifact
- lean department policy
- Director-first classifier behavior
- workflow simulations for Director-only and specialist-heavy paths
- README and checklist synchronization

Completion rules:

- validation command passes
- static preflight passes
- Prisma validate passes
- Prisma generate passes
- TypeScript check passes
- Next build passes
- workflow simulation passes
- no deployment has started before validation pass

## Milestone 10 — Deployment Preparation

Status: LOCKED

Goal:

Prepare controlled Render deployment after validation passes.

Locked until:

- Milestone 9 passes
- owner approves deployment preparation
- current pricing and tier selection are rechecked
- environment variable plan is confirmed

## Milestone 11 — First Private Runtime Deployment

Status: LOCKED

Goal:

Deploy owner-only private runtime.

Locked until:

- Milestone 10 passes
- database migration plan is approved
- owner access token plan is confirmed
- health check plan is confirmed

## Final Rule

Do not start product project work until the Studio OS runtime proves the Director workflow, database memory, role call, decision, validation, and cost logging loop.