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

## Entity Relationships

### Project Relationships

Project has many:

- Milestones
- Tasks
- Decisions
- Memory records
- Approvals
- CostLogs
- ContextPackages

### Milestone Relationships

Milestone belongs to one Project.

Milestone has many Tasks.

### Task Relationships

Task belongs to one Project.

Task may belong to one Milestone.

Task may require one Role.

Task has many:

- Conversations
- Runs
- Messages through Conversations
- Decisions
- Approvals
- CostLogs
- ContextPackages

### Conversation Relationships

Conversation belongs to one Task.

Conversation has many:

- Messages
- Runs

### Message Relationships

Message belongs to one Conversation.

Message may belong to one Role.

Message may belong to one Run.

### Run Relationships

Run belongs to one Conversation.

Run belongs to one Task.

Run belongs to one Role.

Run may use one ContextPackage.

Run may create many Messages.

Run may have one or more CostLogs.

### Decision Relationships

Decision belongs to one Project.

Decision may belong to one Task.

Decision may have one Approval.

### Memory Relationships

Memory belongs to one Project.

Memory may be referenced by many ContextPackages.

### Approval Relationships

Approval belongs to one Project.

Approval may belong to one Task.

Approval may belong to one Decision.

### CostLog Relationships

CostLog belongs to one Project.

CostLog may belong to one Task.

CostLog may belong to one Conversation.

CostLog may belong to one Run.

### ContextPackage Relationships

ContextPackage belongs to one Project.

ContextPackage belongs to one Task.

ContextPackage may be used by many Runs.

ContextPackage may reference many Memory records and file references.

## Required vs Optional Fields

### Global Required Fields

Every main entity should have:

- id
- createdAt

Entities that can be edited should also have:

- updatedAt

### Required Identity Fields

These fields should be required because they define the record:

- Project.name
- Project.type
- Project.status
- Role.name
- Role.isPermanent
- Role.isActive
- Task.projectId
- Task.title
- Task.status
- Conversation.taskId
- Conversation.type
- Conversation.status
- Message.conversationId
- Message.messageType
- Message.content
- Run.conversationId
- Run.taskId
- Run.roleId
- Run.provider
- Run.model
- Run.status
- Decision.projectId
- Decision.title
- Decision.status
- Milestone.projectId
- Milestone.title
- Milestone.status
- Memory.projectId
- Memory.title
- Memory.content
- Memory.reliability
- Approval.projectId
- Approval.status
- CostLog.projectId
- CostLog.provider
- CostLog.model
- ContextPackage.projectId
- ContextPackage.taskId
- ContextPackage.summary

### Optional Workflow Fields

These fields should be optional because they depend on progress or context:

- Project.description
- Project.repositoryUrl
- Task.milestoneId
- Task.requiredRoleId
- Task.completedAt
- Conversation.directorSummary
- Conversation.completedAt
- Message.roleId
- Message.runId
- Run.contextPackageId
- Run.completedAt
- Run.errorMessage
- Decision.taskId
- Decision.reason
- Approval.taskId
- Approval.decisionId
- Approval.notes
- Approval.approvedAt
- CostLog.taskId
- CostLog.conversationId
- CostLog.runId
- ContextPackage.includedMemoryIds
- ContextPackage.includedFileRefs

### Required Status Rule

Every entity that moves through a workflow must have a required status field.

Status should use enums, not free text.

### Optional Timestamp Rule

Start timestamps may be required when execution begins.

Completion timestamps should remain optional until work finishes.

### Final Field Rule

Required fields should describe what the record is.

Optional fields should describe what happened later.

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

## MVP Exclusions

The first working version should not include these systems yet:

- multi-user team management
- complex permission matrix
- billing system
- public customer accounts
- autonomous deployment
- full GitHub PR automation
- plugin marketplace
- multi-tenant organization system
- advanced analytics dashboard
- marketplace for roles or tools

## Future Backlog

The excluded systems are not rejected.

They are parked for later review after the Studio OS runtime MVP is stable.

Future candidates:

- team accounts
- organization workspaces
- advanced permissions
- GitHub PR automation
- deployment assistant
- billing and usage plans
- advanced reporting
- plugin/tool registry
- project templates marketplace

## Backlog Rule

If something is excluded from MVP, it must be listed here or in a future backlog record.

Do not rely on memory alone.

## Entity Separation

- Conversation stores the logical work session.
- Message stores readable content.
- Run stores technical model execution details.
- CostLog stores reporting-friendly usage records.

## Final Rule

The database remembers. The model assists.