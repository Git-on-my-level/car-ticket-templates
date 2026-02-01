# CAR Ticket Templates (Blessed Starter Repo)

This repository contains **plain Markdown ticket templates** for **Codex Autorunner (CAR)** workflows.

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
car templates apply blessed:milestones/milestone_feature_slice.md --into tickets --next
```

## Template conventions

- Templates include **placeholders** like `[FILL_ME]` or `[OPTIONAL]`. Replace as needed.
- Templates are intentionally **model-friendly**:
  - explicit context to load
  - explicit “definition of done”
  - “pause instead of guessing” when blocked
- Prefer durable context in `.codex-autorunner/workspace/`:
  - `spec.md` (acceptance criteria)
  - `active_context.md` (constraints + current state)
  - `decisions.md` (why choices were made)

## Directory map (single-level)

- `meta/` — bootstrap / planning tickets (e.g., TICKET-001 pattern)
- `milestones/` — implementation and refactor milestones
- `reviews/` — review tickets (single + multi-agent orchestration patterns)
- `prs/` — PR creation + feedback follow-up
- `debug/` — reproduce/isolate/fix bugs
- `quality/` — tests, observability, performance hygiene
- `docs/` — spec / decisions / context updates
- `snippets/` — small copy/paste snippets (DISPATCH pause/notify, generic ticket skeleton)

## Notes

- This repo is intended to be configured as a **trusted/blessed** template source.
- For **untrusted** template repos, CAR can scan templates before returning content.
