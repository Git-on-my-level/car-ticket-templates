---
agent: codex
done: false
title: "Milestone: [FILL_ME] Feature slice"
goal: "Deliver a vertical slice that satisfies specific acceptance criteria"
reasoning: medium
---

> Template note: A “feature slice” should be end-to-end enough to validate, but small enough to review quickly.

## Scope (fill in)
- Slice name: [FILL_ME]
- Acceptance criteria addressed (from `workspace/spec.md`):
  - [FILL_ME]
  - [FILL_ME]
- Non-goals for this milestone:
  - [FILL_ME or "none"]

## Context to load
- `.codex-autorunner/workspace/spec.md`
- `.codex-autorunner/workspace/active_context.md`
- Relevant code entry points: [FILL_ME]

## Plan
- [ ] Identify the smallest set of modules/files to touch.
- [ ] Implement the slice behind tests (or at least a smoke check).
- [ ] Update docs or comments as needed.

## Tasks
- [ ] Implement: [FILL_ME]
- [ ] Add/adjust tests: [FILL_ME]
- [ ] Update any wiring/config: [FILL_ME]

## Artifacts
- Files expected to change: [FILL_ME]
- New files expected: [FILL_ME or "none"]
- Workspace docs to update (if decisions/constraints changed):
  - [ ] `.codex-autorunner/workspace/active_context.md`
  - [ ] `.codex-autorunner/workspace/decisions.md`

## Verification
- [ ] Run: [FILL_ME commands]
- [ ] Validate acceptance criteria for this slice (explicitly list how you checked each).

## Stop conditions (pause)
Pause if any of these occur:
- [ ] A spec ambiguity blocks implementation
- [ ] Implementation requires risky refactor beyond this milestone
- [ ] Verification cannot be executed
