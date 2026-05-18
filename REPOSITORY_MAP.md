# Repository Map

## Foundation Repository

`ilkkanml/nexora-ecosytems`

Purpose:

Clean planning and standard repository for NEXORA Studio OS.

Current status:

Foundation, standards, decisions, roadmap, and operating rules.

This repository defines how the studio should work.

It should stay clean and mostly documentation-focused.

It is not the runtime app.

## Runtime Implementation Repository

Active runtime repository:

`ilkkanml/nexora-studio-os-runtime`

Role:

- actual Studio OS application code
- frontend shell
- backend foundation
- Prisma database schema
- validation gate
- owner-only access gate
- OpenAI integration foundation
- model routing foundation
- memory and decision acceptance foundation
- Render deployment preparation

Current runtime status:

```text
Phase 9 — Validation Gate and Build Fixes
Runtime foundation implemented.
Safety hardening implemented.
Lean department policy implemented.
Validation gate reporting implemented.
Validation result pending.
Deployment locked.
```

This repository will run the studio after validation and controlled deployment preparation.

## Product Repositories

No product repository is active during the Studio OS runtime foundation phase.

Future projects may be added only through `PROJECT_INTAKE.md` rules.

Product repositories must not be mixed into the Studio OS runtime repository unless explicitly approved later.

## Repository Roles

### Foundation Repository Role

- studio constitution
- standards
- roadmap
- decision log
- data model planning
- workflow planning
- hosting direction
- project intake rules
- implementation boundary

### Runtime Repository Role

- owner-only runtime MVP
- Studio Director workflow implementation
- database schema implementation
- validation and safety gates
- deployment preparation

### Product Repository Role

Future only.

Product repositories will contain actual product/game/app code after the Studio OS runtime proves the core loop.

## Implementation Repository Decision

Approved direction:

Use a separate runtime implementation repository.

Reason:

- keeps standards separate from runtime code
- prevents planning documents from mixing with application files
- allows clean deployment setup
- reduces scope confusion
- keeps future product projects independent
- allows the foundation repository to remain stable while runtime evolves

Approved repository:

`ilkkanml/nexora-studio-os-runtime`

Status:

- repository exists
- runtime implementation has started
- Phase 9 validation gate is active
- deployment is locked until validation passes

## Alternative Options

### Use Foundation Repository for Runtime

Rejected for first MVP.

Risk:

- mixes foundation documents with runtime code
- increases confusion
- weakens repository boundary
- makes future cleanup harder

### Monorepo

Deferred.

Risk:

- useful later, but too heavy for first MVP
- can encourage premature structure complexity

### Existing Product Repository

Deferred.

Risk:

- would mix Studio OS runtime with product/platform work too early
- creates authority drift before the studio itself is stable

## Approval Rule

Creating paid resources, deploying runtime, or activating product repositories requires owner approval.

## Final Rule

This repository defines the studio.

The runtime repository runs the studio after validation.

Product repositories come later.