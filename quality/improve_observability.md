---
agent: opencode
done: false
title: "Improve observability: [FILL_ME]"
goal: "Make failures diagnosable by adding high-signal logs/errors/artifacts"
---

## Inputs (fill in)
- What is hard to debug today: [FILL_ME]
- Where failures occur (modules/paths): [FILL_ME]
- Desired signal (logs/metrics/errors): [FILL_ME]

## Context to load
- Existing logging conventions / logger setup: [FILL_ME]
- Any existing run artifacts under `.codex-autorunner/runs/` (optional)

## Rules
- Prefer structured, minimal, high-signal logs.
- Avoid logging secrets or large payloads.
- Ensure logs/errors help answer: what happened, why, and where.

## Tasks
- [ ] Add/upgrade error messages with actionable context.
- [ ] Add logs at key boundaries (start/end/error) with identifiers.
- [ ] If appropriate, write a small “debug guide” note in `workspace/active_context.md`.

## Verification
- [ ] Trigger the failure path (or a simulated path) and confirm the new signal appears.
- [ ] Run tests/lint: [FILL_ME]

## Definition of done
- [ ] Observability improved in the specified area without noisy spam.
- [ ] Verification passes.
- [ ] Set `done: true`.
