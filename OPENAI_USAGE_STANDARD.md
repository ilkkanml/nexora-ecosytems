# OpenAI Usage Standard

## Purpose

OpenAI is used as the reasoning and generation engine for NEXORA Studio OS.

The studio backend owns orchestration, storage, approval, memory, and workflow.

## Default Rules

- Use the smallest useful context.
- Do not send full project history by default.
- Do not send secrets, private keys, environment files, payment card data, or unnecessary personal data.
- Store permanent project memory in the owner database.
- Use structured outputs for role responses when possible.
- Log token usage and estimated cost for each run.
- Use model tiers based on task difficulty.
- Do not run uncontrolled multi-role loops.

## Prompt Structure

Keep stable text at the top:

- studio rules
- role definition
- output schema
- truth standard

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

Use stronger models for:

- architecture decisions
- difficult debugging
- security-sensitive reasoning
- cross-project planning
- final Director synthesis when risk is high

## Conversation State

Default approach:

- own database stores state
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

- verified
- inferred
- assumption
- unknown

## Cost Control

Each run should record:

- model
- input tokens
- output tokens
- estimated cost
- task id
- role id

## Final Rule

The model assists. The studio system controls.