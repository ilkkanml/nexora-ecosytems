# NEXORA Studio OS Roadmap

## Status Values

- NOT_STARTED
- IN_PROGRESS
- PARTIAL
- WAITING_APPROVAL
- PASSED
- FAILED
- LOCKED

## Milestone 0 — Studio Constitution Lock

Status: IN_PROGRESS

Goal:

Lock the purpose, operating model, minimum department structure, owner approval rules, and token economy principles.

Completion rules:

- Studio constitution exists
- Department system exists
- Token economy rule exists
- Owner-facing Director model is approved
- No implementation repo is modified during this milestone

## Milestone 1 — Studio Database Foundation Plan

Status: NOT_STARTED

Goal:

Define the database models required to store projects, tasks, department messages, decisions, milestones, approvals, memory, checkpoints, and cost logs.

Completion rules:

- MVP database entities are listed
- Entity relationships are defined
- Sensitive data rules are defined
- Migration target repo is identified

## Milestone 2 — Studio API Foundation Plan

Status: NOT_STARTED

Goal:

Define internal API modules for Studio OS inside TV_Project_Platform.

Scope:

- projects
- departments
- tasks
- conversations
- messages
- decisions
- milestones
- approvals
- memory
- cost logs
- context packages

Completion rules:

- Endpoint groups are defined
- Authorization rules are defined
- Owner-only/internal access is enforced conceptually

## Milestone 3 — Studio Web Dashboard Plan

Status: NOT_STARTED

Goal:

Design the first internal Studio OS dashboard.

Required views:

- Projects
- Active Project
- Tasks
- Milestones
- Decisions
- Department Runs
- Memory
- Cost Usage
- Approvals

Completion rules:

- Dashboard MVP scope is clear
- No customer-facing route is mixed with internal studio routes

## Milestone 4 — Single Department Call MVP

Status: NOT_STARTED

Goal:

Build the first functional AI department call flow.

Flow:

Owner request → Studio Director → one department → response saved to database → Director summary → owner approval if needed.

Completion rules:

- One department call can be stored
- Message history is stored in owner database
- Cost/token log is stored
- No uncontrolled department loops

## Milestone 5 — Controlled Roundtable MVP

Status: NOT_STARTED

Goal:

Allow multiple departments to respond under Director control.

Completion rules:

- Roundtable has max department count
- Roundtable has max turn count
- Director final summary is required
- Results are stored
- Owner sees only final compact result unless details are requested

## Milestone 6 — Project Onboarding Engine

Status: NOT_STARTED

Goal:

Create a flow for starting web, app, game, and platform projects inside the studio.

The system should generate:

- project constitution
- MVP scope
- recommended departments
- milestone list
- first task list
- GitHub repo links

Completion rules:

- New project can be created
- Project type affects recommended departments
- First milestone can be created from template

## Milestone 7 — GitHub Handoff Plan

Status: NOT_STARTED

Goal:

Define how approved studio tasks become GitHub issues, branches, PR plans, or implementation handoffs.

Completion rules:

- AI cannot silently deploy or commit
- Owner approval is required
- Target repo and affected files must be explicit
- Rollback/checkpoint rule exists

## Milestone 8 — Move Existing Projects Into Studio

Status: NOT_STARTED

Goal:

Onboard existing projects:

- TV_Project
- TV_Project_Platform
- future game projects
- future web/app projects

Completion rules:

- Each project has a constitution
- Each project has milestones
- Each project has active tasks
- Each project has decision log entries
