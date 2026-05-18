# Roadmap

## Current Phase

Studio OS foundation setup is complete.

Runtime MVP preparation is active.

No product project is active.

Runtime implementation has not started yet.

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

Required documents:

- README.md
- STUDIO_STANDARD.md
- OPENAI_USAGE_STANDARD.md
- DATA_STANDARD.md
- DATA_MODEL.md
- WORKFLOW.md
- HOSTING.md
- PROJECT_INTAKE.md
- REPOSITORY_MAP.md
- ROADMAP.md
- DECISION_LOG.md

Completion rules:

- owner-facing Director model is defined
- minimal roles are defined
- truth standard is defined
- token economy is defined
- data ownership is defined
- data model is defined
- workflow is defined
- hosting requirements are defined
- project intake rule is defined
- approval rule is defined
- no product project is active

Result:

Foundation document set is complete and clean.

## Milestone 1 — Data Model Review

Status: PASSED

Goal:

Review and approve the MVP database model for Studio OS.

Completion rules:

- all required entities are approved
- entity relationships are clear
- sensitive data rules are approved
- PostgreSQL source-of-truth rule is approved
- Redis temporary-use rule is approved

Result:

MVP data model is accepted for planning. Runtime schema implementation has not started yet.

## Milestone 2 — Workflow Review

Status: PASSED

Goal:

Review and approve the first working studio loop.

Completion rules:

- owner to Director flow is approved
- role call policy is approved
- controlled review policy is approved
- approval gate is approved
- failure rule is approved

Result:

The first Studio OS operating workflow is accepted for planning. Runtime implementation has not started yet.

## Milestone 3 — Hosting Decision

Status: PASSED

Goal:

Choose the permanent runtime target.

Requirements:

- stable Node.js runtime
- PostgreSQL
- Redis or queue support
- GitHub deployment
- environment variables
- logs
- backups
- custom domain support
- secure secret management
- estimated monthly cost

Result:

Render Managed Platform is approved as the first Studio OS runtime hosting direction.

Implementation has not started yet.

Pricing and selected tiers must be rechecked before paid resources are created.

## Milestone 4 — Implementation Repository Decision

Status: PASSED

Goal:

Decide where the first Studio OS implementation will live.

Options:

- dedicated new repository
- existing platform repository later
- monorepo structure

Completion rules:

- implementation repository is selected
- stack is selected
- first implementation milestone is created
- no product project is mixed into the foundation implementation

Result:

Separate runtime repository direction is approved.

Approved runtime repository name:

`nexora-studio-os-runtime`

The runtime repository has not been created yet.

Runtime implementation has not started yet.

## Milestone 5 — Runtime MVP Planning

Status: PASSED

Goal:

Plan the first working Studio OS runtime after hosting and repository decisions are approved.

Initial runtime scope:

- project creation
- role list
- task creation
- single role call
- message storage
- decision storage
- memory storage
- cost logging

Result:

Runtime MVP plan is owner-approved.

Runtime implementation has not started yet.

Runtime repository still needs to be created.

## Milestone 6 — Runtime Repository Setup

Status: IN_PROGRESS

Goal:

Create the approved runtime repository and prepare the basic project structure.

Approved repository name:

`nexora-studio-os-runtime`

Completion rules:

- runtime repository exists
- repository contains no product project code
- basic README exists
- environment variable template exists without secrets
- initial implementation notes exist
- no paid hosting resources are created yet

## Final Rule

Do not start product project work until the Studio OS runtime proves the Director workflow, database memory, role call, decision, and cost logging loop.