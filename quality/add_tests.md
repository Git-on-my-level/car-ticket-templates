---
agent: opencode
done: false
title: "Add tests: [FILL_ME]"
goal: "Increase confidence by adding targeted automated tests"
---

## Inputs (fill in)
- Area under test: [FILL_ME]
- Behaviors to test:
  - [FILL_ME]
  - [FILL_ME]

## Context to load
- Existing test framework and patterns: [FILL_ME]
- Relevant modules: [FILL_ME]
- `.codex-autorunner/workspace/spec.md` (if tests map to acceptance criteria)

## Tasks
- [ ] Identify the best test layer (unit/integration/e2e) for each behavior.
- [ ] Add tests following existing repo conventions.
- [ ] Ensure tests are deterministic and not flaky.
- [ ] Run test suite (or relevant subset).

## Verification
- [ ] Run: [FILL_ME]
- [ ] Confirm tests fail without the change (where feasible) and pass with it.

## Definition of done
- [ ] New tests are readable and stable.
- [ ] Verification passes.
- [ ] Set `done: true`.
