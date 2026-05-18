# Repository Map

## Current Repository

`ilkkanml/nexora-ecosytems`

Purpose:

Clean planning and standard repository for NEXORA Studio OS.

Current status:

Foundation, standards, decisions, roadmap, and operating rules only.

No runtime implementation yet.

## Repository Roles

### Foundation Repository

Current repository:

`ilkkanml/nexora-ecosytems`

Role:

- studio constitution
- standards
- roadmap
- decision log
- data model planning
- workflow planning
- hosting direction
- project intake rules

This repository defines how the studio should work.

It should stay clean and mostly documentation-focused.

### Runtime Implementation Repository

Recommended repository:

`nexora-studio-os-runtime`

Role:

- actual Studio OS application code
- frontend
- backend
- database schema
- migrations
- API routes
- authentication if needed
- OpenAI integration
- GitHub integration
- Render deployment configuration

This repository will run the studio.

## Product Repositories

No product repository is active during the Studio OS foundation phase.

Future projects may be added only through `PROJECT_INTAKE.md` rules.

Product repositories must not be mixed into the Studio OS runtime repository unless explicitly approved later.

## Implementation Repository Decision

Recommended direction:

Create a separate runtime implementation repository.

Reason:

- keeps standards separate from runtime code
- prevents planning documents from mixing with application files
- allows clean deployment setup
- reduces scope confusion
- keeps future product projects independent
- allows the foundation repository to remain stable while runtime evolves

Recommended name:

`nexora-studio-os-runtime`

Status:

- recommended
- pending owner approval
- runtime repo not created yet
- runtime implementation not started yet

## Alternative Options

### Use Current Repository for Runtime

Not recommended.

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

### Existing Platform Repository

Deferred.

Risk:

- would mix Studio OS runtime with product/platform work too early
- creates authority drift before the studio itself is stable

## Approval Rule

Creating or selecting the implementation repository requires owner approval.

No runtime implementation should start until the repository decision is approved.

## Final Rule

This repository defines the studio.

A separate runtime repository should run the studio after owner approval.