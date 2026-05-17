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

### Split Managed Stack

Different providers handle frontend, backend, database, and Redis.

Best for:

- flexibility
- best-in-class components

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

## Final Rule

Do not start implementation until the permanent hosting direction is approved.