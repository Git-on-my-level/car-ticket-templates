# CAR Ticket Templates (Blessed Starter Repo)

This repository contains **plain Markdown ticket templates** for **[Codex Autorunner (CAR)](https://github.com/Git-on-my-level/codex-autorunner)**.

Tickets are the control plane of CAR, so you can think of these ticket templates as **programs** that you can run within CAR on your codebase.

Templates are meant to be copied into a workspace at:

- `.codex-autorunner/tickets/TICKET-###.md`

CAR processes tickets in numeric order, using YAML frontmatter keys:

- `agent` (e.g., `codex`, `opencode`, or `user`)
- `done` (`false` until complete)
- optional: `title`, `goal`, `model`, `reasoning`

## How to use (with the templates feature)

Fetch to stdout:

```bash
car templates fetch blessed:reviews/review_single.md@main
```

Create a new ticket from a template (exact flags may vary by CAR version):

```bash
car templates apply blessed:bootstrap/bootstrap_from_github_issue.md --into tickets --next
```

## Template conventions

Read [CONTRIBUTING.md](CONTRIBUTING.md) if you would like to submit a template.

- Templates include **placeholders** like `[FILL_ME]` or `[OPTIONAL]`. Replace as needed.
- Templates are intentionally **model-friendly**:
  - explicit context to load
  - explicit “definition of done”
  - “pause instead of guessing” when blocked

## Notes

- This repo is the **blessed** template source and trusted by CAR on default install unless configured otherwise.
