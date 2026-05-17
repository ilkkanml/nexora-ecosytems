# Roadmap

## Current Phase

Studio OS foundation standard.

No product project is active.

## Status Values

- NOT_STARTED
- IN_PROGRESS
- PASSED
- FAILED
- LOCKED

## Milestone 0 — Foundation Standard

Status: IN_PROGRESS

Goal:

Create the clean standard for the studio before implementation.

Required documents:

- README.md
- STUDIO_STANDARD.md
- OPENAI_USAGE_STANDARD.md
- DATA_STANDARD.md
- ROADMAP.md
- DECISION_LOG.md

Completion rules:

- owner-facing Director model is defined
- minimal roles are defined
- truth standard is defined
- token economy is defined
- data ownership is defined
- approval rule is defined
- no product project is active

## Milestone 1 — Data Model

Status: NOT_STARTED

Goal:

Define the MVP database schema for Studio OS.

Required entities:

- Project
- Role
- Task
- Conversation
- Message
- Decision
- Milestone
- Approval
- Memory
- CostLog
- ContextPackage

## Milestone 2 — Workflow Model

Status: NOT_STARTED

Goal:

Define the first working studio loop.

Flow:

Owner request → Studio Director → role selection → minimal context → role output → Director summary → storage → owner approval if needed.

## Milestone 3 — Hosting Decision

Status: NOT_STARTED

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

## Milestone 4 — Implementation Repository Decision

Status: NOT_STARTED

Goal:

Decide where the first Studio OS implementation will live.

Options:

- dedicated new repository
- existing platform repository later
- monorepo structure

## Final Rule

Do not start implementation before the standard and hosting direction are approved.