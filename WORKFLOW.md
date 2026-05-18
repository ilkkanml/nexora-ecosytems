# Workflow

## Purpose

This document defines the first clean operating workflow for NEXORA Studio OS.

The workflow must keep the studio fast, controlled, truthful, and low-noise.

## Core Principle

The owner speaks with the Studio Director.

The Studio Director controls role calls, context size, summaries, approvals, memory storage, and next actions.

Roles answer only their assigned task.

## Default Flow

1. Owner gives a request.
2. Studio Director identifies the real task.
3. Director classifies the task type.
4. Director decides whether a role call is needed.
5. Context Builder prepares the smallest useful context.
6. One role answers the assigned task.
7. Director checks result, risk, missing information, and next action.
8. Owner approval is requested when needed.
9. Accepted output is stored as memory.
10. Cost and token usage are logged.

## Workflow Modes

### Director Only

Use when the request can be answered from existing approved memory or current standards.

Examples:

- status summary
- simple decision recap
- next-step explanation
- asking what is currently active

### Single Role

Default execution mode.

Use when one role can answer the task clearly.

Examples:

- Product Architect defines scope
- Builder reviews technical shape
- QA Reviewer checks risk
- Memory Writer summarizes accepted output

### Controlled Review

Use only when a task has cross-domain risk.

Examples:

- data model approval
- hosting decision
- implementation repository decision
- security-sensitive workflow
- project activation decision

### Owner Approval

Use when a decision changes direction, starts implementation, changes data, changes hosting, changes security posture, or activates a project.

## Owner Interface

The owner normally communicates only with Studio Director.

The owner should not need to manage every role directly.

The owner sees compact results by default.

Detailed role outputs can be shown only when needed.

## Director Decision Tree

For each owner request, the Studio Director decides:

1. Is this already answered by approved memory?
2. Is a role call needed?
3. Which single role is sufficient?
4. Is controlled review required?
5. Is owner approval required?
6. Should the result be stored as memory?
7. Should a decision record be created?

## Role Call Policy

Default:

- one task
- one role
- one answer
- compact output

Role calls must include:

- task
- expected output
- relevant context
- constraints
- confidence requirement

Use multiple roles only when the task has cross-domain risk.

## Controlled Review Policy

A controlled review may include:

- Product Architect
- Builder
- QA Reviewer
- Memory Writer

Rules:

- Director starts the review.
- Each role answers once.
- Roles do not run open-ended discussion.
- Roles do not speak directly to the owner.
- Director gives final summary.
- Owner sees compact result by default.

Default limits:

- max roles: 4
- max turns per role: 1
- Director final summary required
- owner approval required for major decisions

## Context Builder Rule

Context should include only:

- project name
- active milestone
- task
- relevant standard rules
- relevant compact memory
- required file excerpts
- expected output
- known uncertainty

Do not include full history by default.

Do not include secrets, private keys, environment files, payment card data, or unnecessary personal data.

## Output Contract

### Director Output

Default Director output:

- result
- risk
- missing information
- next action
- approval needed or not

### Role Output

Default role output:

- role
- task
- result
- risk
- missing information
- next action
- confidence

Confidence values:

- VERIFIED
- INFERRED
- ASSUMPTION
- UNKNOWN

## Truth Check

Before the Director summarizes, the result should be checked for:

- unsupported claims
- hidden assumptions
- missing evidence
- scope expansion
- false completion language

A result must not be marked verified, tested, complete, implemented, deployed, or fixed unless evidence exists.

## Approval Gate

Owner approval is required before:

- implementation
- file change
- code change
- database change
- deployment
- billing/payment change
- security-sensitive change
- hosting decision
- implementation repository decision
- project activation
- project direction change

Approval result can be:

- APPROVED
- REJECTED
- NEEDS_REVISION

## Storage Rule

Store:

- accepted summaries
- decisions
- approvals
- task state
- role outputs
- model runs
- cost records
- compact memory

Do not store unnecessary sensitive data in prompts or memory.

## Failure Rule

After three failed attempts on the same task:

- stop retrying
- record the failure
- identify last safe state
- require Director review
- simplify or redesign the task

## Completion Rule

A workflow is complete only when:

- expected output exists
- risk is stated
- missing information is stated
- approval need is clear
- storage need is clear
- next action is clear

## Final Rule

Small verified steps beat large unclear progress.