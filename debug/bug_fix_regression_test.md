---
agent: opencode
done: false
title: "Fix bug: [FILL_ME]"
goal: "Fix the bug and add/verify a regression test"
---

> Template note: If the fix is complex or touches risky areas, consider switching `agent: codex`.

## Inputs (fill in)
- Repro/root-cause ticket: [FILL_ME path]
- Bug acceptance criteria: [FILL_ME]
- Target branch: [FILL_ME]

## Context to load
- The repro ticket (required)
- Relevant modules/files: [FILL_ME]
- `.codex-autorunner/workspace/spec.md`

## Plan
- [ ] Implement the minimal fix consistent with the root cause.
- [ ] Add a regression test (or strengthen an existing test).
- [ ] Verify the repro no longer fails.

## Tasks
- [ ] Implement fix: [FILL_ME]
- [ ] Add regression test: [FILL_ME]
- [ ] Run verification:
  - [ ] [FILL_ME commands]

## Definition of done
- [ ] Regression test exists and would have failed before the fix.
- [ ] Verification passes.
- [ ] Root cause ticket is referenced/updated as resolved (optional).
- [ ] Set `done: true`.
