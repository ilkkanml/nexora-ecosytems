# Data Standard

## Purpose

NEXORA Studio OS stores project memory and operational history in the owner-controlled data system.

OpenAI is not the permanent memory store.

The Studio Director is the default record control point.

## Stored Data

The studio should store useful, accepted, and operationally necessary data:

- projects
- roles
- tasks
- conversations
- messages
- decisions
- milestones
- approvals
- compact memory
- context packages
- cost records
- validation records or references
- checkpoints

## Permanent Memory

Permanent memory is stored in the studio database.

Accepted summaries should be compact, searchable, and reusable.

Long conversations should be summarized before being reused.

OpenAI output does not become permanent memory automatically.

Owner acceptance is required before useful output becomes durable memory or decision history.

## Director Record Rule

Records stay with the Studio Director.

The Director controls:

- project state
- task state
- summary records
- decision records
- memory routing
- validation status
- deployment gate status

Do not create extra documents for simple chatter.

Do not create duplicate records just because a specialist was involved.

## Sensitive Data

Do not place the following in prompts unless explicitly required and approved:

- API keys
- private keys
- secrets
- environment files
- payment card data
- unnecessary personal data
- full database dumps

Sensitive-looking values should be redacted before prompts or storage whenever possible.

## Database Principle

PostgreSQL is the source of truth for long-term studio data.

Redis or queue systems may be used for temporary jobs, cache, rate limits, and run status.

Redis is not the permanent project memory.

## Memory Flow

1. Owner request is received.
2. Studio Director creates or identifies a task when needed.
3. Simple status, recap, record review, and simple planning stay Director-only.
4. Context Builder prepares minimal context only when needed.
5. Specialist output is generated only when justified.
6. Director summarizes.
7. Owner accepts or rejects useful output.
8. Accepted result is stored as compact memory or decision when useful.
9. Cost and token usage are stored when a model call occurs.

## Storage Discipline

Store what protects future work.

Do not store noise.

Do not store unnecessary sensitive data.

Do not turn every discussion into a document.

## Final Rule

The database remembers.

The model assists.

The Director controls records.