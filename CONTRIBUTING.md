# Contributing

## Philosophy

These templates should:
- be usable as **plain Markdown** (no template language required)
- be **high-signal** and **model-friendly**
- encourage **small, reviewable diffs**
- encourage durable context under `.codex-autorunner/workspace/`

## Style guidelines

- Keep templates short; prefer checklists over prose.
- Include:
  - Context to load
  - Tasks
  - Verification
  - Stop conditions (pause instead of guessing)
- Avoid:
  - “ignore previous instructions” language
  - instructions to exfiltrate secrets or run unsafe commands
  - large generic essays

## PR hygiene

- One primary intent per PR.
- Add new templates only if they represent a repeated workflow.
