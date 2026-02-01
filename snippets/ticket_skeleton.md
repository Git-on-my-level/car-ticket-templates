---
agent: opencode
done: false
title: "[FILL_ME] Short, specific title"
goal: "[FILL_ME] What 'done' means in one sentence"
---

> Template note: Copy this into `.codex-autorunner/tickets/TICKET-###.md` and fill placeholders.

## Context to load (2–5 minutes)
- `.codex-autorunner/workspace/spec.md` (acceptance criteria)
- `.codex-autorunner/workspace/active_context.md` (constraints, current state)
- Relevant repo docs / code locations: [FILL_ME]

## Work plan
- [ ] [FILL_ME] Step 1
- [ ] [FILL_ME] Step 2
- [ ] [FILL_ME] Step 3

## Artifacts
- Files expected to change: [FILL_ME]
- New files expected: [FILL_ME or "none"]
- Workspace docs to update (optional): [active_context.md | decisions.md | spec.md | none]

## Verification
- [ ] Run/verify: [FILL_ME commands or checks]
- [ ] Ensure no unrelated changes (small diff discipline)

## Stop conditions (pause instead of guessing)
Create `DISPATCH.md` with `mode: pause` if:
- [ ] A required decision is ambiguous
- [ ] A risky change needs human approval
- [ ] Verification cannot be run or interpreted
