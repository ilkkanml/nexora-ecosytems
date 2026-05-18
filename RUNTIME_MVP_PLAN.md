# Runtime MVP Plan

## Purpose

This document defines the first working runtime scope for NEXORA Studio OS.

The goal is not to build the full studio.

The goal is to build the smallest useful version that proves the Studio Director workflow, database memory, role calls, validation, and cost logging can work together.

## Current Boundary

Runtime MVP plan is owner-approved.

Runtime implementation is active in:

`ilkkanml/nexora-studio-os-runtime`

Current runtime state:

```text
Phase 9 — Validation Gate and Build Fixes
Runtime foundation implemented.
Safety hardening implemented.
Lean department policy implemented.
Validation gate reporting implemented.
Validation result pending.
Deployment locked.
```

No product project is active.

No paid hosting resources have been created.

## Approved Runtime Direction

Hosting direction:

- Render Managed Platform

Repository direction:

- separate runtime repository
- active repository: `ilkkanml/nexora-studio-os-runtime`

Database direction:

- PostgreSQL is the source of truth
- Redis is temporary operations support only

AI direction:

- OpenAI is the reasoning and generation engine
- Studio OS owns orchestration, memory, approvals, validation, and workflow

## Lean Runtime Workflow

Default behavior:

```text
Director-only first.
Specialists only when the work is heavy, risky, technical, or quality-sensitive.
Records stay with the Director.
No unnecessary departments.
No unnecessary paperwork.
```

Simple status, recap, record review, and simple planning stay with the Studio Director.

Heavy architecture routes to Product Architect.

Code, database, deployment, and security-sensitive work require controlled specialist handling and approval where needed.

## MVP Goal

Create a private owner-controlled Studio OS runtime that can:

1. create and view a project
2. define the permanent studio roles
3. create and track tasks
4. classify owner requests through the Studio Director
5. keep simple work Director-only
6. route heavy or risky work to the right specialist
7. run one controlled role call through the Studio Director workflow
8. store conversation messages
9. store model run records
10. store decisions
11. store compact memory
12. store cost/token usage
13. show a clear next action
14. validate before deployment

## MVP User

The first runtime MVP is owner-only.

No public users.

No customer accounts.

No team accounts.

No multi-tenant organizations.

## MVP Core Screens

### Dashboard

Shows:

- active project
- active milestone
- open tasks
- latest decisions
- latest memory records
- token/cost summary
- validation status

### Projects

Allows:

- create project
- view project
- update project status

### Tasks

Allows:

- create task
- assign required role when justified
- keep simple tasks Director-only
- set task status
- view task history

### Director Console

Allows:

- owner sends request
- Director classifies task
- Director prepares or confirms next action
- role call can be triggered when needed
- approval can be requested when needed

### Conversations

Shows:

- conversation messages
- Director context
- role output
- Director summary

### Memory

Shows:

- accepted compact memories
- reliability level
- project relationship

### Decisions

Shows:

- approved decisions
- rejected decisions
- pending decisions if needed

### Cost Log

Shows:

- model
- model route tier
- reasoning effort
- input tokens
- output tokens
- estimated cost
- related task/conversation/run

## MVP Backend Scope

Required backend capabilities:

- project CRUD
- role seed data
- task CRUD
- conversation creation
- message storage
- run storage
- decision storage
- memory storage
- cost logging
- minimal context package creation
- Director classification
- model route policy
- owner approval gates
- OpenAI request execution for controlled role calls
- validation gate reporting

## MVP Database Scope

Use the approved MVP entities from `DATA_MODEL.md`:

- Project
- Role
- Task
- Conversation
- Message
- Run
- Decision
- Milestone
- Memory
- Approval
- CostLog
- ContextPackage

Runtime schema now also tracks model route metadata where needed.

## MVP Role Scope

Permanent roles only:

- Studio Director
- Product Architect
- Builder
- QA Reviewer
- Memory Writer

No custom role marketplace.

No unlimited agents.

No autonomous role loops.

No casual permanent department creation.

## MVP AI Flow

Default first flow:

1. Owner sends a request.
2. Studio Director classifies the request.
3. Simple status, recap, record review, and simple planning remain Director-only.
4. Heavy, risky, technical, or quality-sensitive work routes to the smallest justified specialist path.
5. Context Builder prepares the smallest useful context.
6. One role receives one task when needed.
7. Role returns structured output.
8. Director summarizes result, risk, missing information, and next action.
9. Owner accepts or rejects the result.
10. Accepted output becomes memory or decision only when useful and approved.
11. Run and cost records are stored when a role call occurs.

