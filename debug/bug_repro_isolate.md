---
agent: codex
done: false
title: "Debug: reproduce + isolate [FILL_ME]"
goal: "Produce a reliable repro and a credible root-cause hypothesis"
reasoning: medium
---

## Bug report (fill in)
- Symptom: [FILL_ME]
- Expected behavior: [FILL_ME]
- Actual behavior: [FILL_ME]
- Environment/context: [FILL_ME]
- Links/logs: [OPTIONAL]

## Context to load
- `.codex-autorunner/workspace/spec.md` (what “correct” is)
- Relevant code paths: [FILL_ME]
- Existing tests around the area: [FILL_ME]

## Tasks
- [ ] Reproduce the issue reliably (document exact steps).
- [ ] Minimize the repro:
  - smallest input/config that triggers the bug
  - smallest code path involved
- [ ] Identify the likely root cause (file/function/line-level pointers).
- [ ] Propose the smallest safe fix.
- [ ] If possible, write a failing test that captures the bug (optional but strongly preferred).

## Deliverables (required)
- In this ticket:
  - Repro steps (copy/paste runnable if possible)
  - Root cause hypothesis with evidence
  - Proposed fix sketch
- Update `.codex-autorunner/workspace/active_context.md` with:
  - “Bug repro + root cause notes” section

## Stop conditions (pause)
- [ ] Cannot reproduce (need more info)
- [ ] Bug depends on external system/credentials not available
- [ ] Fix requires a high-risk refactor beyond scope
