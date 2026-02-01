---
agent: codex
done: false
title: "Open PR (agent-assisted): [FILL_ME]"
goal: "Prepare PR-ready branch and either open PR (if automation exists) or hand off cleanly"
reasoning: medium
---

> Template note: Use when you want the agent to do as much as possible, but avoid credential guessing.

## Inputs (fill in)
- Base branch: [FILL_ME, e.g. main]
- Head branch: [FILL_ME]
- Repo remote: [OPTIONAL]
- Tickets included:
  - [FILL_ME]

## Work
- [ ] Ensure working tree is clean and commits are in a good state.
- [ ] Run verification:
  - [ ] [FILL_ME commands]
- [ ] Draft PR title and description (see below).

## PR title
[FILL_ME]

## PR description (draft)
### What
- [FILL_ME]

### Why
- [FILL_ME]

### How tested
- [FILL_ME]

### Risk / rollout
- [FILL_ME]

### Tickets
- [FILL_ME]

## Opening the PR
- If CAR/GitHub automation is available in this workspace, open the PR and record the PR URL in `workspace/active_context.md`.
- If automation is **not** available, create a `DISPATCH.md` with `mode: pause` that includes:
  - PR title + description draft
  - exact branch names
  - verification commands run + results
  - request the user to open the PR

## Definition of done
- [ ] Either PR is opened (URL recorded) OR a pause dispatch hands off everything needed to open it.
- [ ] Set `done: true`.
