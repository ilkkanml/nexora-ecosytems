# Data Model

## Purpose

This document defines the first clean database model for NEXORA Studio OS.

The database is the permanent memory of the studio.

OpenAI is the intelligence engine, not the permanent data store.

## MVP Entities

### Project

Represents a project managed by the studio.

Fields:

- id
- name
- type
- status
- description
- repositoryUrl
- createdAt
- updatedAt

Types:

- WEB_DESIGN
- WEB_APP
- MOBILE_APP
- TV_APP
- GAME
- BACKEND_PLATFORM
- INTERNAL_TOOL

### Role

Represents a studio role.

Fields:

- id
- name
- description
- isPermanent
- isActive
- defaultModelTier
- createdAt
- updatedAt

Permanent roles:

- Studio Director
- Product Architect
- Builder
- QA Reviewer
- Memory Writer

### Task

Represents a unit of work.

Fields:

- id
- projectId
- milestoneId
- title
- goal
- status
- priority
- requiredRoleId
- requiresOwnerApproval
- createdAt
- updatedAt
- completedAt

Statuses:

- DRAFT
- READY
- IN_PROGRESS
- WAITING_OWNER
- PASSED
- FAILED
- CLOSED

### Conversation

Represents one role call or one controlled review.

Fields:

- id
- taskId
- type
- status
- tokenBudget
- maxTurns
- directorSummary
- createdAt
- completedAt

Types:

- DIRECTOR_ONLY
- SINGLE_ROLE
- CONTROLLED_REVIEW

### Message

Stores user, Director, role, and owner-facing message content.

Fields:

- id
- conversationId
- roleId
- runId
- messageType
- content
- createdAt

Message types:

- USER_REQUEST
- DIRECTOR_CONTEXT
- ROLE_OUTPUT
- DIRECTOR_SUMMARY
- OWNER_DECISION

### Run

Represents one technical model execution or tool-assisted role execution.

Run is separate from Message because a conversation may contain many messages, but each model call needs its own technical record.

Fields:

- id
- conversationId
- taskId
- roleId
- contextPackageId
- provider
- model
- status
- inputTokens
- outputTokens
- estimatedCost
- startedAt
- completedAt
- errorMessage

Statuses:

- QUEUED
- RUNNING
- SUCCEEDED
- FAILED
- CANCELLED

### Decision

Stores owner-level decisions.

Fields:

- id
- projectId
- taskId
- title
- decision
- reason
- status
- createdAt
- updatedAt

Statuses:

- PROPOSED
- APPROVED
- REJECTED
- REPLACED

### Milestone

Stores project progress structure.

Fields:

- id
- projectId
- title
- goal
- status
- orderIndex
- completionRulesJson
- createdAt
- updatedAt

Statuses:

- NOT_STARTED
- IN_PROGRESS
- PASSED
- FAILED
- LOCKED

### Memory

Stores compact reusable memory.

Fields:

- id
- projectId
- sourceType
- title
- content
- reliability
- createdAt
- updatedAt

Reliability values:

- VERIFIED
- OWNER_APPROVED
- INFERRED
- OUTDATED

### Approval

Stores owner approvals.

Fields:

- id
- projectId
- taskId
- decisionId
- approvalType
- status
- notes
- createdAt
- approvedAt

Statuses:

- REQUIRED
- APPROVED
- REJECTED
- EXPIRED

### CostLog

Stores AI usage cost records.

CostLog may summarize Run records for reporting.

Fields:

- id
- projectId
- taskId
- conversationId
- runId
- provider
- model
- inputTokens
- outputTokens
- estimatedCost
- createdAt

### ContextPackage

Stores prepared task context.

Fields:

- id
- taskId
- projectId
- summary
- includedMemoryIds
- includedFileRefs
- tokenEstimate
- createdAt

## Data Rules

- PostgreSQL is the source of truth.
- Redis may be used for jobs, cache, rate limits, and temporary run status.
- Redis is not permanent memory.
- Accepted summaries become reusable memory.
- Long conversations should be compacted before reuse.
- Sensitive data should not be sent to model context unless explicitly required and approved.

## MVP Scope

The first working version only needs:

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

## Entity Separation

- Conversation stores the logical work session.
- Message stores readable content.
- Run stores technical model execution details.
- CostLog stores reporting-friendly usage records.

## Final Rule

The database remembers. The model assists.