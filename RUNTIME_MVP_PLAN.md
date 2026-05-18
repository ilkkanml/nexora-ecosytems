# Runtime MVP Plan

## Purpose

This document defines the first working runtime scope for NEXORA Studio OS.

The goal is not to build the full studio.

The goal is to build the smallest useful version that proves the Studio Director workflow, database memory, role calls, and cost logging can work together.

## Current Boundary

Runtime MVP planning is active.

Runtime implementation has not started yet.

The runtime repository has not been created yet.

No product project is active.

## Approved Runtime Direction

Hosting direction:

- Render Managed Platform

Repository direction:

- separate runtime repository
- approved name: `nexora-studio-os-runtime`

Database direction:

- PostgreSQL is the source of truth
- Redis is temporary operations support only

AI direction:

- OpenAI is the reasoning and generation engine
- Studio OS owns orchestration, memory, approvals, and workflow

## MVP Goal

Create a private owner-controlled Studio OS runtime that can:

1. create and view a project
2. define the permanent studio roles
3. create and track tasks
4. run one controlled role call through the Studio Director workflow
5. store conversation messages
6. store model run records
7. store decisions
8. store compact memory
9. store cost/token usage
10. show a clear next action

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

### Projects

Allows:

- create project
- view project
- update project status

### Tasks

Allows:

- create task
- assign required role
- set task status
- view task history

### Director Console

Allows:

- owner sends request
- Director classifies task
- Director prepares or confirms next action
- role call can be triggered when needed

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
- OpenAI request execution for one role call

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

## MVP AI Flow

Default first flow:

1. Owner creates or selects a task.
2. Studio Director identifies the task type.
3. Context Builder prepares smallest useful context.
4. One role receives one task.
5. Role returns structured output.
6. Director summarizes result, risk, missing information, and next action.
7. Owner accepts or rejects the result.
8. Accepted output becomes memory if useful.
9. Run and cost records are stored.

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

## GitHub Integration Scope

First runtime MVP may store repository URLs and reference GitHub manually.

Full automated GitHub PR creation is excluded from MVP.

Safe future GitHub integration can be planned after runtime stability.

## Authentication Scope

First MVP should be private and owner-only.

Minimum acceptable auth:

- protected owner login or platform-level private access

Not included:

- public signup
- teams
- organization accounts
- role-based permission matrix

## Success Definition

Runtime MVP is successful when the owner can:

1. create a project
2. create a task
3. trigger one Director-controlled role call
4. see the role output
5. accept the output
6. store the accepted result as memory
7. see the decision/memory/task state later
8. see token and cost record for the run

## Approval Requirement

Runtime MVP plan must be owner-approved before runtime implementation starts.

## Final Rule

Build the smallest Studio OS that proves the loop.

Do not build the full dream system in MVP.