# NEXORA Studio OS Database Plan

## Purpose

Studio OS stores project management, AI department conversations, decisions, milestones, approvals, memory, checkpoints, and cost logs in the owner-controlled database.

OpenAI is used as the intelligence engine.

The owner database is the permanent project memory.

## MVP Entities

### StudioProject

Represents a managed project.

Fields:

- id
- name
- type
- status
- description
- primaryRepo
- createdAt
- updatedAt

Project types:

- WEB_DESIGN
- WEB_APP
- MOBILE_APP
- TV_APP
- GAME
- BACKEND_PLATFORM
- INTERNAL_TOOL

### StudioDepartment

Represents a permanent or temporary department.

Fields:

- id
- name
- type
- mode
- isPermanent
- isActive
- systemPromptKey
- createdAt
- updatedAt

Permanent departments:

- Studio Director
- Product Architect
- Builder
- QA / Security
- Memory / Documentation

### StudioTask

Represents a unit of work.

Fields:

- id
- projectId
- milestoneId
- title
- description
- status
- priority
- assignedDepartmentId
- requiresOwnerApproval
- targetRepo
- createdAt
- updatedAt
- completedAt

### StudioConversation

Represents a department call or roundtable.

Fields:

- id
- taskId
- type
- status
- maxTurns
- tokenBudget
- directorSummary
- createdAt
- completedAt

Conversation types:

- SINGLE_DEPARTMENT
- CONTROLLED_ROUNDTABLE
- DIRECTOR_ONLY

### StudioMessage

Stores messages and outputs.

Fields:

- id
- conversationId
- departmentId
- role
- content
- model
- inputTokens
- outputTokens
- costEstimate
- createdAt

### StudioDecision

Stores important decisions.

Fields:

- id
- projectId
- taskId
- title
- decision
- reason
- status
- approvedByOwner
- locked
- createdAt

### StudioMilestone

Stores milestone structure.

Fields:

- id
- projectId
- title
- goal
- status
- completionRulesJson
- orderIndex
- createdAt
- updatedAt

### StudioConstitution

Stores project/studio rules.

Fields:

- id
- projectId
- title
- content
- version
- isLocked
- createdAt
- updatedAt

### StudioMemory

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

### StudioApproval

Stores owner approvals.

Fields:

- id
- projectId
- taskId
- decisionId
- approvalType
- status
- approvedBy
- approvedAt
- notes

### StudioCostLog

Stores token and estimated cost data.

Fields:

- id
- projectId
- taskId
- conversationId
- model
- inputTokens
- outputTokens
- estimatedCost
- createdAt

### StudioCheckpoint

Stores safe project checkpoints.

Fields:

- id
- projectId
- targetRepo
- label
- commitSha
- branchName
- notes
- createdAt

### StudioContextPackage

Stores prepared minimal context packages.

Fields:

- id
- taskId
- projectId
- includedMemoryIds
- includedFileRefs
- promptSummary
- tokenEstimate
- createdAt

## Data Separation Rule

Studio OS internal data must be separated from customer-facing Nexora product data.

Internal studio routes, APIs, and database access must not be exposed to customers.

## Sensitive Data Rules

Do not store:

- raw API keys
- private keys
- production secrets
- payment card data
- unnecessary customer personal data in AI messages

Do store:

- compact decisions
- task summaries
- accepted outputs
- token usage
- approval records
- checkpoint references

## First MVP Database Scope

For the first implementation, only these are required:

- StudioProject
- StudioDepartment
- StudioTask
- StudioConversation
- StudioMessage
- StudioDecision
- StudioMilestone
- StudioMemory
- StudioApproval
- StudioCostLog

Everything else can be added after the first working loop.