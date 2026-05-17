# Workflow

## Purpose

This document defines the first clean operating workflow for NEXORA Studio OS.

## Default Flow

1. Owner gives a request.
2. Studio Director identifies the real task.
3. Director checks whether a role call is needed.
4. Context Builder prepares the smallest useful context.
5. One role answers the assigned task.
6. Director summarizes result, risk, missing information, and next action.
7. Owner approval is requested when needed.
8. Accepted output is stored as memory.
9. Cost and token usage are logged.

## Owner Interface

The owner normally communicates only with Studio Director.

The owner should not need to manage every role directly.

## Role Call Policy

Default:

- one task
- one role
- one answer
- compact output

Use multiple roles only when the task has cross-domain risk.

## Controlled Review

A controlled review may include:

- Product Architect
- Builder
- QA Reviewer
- Memory Writer

Rules:

- Director starts the review.
- Each role answers once.
- Roles do not run open-ended discussion.
- Director gives final summary.
- Owner sees compact result by default.

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

## Task Output

Default Director output:

- result
- risk
- missing information
- next action
- approval needed or not

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

## Approval Gate

Owner approval is required before:

- implementation
- code change
- database change
- deployment
- billing/payment change
- security-sensitive change
- project direction change

## Failure Rule

After three failed attempts on the same task:

- stop retrying
- record the failure
- identify last safe state
- require Director review

## Final Rule

Small verified steps beat large unclear progress.