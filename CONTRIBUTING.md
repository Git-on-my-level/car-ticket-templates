# Contributing

## Philosophy

You should think of *tickets as software*. Since tickets are the control plane for CAR you must write your tickets so that they are executable reliably by an agent. This means you should avoid things that are overly specific, like specific to an OS or machine, reliance on any non-CAR tools, or best practices/behaviors that are specific to a particular codebase.

## Style guidelines

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
