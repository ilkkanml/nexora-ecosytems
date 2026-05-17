# Data Storage Standard

NEXORA Studio OS keeps project memory in the owner controlled data store.

OpenAI is used for reasoning and generation.

The local project database is the long term source for:

- projects
- tasks
- milestones
- decisions
- role outputs
- compact memory
- approvals
- cost records
- checkpoints

Studio data should be organized so it can be searched, summarized, reused, and audited.

Sensitive data should be kept out of AI context unless it is strictly needed for a task.

Secrets, private keys, payment card data, and unnecessary personal data should not be placed in role prompts.

Default memory flow:

1. Task is created.
2. Minimal context is prepared.
3. Role output is produced.
4. Director summary is created.
5. Accepted result is saved as compact memory.
6. Decision is saved when owner approval is needed.

Final principle:

The database remembers. The model assists.