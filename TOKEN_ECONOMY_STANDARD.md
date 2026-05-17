# Token Economy Standard

## Goal

Use the smallest useful AI context for each task.

## Rules

- Do not send full project history by default.
- Do not send long files unless required.
- Use compact project memory first.
- Use task-specific context packages.
- Call only the departments needed for the task.
- Prefer one focused department call over many broad calls.
- Use roundtables only for cross-domain decisions.
- Keep department outputs short and structured.
- Store accepted summaries for reuse.
- Stop repeated attempts after three failed tries.

## Context Package Should Include

- project name
- active milestone
- task
- relevant rules
- relevant compact memory
- required file excerpts
- acceptance criteria
- known uncertainty

## Default Department Budget

- Studio Director: medium budget
- Product Architect: low to medium budget
- Builder: medium budget only when implementation detail is needed
- QA / Security: low budget for checks
- Memory / Documentation: low budget

## Final Rule

More context is not better. Useful context is better.