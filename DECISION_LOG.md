# Decision Log

## 2026-05-17 — Clean Studio Foundation Restart

Decision:

Restart the repository as a clean NEXORA Studio OS foundation.

Approved direction:

- No product project is active during foundation phase.
- The studio standard is created first.
- The owner speaks with the Studio Director.
- Roles stay inside their assigned task.
- Project memory belongs in the owner-controlled data system.
- OpenAI is used as the intelligence engine.
- Token usage must be minimized.
- Evidence and uncertainty must be clearly separated.
- Implementation starts only after the standard, data model, workflow, hosting, and repository decision are approved.

Reason:

A clean foundation avoids confusion and prevents product projects from shaping the studio before the studio standard is ready.

Status:

APPROVED

## 2026-05-17 — Complete Clean Setup

Decision:

Complete the foundation document set before implementation begins.

Approved direction:

- Documentation-first setup.
- No runtime implementation yet.
- No product project activation yet.
- PostgreSQL is long-term memory.
- Redis is temporary operations support.
- OpenAI is reasoning support.
- Owner approval is required before major changes.

Reason:

The studio needs a stable standard, data model, workflow, hosting rule, and project intake rule before code starts.

Status:

APPROVED

## 2026-05-17 — Hosting Direction Approval

Decision:

Approve Render Managed Platform as the first runtime hosting direction for NEXORA Studio OS.

Approved direction:

- Frontend host: Render.
- Backend host: Render Node.js Web Service.
- PostgreSQL provider: Render Postgres.
- Redis provider: Render Key Value or Redis-compatible queue layer.
- Deployment method: GitHub auto-deploy after implementation repository is selected.
- Backup approach: managed Postgres backup / recovery features plus manual export policy before production use.
- Estimated monthly cost: approximately $13-$80 depending on selected service tiers.
- Scaling path: start managed, split database, Redis, or frontend later only when real usage requires it.

Boundaries:

- Hosting direction is approved.
- Runtime implementation has not started yet.
- Exact pricing and selected tiers must be rechecked before paid resources are created.
- Implementation repository decision is still required.
- Runtime MVP planning is still required.

Reason:

Render keeps the first Studio OS runtime simple by grouping app runtime, Postgres, Redis-compatible support, logs, environment variables, HTTPS, custom domain support, and GitHub deployment in one managed platform.

Status:

APPROVED

## 2026-05-17 — Separate Runtime Repository Approval

Decision:

Approve a separate runtime implementation repository for NEXORA Studio OS.

Approved direction:

- Current repository remains the foundation and standards repository.
- Runtime code must live in a separate repository.
- Approved runtime repository name: `nexora-studio-os-runtime`.
- Product projects must not be mixed into the runtime repository.
- Runtime implementation must wait for Runtime MVP Planning approval.

Boundaries:

- Repository direction is approved.
- Runtime repository has not been created yet.
- Runtime implementation has not started yet.
- Runtime MVP planning is now the active milestone.

Reason:

Separating foundation documents from runtime code keeps the studio standard stable, reduces scope confusion, and allows clean deployment setup.

Status:

APPROVED
