---
agent: opencode
done: false
title: "Review: [FILL_ME] (single-agent)"
goal: "Perform a high-signal review and produce actionable feedback"
---

> Template note: Use after a milestone. This ticket should not introduce new behavior unless explicitly instructed.

## Review target (fill in)
- What to review:
  - [ ] Uncommitted changes
  - [ ] Latest commit: [FILL_ME sha]
  - [ ] Branch diff: [FILL_ME branch/base]
  - [ ] Specific files/paths: [FILL_ME]
- Acceptance criteria to keep in mind (from `workspace/spec.md`): [FILL_ME]

## Context to load
- `.codex-autorunner/workspace/spec.md`
- `.codex-autorunner/workspace/active_context.md` (if present)
- The milestone ticket you are reviewing: [FILL_ME path]

## Review checklist
- [ ] Correctness: does it do what it claims?
- [ ] Tests: adequate coverage; regression added where appropriate
- [ ] Edge cases: input validation, error handling
- [ ] API/UX: naming, ergonomics, backwards compatibility
- [ ] Architecture: respects CAR layering boundaries where relevant
- [ ] Security: avoid secret leakage, unsafe file/network behavior
- [ ] Diff hygiene: minimal unrelated changes

## Output (required)
Write a concise review into this ticket:
- Summary (3–8 bullets)
- Must-fix items (if any)
- Nice-to-haves (optional)
- Any suggested follow-up tickets (optional)

If a must-fix item exists:
- [ ] Create follow-up ticket(s) under `.codex-autorunner/tickets/` (preferred over long inline instructions).

## Definition of done
- [ ] Review notes are specific (file paths, functions, and suggested changes).
- [ ] Follow-up tickets exist for must-fix items (if any).
- [ ] Set `done: true`.
