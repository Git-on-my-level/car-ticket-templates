---
agent: opencode
done: false
title: "Address review feedback: [FILL_ME]"
goal: "Resolve review items with minimal diff and clear verification"
---

## Inputs (fill in)
- PR / branch: [FILL_ME]
- Review source:
  - [ ] Code review ticket(s): [FILL_ME]
  - [ ] PR comments pasted below
- Must-fix items:
  - [FILL_ME]
  - [FILL_ME]

## Context to load
- Relevant review tickets / comments
- `.codex-autorunner/workspace/spec.md` (ensure changes still meet acceptance)

## Work plan
- [ ] Turn must-fix items into a checklist with file-level pointers.
- [ ] Implement changes, keeping diffs focused.
- [ ] Add/adjust tests if behavior changes.
- [ ] Re-run verification.

## Verification
- [ ] Run: [FILL_ME]
- [ ] Confirm must-fix items are resolved (explicitly check each).

## Definition of done
- [ ] Must-fix items are addressed (or clearly explained why not).
- [ ] Verification passes (or failures are explained and paused).
- [ ] Set `done: true`.
