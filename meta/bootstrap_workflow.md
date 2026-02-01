---
agent: codex
done: false
title: "Bootstrap: generate milestone + review + PR ticket backlog"
goal: "Create a coherent, low-ambiguity ticket backlog for this workspace"
reasoning: medium
---

> Template note: Use this as `TICKET-001.md` (or similar) to bootstrap a CAR workflow.

## Inputs (fill in)
- Primary goal: [FILL_ME]
- Risk level: [low | medium | high] (if unsure, assume medium)
- Preferred template repo id (if templates feature is enabled): [blessed]

## Read-first context (required)
- `.codex-autorunner/workspace/spec.md`
- `.codex-autorunner/workspace/active_context.md` (if present)
- `.codex-autorunner/workspace/decisions.md` (if present)
- Any existing tickets under `.codex-autorunner/tickets/`

## Output you must produce in this ticket
1) A **backlog** of follow-up tickets under `.codex-autorunner/tickets/`:
   - milestone implementation tickets
   - review ticket(s) after medium/high-risk milestones
   - an “open PR” ticket at a clear boundary
2) Tighten/append **acceptance criteria** in `.codex-autorunner/workspace/spec.md` if needed.
3) This ticket stays open until (1) + (2) are done.

## How to shape the backlog (CAR-native)
- Prefer **many small tickets** over one large one.
- Each ticket should have one primary intent and clear verification steps.
- Put durable cross-ticket context in workspace docs; avoid “secret knowledge” inside one ticket.
- If risk is medium/high, add explicit review gates (single or multi-agent).

### Suggested ticket sequence (edit as needed)
- Milestone 1: scaffold/interfaces
- Review milestone 1
- Milestone 2: core implementation
- Review milestone 2
- Milestone 3: polish/docs/tests
- Open PR (agent: user, unless GitHub automation exists)

## If the templates feature is enabled (recommended)
Prefer creating follow-up tickets by applying templates rather than drafting from scratch.

Examples:

```bash
# Inspect a template
car templates fetch [TEMPLATE_REPO_ID]:milestones/milestone_feature_slice.md@main

# Create the next ticket from a template (flag names may vary)
car templates apply [TEMPLATE_REPO_ID]:milestones/milestone_feature_slice.md --into tickets --next
```

Then edit the new ticket file to fill placeholders.

## Definition of done
- [ ] Follow-up tickets exist and are ordered/sensible.
- [ ] Each follow-up ticket has:
  - `agent`, `done: false`, `title`, `goal`
  - concrete steps and verification
- [ ] Workspace spec has clear acceptance criteria (or you explicitly note why not).
- [ ] Set this ticket’s `done: true`.
