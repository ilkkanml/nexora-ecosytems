# OpenAI Usage Standard

## Purpose

OpenAI is used as the reasoning and generation engine for NEXORA Studio OS.

The studio backend owns orchestration, storage, approval, memory, validation, cost control, and workflow.

OpenAI is not the permanent memory store.

## Default Rules

- Use the smallest useful context.
- Do not send full project history by default.
- Keep simple status, recap, record review, and simple planning Director-only when possible.
- Use specialist model calls only when the work is heavy, risky, technical, or quality-sensitive.
- Do not send secrets, private keys, environment files, payment card data, or unnecessary personal data.
- Store permanent project memory in the owner database.
- Use structured outputs for role responses when possible.
- Log token usage and estimated cost for each model run.
- Use model tiers based on task difficulty.
- Do not run uncontrolled multi-role loops.
- Do not use high-cost or restricted model routes without owner approval.

## Lean Model Use Rule

The best model call is the one that was actually needed.

Do not call a specialist model for simple records, summaries, or status checks.

Do not use a stronger model only because it is available.

Use role calls to reduce risk, not to create ceremony.

## Prompt Structure

Keep stable text at the top:

- studio rules
- role definition
- output schema
- truth standard
- lean workflow rule

Put changing text near the end:

- project context
- current milestone
- task
- relevant memory
- file excerpts
- expected output

This supports prompt caching and reduces repeated cost.

## Model Tier Policy

Use lower-cost models for:

- routing
- summarization
- memory writing
- simple QA checks
- formatting
- simple status support

Use standard models for:

- normal planning
- normal implementation reasoning
- ordinary role outputs

Use stronger models for:

- architecture decisions
- difficult debugging
- security-sensitive reasoning
- cross-project planning
- final Director synthesis when risk is high

Use restricted or high-cost routes only for:

- unusually long context
- failed prior attempts
- high-risk architecture
- owner-approved expensive reasoning paths

## Conversation State

Default approach:

- owner database stores state
- Studio Director controls records
- context builder prepares each request
- OpenAI receives only what is needed for the task

OpenAI conversation state may be used only when it clearly helps and does not replace the owner database.

## Role Output Shape

Role outputs should be structured:

- role
- task
- result
- risk
- missing_information
- next_action
- confidence

Confidence values:

- VERIFIED
- INFERRED
- ASSUMPTION
- UNKNOWN

## Cost Control

Each model run should record:

- model
- model route tier
- reasoning effort when available
- input tokens
- output tokens
- estimated cost
- task id when available
- role id when available

## Approval Control

Owner approval is required before:

- restricted model route
- high-cost model route
- unusually large context request
- deployment-impacting model action
- security-sensitive model action

## Validation Rule

Model routing and workflow behavior should be covered by simulation before deployment.

Deployment remains locked until validation passes.

## Final Rule

The model assists.

The studio system controls.

Small context beats expensive confusion.