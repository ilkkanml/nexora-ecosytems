# Hosting Standard

## Current Decision

GoDaddy/cPanel is not the runtime target for NEXORA Studio OS.

GoDaddy may be used for domain and DNS management only.

Studio OS needs a modern application hosting environment with:

- stable Node.js runtime
- PostgreSQL
- Redis or Redis-compatible service
- environment variables
- GitHub deployment
- logs
- backups
- custom domain support
- secure secret handling

## Preferred Hosting Shape

Recommended architecture:

- Domain: GoDaddy or Cloudflare DNS
- Frontend: Next.js hosting
- Backend: Node.js/NestJS long-running service
- Database: managed PostgreSQL
- Queue/cache: managed Redis or Redis-compatible service
- Source control: GitHub

## Hosting Rules

1. Do not depend on cPanel for Studio OS runtime.
2. Do not store production secrets in GitHub.
3. Use managed PostgreSQL for project memory.
4. Use Redis only for queue/cache/session needs, not as permanent memory.
5. Store permanent project data in PostgreSQL.
6. Use GitHub-based deployment.
7. Use backups before production use.
8. Keep Studio OS private/internal by default.

## Candidate Hosting Patterns

### Pattern A — Simple Managed PaaS

Use one managed platform for web service, database, and Redis-compatible cache.

Best for:

- fastest launch
- low server maintenance
- simple deployment

### Pattern B — Split Managed Stack

Use separate best-in-class services:

- web/app host
- managed Postgres
- managed Redis

Best for:

- flexibility
- low starting cost
- clean scaling

### Pattern C — VPS + Docker

Use a VPS with Docker and manage services manually or with a panel.

Best for:

- maximum control
- predictable monthly cost

Risk:

- more maintenance
- backups, security, updates, and monitoring become owner responsibility

## Recommended Starting Direction

Start with managed hosting, not cPanel and not self-managed VPS.

Reason:

The first goal is to build the studio, not become a server administrator.

## Final Rule

Studio OS runtime must support Node.js, PostgreSQL, Redis-compatible service, GitHub deployment, logs, backups, and environment variables.