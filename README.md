# NEXORA Studio OS

Clean foundation repository for building an internal AI-assisted studio.

This repository defines the studio standard, data model, workflow, hosting requirements, repository boundaries, and runtime MVP direction.

It is not a product project.
It is not the runtime app.
It is the foundation and operating standard for the runtime app.

## Current Focus

Keep the Studio OS foundation aligned with the runtime implementation.

The active runtime implementation lives in:

`ilkkanml/nexora-studio-os-runtime`

Current runtime state:

```text
Runtime foundation implemented.
Safety hardening implemented.
Lean department policy implemented.
Validation gate reporting implemented.
Validation result pending.
Deployment locked.
```

No product project is active.

No paid hosting resources should be created until validation passes and deployment preparation is explicitly approved.

## Core Idea

The owner speaks with the Studio Director.

The Studio Director controls intake, classification, context size, summaries, approvals, records, and task flow.

Specialists are used only when the work is heavy, risky, technical, or quality-sensitive.

All permanent memory, decisions, tasks, role outputs, approvals, and cost records belong in the owner-controlled data system.

OpenAI is used as the intelligence engine, not as permanent project memory.

## Lean Workflow Rule

Default workflow:

```text
Director-only first.
Specialists only when the work justifies them.
Records stay with the Director.
No unnecessary departments.
No unnecessary paperwork.
```

## Active Documents

- `STUDIO_STANDARD.md` — studio rules, roles, truth standard, approvals
- `OPENAI_USAGE_STANDARD.md` — OpenAI API usage, token control, model policy
- `DATA_STANDARD.md` — permanent memory and storage rules
- `DATA_MODEL.md` — MVP database entities
- `WORKFLOW.md` — Director-led task flow
- `HOSTING.md` — permanent runtime requirements and approved hosting direction
- `PROJECT_INTAKE.md` — how future projects enter the studio
- `REPOSITORY_MAP.md` — repo purpose and implementation boundary
- `RUNTIME_MVP_PLAN.md` — first runtime MVP scope and exclusions
- `ROADMAP.md` — current milestones
- `DECISION_LOG.md` — approved decisions

## Foundation Rule

Do not start product work until the Studio OS runtime proves the Director workflow, database memory, role call, decision, validation, and cost logging loop.

## Current Status

Foundation setup is approved.

Runtime MVP implementation is active in the separate runtime repository.

Phase 9 validation gate is active.

Deployment remains locked until validation passes.