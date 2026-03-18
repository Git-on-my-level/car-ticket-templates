# AGENTS.md

## Purpose

This repository contains reusable Markdown templates for Codex Autorunner (CAR). Treat changes here as changes to a template library, not to an application codebase.

Most tasks in this repo should result in one of these outcomes:
- add a new reusable template
- refine an existing template
- tighten template wording so an agent can execute it more reliably
- update repo documentation about how templates should be used

Do not treat this repo itself as a CAR workspace unless the user explicitly asks for that. In normal work here, files under `.codex-autorunner/tickets/` are examples or output destinations mentioned by templates, not files you should create in this repo.

## Repo layout

- `README.md`: repo purpose and high-level usage
- `CONTRIBUTING.md`: template philosophy and contribution guidelines
- `bootstrap/`: templates for initial decomposition and planning
- `reviews/`: templates for review workflows
- `refactor/`: templates for refactor-oriented planning and execution chains

When adding a template, place it in the most specific top-level folder that matches its workflow. If no folder fits and the workflow is genuinely reusable, create a new top-level category only if the distinction is clear and durable.

## Working rules

- Read `README.md` and `CONTRIBUTING.md` before making substantive template changes.
- Match the style of nearby templates before inventing a new structure.
- Keep templates plain Markdown with YAML frontmatter.
- Preserve the repo’s core philosophy: tickets are executable instructions for agents, so ambiguity is a bug.
- Prefer reusable instructions over codebase-specific assumptions.
- Use placeholders like `[FILL_ME]` or `<descriptive placeholder>` when the template will be reused across repositories.
- Keep templates focused on one repeated workflow. Do not bundle unrelated workflows into one file.
- When a template is for planning only, say so explicitly and state what it must not implement.
- Make stop conditions explicit when guessing would be risky.

## Template quality bar

A good template in this repo should:
- state its purpose in the frontmatter `title` and `goal`
- make the expected inputs explicit
- tell the agent what context to load
- define the concrete output artifact(s)
- include observable completion criteria
- avoid relying on hidden chat history
- be portable across repos, unless the template is intentionally specialized

When editing a template, optimize for agent reliability:
- reduce vague words like "clean up", "improve", or "handle"
- replace broad intent with explicit decision rules
- add applicability gates when a workflow only fits certain problems
- separate planning, implementation, and review responsibilities when that distinction matters

## Frontmatter conventions

Templates in this repo generally use:

```yaml
---
agent: <strong planning agent|strong coding agent|user>
done: false
title: "..."
goal: "..."
---
```

Optional keys like `reasoning` are fine when they materially clarify execution. Keep frontmatter minimal otherwise.

## Naming conventions

- Use descriptive snake-like filenames with `.md`, for example `review_single.md` or `refactor_contraction_loop.md`.
- Name files by reusable workflow, not by one-off issue or repository.
- Keep titles human-readable and goals action-oriented.

## What to avoid

- Do not add templates that are just generic essays or best-practice checklists.
- Do not bake in OS-specific commands unless the workflow truly requires them.
- Do not assume the destination repo has a particular language, framework, CI system, or directory structure unless the template explicitly says so.
- Do not create unnecessary ceremony or placeholder sections that do not help an agent act.
- Do not overfit a template to one anecdotal task if the workflow is not meaningfully reusable.

## Validation

Before finishing:
- read the full template you changed
- check that section names and placeholders are internally consistent
- confirm the template clearly distinguishes inputs, tasks, and completion criteria
- verify new files are in the correct category directory

If the user asks whether a template is "clear enough", review it from the perspective of a fresh agent with only the file contents available. Tighten applicability, scope boundaries, and stop conditions before adding more detail.
