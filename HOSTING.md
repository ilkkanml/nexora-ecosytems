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

Before implementation starts, choose one permanent hosting direction.

The decision must include:

- frontend host
- backend host
- PostgreSQL provider
- Redis provider
- deployment method
- backup approach
- estimated monthly cost
- scaling path

## Candidate Patterns

### Managed Platform

One managed platform provides app runtime, PostgreSQL, Redis, logs, and deployment.

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

Recommended for the first Studio OS runtime MVP.

Shape:

- Frontend: Render static site or web service
- Backend: Render Node.js web service
- PostgreSQL: Render Postgres
- Redis/Queue: Render Key Value or compatible queue layer
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

Estimated MVP cost:

- low MVP: approximately $17-$30/month
- safer small production: approximately $30-$60/month

Status:

- recommended
- not yet owner-approved

### Option B — Railway Managed Platform

Good alternative for fast deployment and simple developer workflow.

Shape:

- Frontend/backend/services: Railway services
- PostgreSQL: Railway database service
- Redis/Queue: Railway service or plugin/template approach
- Deployment: GitHub deployment
- Logs: Railway logs
- Secrets: environment variables

Why it fits:

- simple project canvas
- fast app deployment
- usage-based pricing
- GitHub deployment support

Risk:

- usage-based pricing may be less predictable
- production database/backup strategy must be checked carefully before final approval

Estimated MVP cost:

- low MVP: approximately $5-$25/month
- safer small production: approximately $20-$60/month

Status:

- alternative
- not selected yet

### Option C — Split Managed Stack

Best future flexibility, but not the simplest MVP path.

Shape:

- Frontend: Vercel
- Backend: Render or Railway
- PostgreSQL: Neon or Supabase
- Redis/Queue: Upstash
- Deployment: GitHub deployment per service
- Logs: provider-specific logs
- Secrets: provider-specific environment variables

Why it fits:

- strong frontend hosting
- strong serverless PostgreSQL options
- lightweight Redis option
- each layer can scale independently

Risk:

- more moving parts
- harder setup
- more places to debug
- not ideal for first Studio OS runtime unless needed

Estimated MVP cost:

- low MVP: approximately $0-$35/month
- safer small production: approximately $35-$100/month

Status:

- future-friendly alternative
- not recommended as first path unless frontend requirements demand it

### Option D — VPS with Docker

Not recommended for the first MVP.

Why not now:

- more server maintenance
- security patching responsibility
- manual backup setup
- more DevOps work before the studio proves its runtime shape

Status:

- deferred

## Recommended Direction

Use Render Managed Platform for the first Studio OS runtime MVP, pending owner approval.

Recommended MVP shape:

- Frontend host: Render
- Backend host: Render Node.js Web Service
- PostgreSQL provider: Render Postgres
- Redis provider: Render Key Value or Redis-compatible queue layer
- Deployment method: GitHub auto-deploy after implementation repo is selected
- Backup approach: managed Postgres backup / recovery features plus manual export policy before production use
- Estimated monthly cost: approximately $17-$60 depending on selected service tiers
- Scaling path: start managed, split database/Redis/frontend later only when real usage requires it

## Approval Requirement

Hosting direction is a major architecture decision.

It must remain pending until owner approval.

No implementation should start from this recommendation alone.

## Final Rule

Do not start implementation until the permanent hosting direction is approved.