---
agent: codex
done: false
title: "Meta: split oversized ticket into smaller tickets"
goal: "Reduce scope/ambiguity by creating a small, ordered set of follow-up tickets"
reasoning: medium
---

> Template note: Use when a ticket has grown too large or ambiguous and needs decomposition.

## Inputs (fill in)
- Ticket to split: [FILL_ME: path, e.g. `.codex-autorunner/tickets/TICKET-012.md`]
- Desired outcome / acceptance criteria: [FILL_ME]

## Read-first context (required)
- The ticket being split
- `.codex-autorunner/workspace/spec.md`
- `.codex-autorunner/workspace/active_context.md`

## Decomposition rules
- Each new ticket has one primary intent.
- Tickets must be runnable in numeric order without hidden context.
- Add review gates only when risk warrants it.

## Work
- [ ] Summarize the current oversized ticket in 5–10 lines (in this ticket body).
- [ ] Draft 3–10 follow-up tickets under `.codex-autorunner/tickets/`:
  - implementation tickets
  - review ticket(s) (optional)
  - open PR ticket (optional)
- [ ] Edit the original ticket:
  - mark it `done: true` (only after the split tickets exist)
  - add a short pointer to the new tickets

## Definition of done
- [ ] New tickets exist with clear goals + verification.
- [ ] Oversized ticket is closed with a pointer to the new queue.