## MVP Implementation Phases

### Phase 0 — Runtime Repository Setup

Status: PASSED

Goal:

Create the separate runtime repository and prepare the basic project structure.

### Phase 1 — Database Foundation

Status: PASSED

Goal:

Prepare the approved MVP data model for runtime use.

### Phase 2 — Owner-Only Shell

Status: PASSED

Goal:

Create the private owner-facing app shell.

### Phase 3 — Director Workflow Loop

Status: PASSED

Goal:

Implement the first Director-controlled task loop.

### Phase 4 — First OpenAI Role Call

Status: PASSED

Goal:

Connect one controlled role call to OpenAI.

### Phase 5 — Memory and Decision Acceptance

Status: PASSED

Goal:

Allow owner to accept useful results into memory or decision log.

### Phase 6 — Render Deployment MVP Preparation

Status: PASSED

Goal:

Prepare Render deployment templates and health check without deploying.

### Phase 7 — Model Routing and Cost Policy

Status: PASSED

Goal:

Add model tier routing, approval requirements, and cost policy foundation.

### Phase 8 — Safety Hardening

Status: PASSED

Goal:

Add safety hardening before validation and deployment.

### Phase 9 — Validation Gate and Lean Workflow

Status: IN_PROGRESS

Goal:

Prove runtime validation and prevent workflow bloat before deployment.

Completion rule:

Validation must pass before deployment preparation opens.

### Phase 10 — Deployment Preparation

Status: LOCKED

Goal:

Prepare controlled Render deployment after validation passes.

### Phase 11 — First Private Runtime Deployment

Status: LOCKED

Goal:

Deploy owner-only private runtime after deployment preparation passes.

## MVP Exclusions

Not included in first runtime MVP:

- multi-user team system
- billing
- public accounts
- product project activation
- autonomous deployment
- full GitHub PR automation
- plugin marketplace
- complex permission matrix
- advanced analytics
- mobile app
- desktop app
- real-time multiplayer collaboration
- marketplace for roles/tools
- autonomous coding engine
- unnecessary departments
- unnecessary documentation workflow

## GitHub Integration Scope

First runtime MVP may store repository URLs and reference GitHub manually.

Full automated GitHub PR creation is excluded from MVP.

Safe future GitHub integration can be planned after runtime stability.

## Authentication Scope

First MVP should be private and owner-only.

Minimum acceptable auth:

- owner-only runtime access gate
- protected deployment environment variables

Not included:

- public signup
- teams
- organization accounts
- role-based permission matrix

## Validation Scope

Runtime validation must check:

- static preflight
- Prisma validate
- Prisma generate
- TypeScript check
- Next build
- workflow simulation

Validation reports should be readable and preserved when possible.

Deployment remains locked unless validation passes.

## Success Definition

Runtime MVP is successful when the owner can:

1. use the owner-only runtime
2. create or view a project
3. create or classify a task
4. keep simple work Director-only
5. route heavy work to the correct specialist
6. trigger one Director-controlled role call when needed
7. see the role output
8. accept useful output
9. store accepted result as memory or decision
10. see later task, memory, and decision state
11. see token and cost record for role calls
12. validate the runtime before deployment

## MVP Acceptance Checklist

The Runtime MVP can be accepted only if:

- owner-only access is working
- project creation or project viewing works
- permanent roles exist
- task creation or task classification works
- Director-first lean workflow is preserved
- one Director-controlled role call works
- messages are stored
- Run record is stored when a role call happens
- cost/token record is stored when a role call happens
- accepted output can become Memory
- approved decision can be stored
- validation gate passes
- no product project is active
- no autonomous deployment exists
- no uncontrolled multi-agent loop exists

## Stop Conditions

Stop implementation and return to Director review if:

- scope expands beyond MVP without approval
- product project code enters the runtime repo
- public user system is added too early
- autonomous coding or deployment is added too early
- secrets are committed
- cost tracking is skipped
- database memory is bypassed
- OpenAI is treated as permanent memory
- unnecessary departments slow the workflow
- validation gate is bypassed

## Approval Status

Runtime MVP plan is owner-approved.

Runtime implementation is active.

Deployment preparation is locked until validation passes.

## Final Rule

Build the smallest Studio OS that proves the loop.

Keep it lean, Director-first, and validation-gated.

Do not build the full dream system in MVP.