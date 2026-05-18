# Director Bootstrap Protocol

## Purpose

This document defines how the Studio Director should recover the foundation state after a new chat, new session, or long pause.

The goal is to avoid context loss and avoid stale assumptions.

## Bootstrap Order

When starting work from the foundation repository, read in this order:

1. `CURRENT_STATUS.md`
2. `README.md`
3. `ROADMAP.md`
4. `DECISION_LOG.md`
5. `REPOSITORY_MAP.md`
6. `RUNTIME_MVP_PLAN.md`
7. runtime repository `CURRENT_STATUS.md`

Runtime repository:

```text
ilkkanml/nexora-studio-os-runtime
```

## First Question To Answer Internally

Before doing any work, the Director should know:

```text
What repository am I in?
What phase is active?
What is locked?
What evidence is missing?
What should not be started yet?
```

## Current Expected Answers

```text
Foundation status: approved and synced
Runtime phase: Phase 9 — Validation Gate and Build Fixes
Next gate: runtime validation evidence
Deployment: locked
Product projects: locked
Paid resources: none
```

## Foundation vs Runtime Rule

Foundation repository defines:

- rules
- standards
- roadmap
- decision log
- repository boundaries

Runtime repository implements:

- owner-only app shell
- database schema
- Director workflow
- validation gate
- model routing
- deployment preparation files

Do not mix foundation documents with runtime code.

Do not mix product project code into runtime or foundation.

## Director-First Rule

Default to Director-only for:

- status checks
- recap
- record review
- simple planning
- next-step explanation

Use a specialist only when the task is heavy, risky, technical, or quality-sensitive.

## Do Not Guess Rule

If runtime validation has not been proven, do not say validation passed.

If deployment has not happened, do not say deployed.

If product project activation is locked, do not start product work.

If a paid resource has not been created, do not assume it exists.

## Current Main Runtime Command

```bash
npm install
npm run validate:local
```

## Work Selection Rule

If validation is pending, prioritize:

1. validation evidence
2. first failed validation step
3. smallest root-cause fix
4. re-run validation

Do not add new product features while validation is pending.

## Final Rule

Start from `CURRENT_STATUS.md`.

Trust evidence over memory.

Foundation defines the studio.

Runtime proves the studio.

Product projects come later.