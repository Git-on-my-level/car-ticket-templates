---
agent: codex
done: false
title: "Spike (timeboxed): [FILL_ME]"
goal: "Answer a specific question with minimal code and a durable write-up"
reasoning: medium
---

> Template note: A spike is not “ship code”. It’s “reduce uncertainty”.

## Timebox
- Limit: [FILL_ME, e.g. 60–120 minutes of work]
- If timebox expires, stop and write findings.

## Spike question (be specific)
- [FILL_ME]

## Context to load
- `.codex-autorunner/workspace/spec.md` (what we’re trying to accomplish)
- Existing design docs / code relevant to the question: [FILL_ME]

## Work
- [ ] Identify 2–3 possible approaches.
- [ ] Prototype the smallest thing needed to validate assumptions (optional).
- [ ] Document findings + recommendation in a durable place.

## Deliverable (required)
Write/update one of:
- `.codex-autorunner/workspace/decisions.md` (preferred for a decision)
- `.codex-autorunner/workspace/active_context.md` (preferred for current state/notes)

Include:
- Options considered
- Pros/cons
- Recommendation
- Follow-up tickets needed (if any)

## Definition of done
- [ ] The question is answered in writing, with a clear recommendation.
- [ ] Any prototype code is either cleaned up or explicitly marked “spike only”.
