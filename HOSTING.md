# Hosting

## Purpose

This document defines the permanent hosting requirements for NEXORA Studio OS.

The studio should not be installed temporarily on a weak or incompatible host.

Every migration creates extra setup, risk, and milestone cost.

## Runtime Requirements

The permanent runtime must support:

- stable Node.js backend
- PostgreSQL
- Redis or queue support
- environment variables
- GitHub deployment
- logs
- backups
- custom domain
- secure secret management
- HTTPS

## GoDaddy / cPanel Position

GoDaddy or cPanel may be used for:

- domain
- DNS
- email if needed

GoDaddy/cPanel should not be the Studio OS runtime unless it provides stable support for the full runtime requirements.

## Database Rule

PostgreSQL stores permanent studio memory.

Redis is used only for temporary operations such as:

- queues
- cache
- rate limits
- job status
- short-lived locks

Redis is not the source of truth.

## Hosting Decision Rule

Before deployment preparation starts, confirm one hosting direction and selected tiers.

The decision must include:

- frontend host
- backend host
- PostgreSQL provider
- Redis provider or deferral decision
- deployment method
- backup approach
- estimated monthly cost
- scaling path
- owner approval

## Candidate Patterns

### Managed Platform

One managed platform provides app runtime, PostgreSQL, Redis-compatible support, logs, and deployment.

Best for:

- simpler operations
- faster launch
- less server maintenance

Risk:

- less provider flexibility
- some scaling limits depend on the platform
- later migration may be needed if the system becomes large

### Split Managed Stack

Different providers handle frontend, backend, database, and Redis.

Best for:

- flexibility
- best-in-class components
- independent scaling per layer

Risk:

- more accounts
- more environment variables
- more integration points
- more debugging surfaces

### VPS with Docker

A server runs the whole stack.

Best for:

- maximum control
- predictable cost

Risk:

- more maintenance
- security updates
- backup management
- monitoring responsibility

## Current MVP Hosting Evaluation

### Option A — Render Managed Platform

Selected for the first Studio OS runtime MVP.

Shape:

- Frontend: Render static site or web service
- Backend: Render Node.js web service
- PostgreSQL: Render Postgres
- Redis/Queue: Render Key Value or compatible queue layer if needed
- Deployment: GitHub auto-deploy or manual deploy
- Logs: Render service logs
- Domain: custom domain via DNS
- Secrets: environment variables

Why it fits:

- one platform for most runtime pieces
- lower operational complexity
- supports GitHub-based deployment
- supports Node.js services
- supports managed Postgres
- supports Redis-compatible key-value service
- good fit before the studio has heavy traffic

Risk:

- estimated cost can grow with database, worker, Redis, and compute tiers
- long-term scaling may require split services later
- advanced observability may need add-ons later
- final pricing must be rechecked on setup day before paid services are created

Estimated MVP cost:

- low paid MVP: approximately $13-$30/month depending on selected service and datastore tiers
- safer small production: approximately $30-$80/month depending on workspace, compute, database, and key-value tiers

Status:

- owner-approved hosting direction
- runtime implementation is active
- deployment preparation is locked until validation passes

### Option B — Railway Managed Platform

Good alternative for fast deployment and simple developer workflow.

Status:

- alternative
- not selected

### Option C — Split Managed Stack

Best future flexibility, but not the simplest MVP path.

Status:

- future-friendly alternative
- not selected as first path

### Option D — VPS with Docker

Not recommended for the first MVP.

Status:

- deferred

## Approved Direction

Use Render Managed Platform for the first Studio OS runtime MVP.

Approved MVP shape:

- Frontend host: Render
- Backend host: Render Node.js Web Service
- PostgreSQL provider: Render Postgres
- Redis provider: Render Key Value or Redis-compatible queue layer if needed
- Deployment method: GitHub deployment after validation and owner approval
- Backup approach: managed Postgres backup / recovery features plus manual export policy before production use
- Estimated monthly cost: approximately $13-$80 depending on selected service tiers
- Scaling path: start managed, split database/Redis/frontend later only when real usage requires it

## Pricing Verification Rule

Provider pricing can change.

Before creating paid runtime resources, check current provider pricing and confirm the selected tiers.

Do not treat old estimates as final billing commitments.

## Implementation Boundary

Hosting direction is approved.

Runtime implementation is active in the separate runtime repository.

Deployment preparation has not started.

Deployment preparation is locked until:

- runtime validation passes
- owner approves deployment preparation
- current pricing is rechecked
- environment variable plan is confirmed

## Final Rule

No validation, no deployment.

No owner approval, no paid hosting resources.