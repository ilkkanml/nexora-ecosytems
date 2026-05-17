# Data Standard

## Purpose

NEXORA Studio OS stores project memory and operational history in the owner-controlled data system.

OpenAI is not the permanent memory store.

## Stored Data

The studio should store:

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
- checkpoints

## Permanent Memory

Permanent memory is stored in the studio database.

Accepted summaries should be compact, searchable, and reusable.

Long conversations should be summarized before being reused.

## Sensitive Data

Do not place the following in prompts unless explicitly required and approved:

- API keys
- private keys
- secrets
- environment files
- payment card data
- unnecessary personal data
- full database dumps

## Database Principle

PostgreSQL is the source of truth for long-term studio data.

Redis or queue systems may be used for temporary jobs, cache, rate limits, and run status.

Redis is not the permanent project memory.

## Memory Flow

1. Owner request is received.
2. Studio Director creates or identifies a task.
3. Context Builder prepares minimal context.
4. Role output is generated.
5. Director summarizes.
6. Accepted result is stored as compact memory.
7. Important decisions are stored in the decision log.
8. Cost and token usage are stored.

## Final Rule

The database remembers. The model assists.