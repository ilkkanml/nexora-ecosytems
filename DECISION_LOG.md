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

## 2026-05-17 — Runtime MVP Plan Approval

Decision:

Approve the first Runtime MVP plan for NEXORA Studio OS.

Approved direction:

- Build the smallest useful runtime that proves the Studio Director loop.
- Runtime MVP is owner-only.
- Use the approved MVP data model.
- Use permanent roles only.
- Implement one Director-controlled role call before any advanced automation.
- Store messages, runs, decisions, memory, and token/cost records.
- Exclude product projects, billing, public accounts, autonomous deployment, full GitHub PR automation, and autonomous coding engine from MVP.

Approved phases:

- Phase 0 — Runtime Repository Setup.
- Phase 1 — Database Foundation.
- Phase 2 — Owner-Only Shell.
- Phase 3 — Director Workflow Loop.
- Phase 4 — First OpenAI Role Call.
- Phase 5 — Memory and Decision Acceptance.
- Phase 6 — Render Deployment MVP.

Boundaries:

- Runtime MVP plan is approved.
- Runtime repository still needs to be created.
- Runtime implementation has not started yet.
- No paid hosting resources should be created before tier and pricing confirmation.

Reason:

A narrow MVP prevents the studio runtime from becoming a large uncontrolled system before the core loop is proven.

Status:

APPROVED

## 2026-05-18 — Runtime Repository Active

Decision:

Runtime implementation repository is active.

Approved direction:

- Runtime implementation lives in `ilkkanml/nexora-studio-os-runtime`.
- Foundation repository remains standards and decisions only.
- Runtime repository contains no product project code.
- Product project activation remains blocked until the Studio OS runtime proves the core loop.

Status:

APPROVED

## 2026-05-18 — Lean Department Policy

Decision:

Adopt Director-first workflow and avoid unnecessary departments.

Approved direction:

- Studio Director is the default control point.
- Simple status, recap, record review, and simple planning stay Director-only.
- Specialists are used only for heavy, risky, technical, or quality-sensitive work.
- Records stay with the Director.
- New permanent departments must not be added casually.
- Temporary specialists may be used only for narrow, justified work.

Reason:

The Studio OS must stay fast and useful without increasing error risk.

Unnecessary departments and documents slow the project.

Skipping specialist review for heavy work increases risk.

Status:

APPROVED

## 2026-05-18 — Validation Before Deployment

Decision:

Deployment remains locked until validation passes.

Approved direction:

- Runtime validation must run before deployment preparation.
- Validation gate must check static preflight, Prisma validate, Prisma generate, TypeScript, build, and workflow simulation.
- Validation should produce readable reports.
- GitHub Actions should preserve validation reports as artifacts.
- Phase 10 deployment preparation remains locked until Phase 9 validation passes.

Reason:

The runtime should not be deployed before its safety, schema, build, and workflow checks pass.

Status:

APPROVED
