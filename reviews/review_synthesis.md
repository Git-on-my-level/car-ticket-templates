---
agent: codex
done: false
title: "Review synthesis: [FILL_ME]"
goal: "Turn multiple review inputs into a single prioritized action list"
reasoning: medium
---

## Inputs (fill in)
- Review A ticket: [FILL_ME path]
- Review B ticket: [FILL_ME path]
- Target milestone ticket: [FILL_ME path]

## Context to load
- `.codex-autorunner/workspace/spec.md`
- The reviewed diff/code (as referenced by A/B)

## Synthesis tasks
- [ ] Extract all issues from A and B into one list.
- [ ] Deduplicate and categorize:
  - Must-fix (blocks merge/acceptance criteria)
  - Should-fix (quality, correctness risk)
  - Nice-to-have
- [ ] Resolve disagreements:
  - Pick a direction and justify briefly
  - If unclear, pause and ask the user

## Output (required)
In this ticket, produce:
- Prioritized action list
- Suggested follow-up ticket titles (if many changes)
- A short “merge readiness” recommendation

If must-fix items exist:
- [ ] Create follow-up ticket(s) for the implementer(s).

## Definition of done
- [ ] The action list is prioritized and unambiguous.
- [ ] Follow-up tickets exist for must-fix items (if any).
- [ ] Set `done: true`.
