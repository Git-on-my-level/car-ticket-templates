---
agent: <strong planning model>
done: false
title: "Refactor: [FILL_ME theme] contraction loop"
goal: "Generate a recursive seam-by-seam refactor ticket chain that converges on canonical contracts without guessing through compatibility risks"
---

> Template note: Use this when a refactor should expand into a sequence of CAR tickets rather than a single broad cleanup ticket.

## Applicability gate
Use this template only when the goal is to consolidate multiple live contracts that currently represent the same behavior, workflow, or persisted state across different paths, wrappers, aliases, schemas, helpers, or entrypoints.

Do not use this template for:
- pure formatting, linting, or stylistic cleanup
- broad dead-code sweeps without a clear canonicalization seam
- drive-by renames or file moves with no contract consolidation
- unrelated modernization bundled into one generic cleanup effort
- bugfix-only work where there is no overlapping-contract seam to collapse

If the input goal is a vague "cleanup" request, first determine whether there is at least one concrete seam with competing live contracts and real user, runtime, or persisted-data impact. If not, do not force this template onto the work.

## Input
- Refactor theme: `[FILL_ME]`
- Source context to ground the chain:
  - PR / issue / design doc / user discussion: `[FILL_ME]`
  - Key paths / modules / surfaces: `[FILL_ME]`
  - Known compatibility or migration concerns: `[FILL_ME]`

## Context to load
- Read the source context above.
- Inspect the relevant codepaths, persisted artifacts, and user-visible surfaces before writing tickets.
- Confirm how many distinct seams exist, but keep each generated implementation ticket scoped to exactly one seam.

## Your Task
- Convert the refactor into a contraction loop, not a generic cleanup plan.
- Choose one seam where multiple contracts coexist.
- Define the canonical contract for that seam.
- Canonicalize new writes and primary entrypoints first.
- Migrate only the callers needed for that seam.
- Remove shims, wrappers, aliases, or compatibility code only when they are proven dead.
- Surface uncertain persisted-data or external-caller compatibility questions explicitly instead of guessing them away.
- Write a recursive CAR ticket chain with numeric gaps and a final user-owned decision ticket.

## Required outputs
Create the following ticket files under `.codex-autorunner/tickets/`:

1. `TICKET-001-[FILL_ME refactor-theme]-bootstrap.md`
2. `TICKET-010-[FILL_ME seam-slug].md`
3. Additional recursive seam tickets as needed: `TICKET-020-...`, `TICKET-030-...`, `TICKET-040-...`
4. `TICKET-800-[FILL_ME refactor-theme]-convergence.md`
5. `TICKET-900-[FILL_ME refactor-theme]-user-review.md`

## Chain rules
- One ticket = one seam.
- Canonicalize writes and primary entrypoints before deleting readers.
- Do not remove legacy persisted-data handling on assumption alone.
- Every implementation ticket must create the next ticket or the convergence ticket before it is done.
- Every uncertainty goes into `TICKET-900`, not into silent code guesses.

## Ticket templates to emit

### `TICKET-001-[FILL_ME refactor-theme]-bootstrap.md`

```md
---
title: "[FILL_ME Refactor theme]: bootstrap canonicalization loop"
agent: "codex"
done: false
goal: "Identify the first concrete seam to canonicalize, seed the next agent ticket with self-contained context, and seed the final user review ticket."
---

## Tasks
- Inspect the repo for one refactor seam where multiple paths, aliases, wrappers, schemas, or helper contracts currently represent the same behavior or persisted state.
- Prioritize seams that affect:
  - persisted artifacts or stored records
  - user-visible workflows
  - multiple control surfaces or integrations
- Pick exactly one seam for the next ticket. Do not perform the full refactor in this bootstrap ticket.
- Write `TICKET-010-[FILL_ME seam-slug].md` as a self-contained implementation ticket that includes:
  - the current competing contracts
  - the desired canonical contract
  - the concrete files/modules/surfaces likely involved
  - the real behaviors that must not regress
  - the persisted artifacts or external callers that may still depend on legacy behavior
  - the focused tests and smoke checks to run
- Write `TICKET-900-[FILL_ME refactor-theme]-user-review.md` as the final user-owned decision ticket.
- Copy forward every fact the next agent needs. Do not rely on this ticket, earlier tickets, or chat history being available later.

## Acceptance criteria
- `TICKET-010-[FILL_ME seam-slug].md` exists and scopes exactly one seam.
- `TICKET-900-[FILL_ME refactor-theme]-user-review.md` exists with an `Open questions` section.
- The next ticket is understandable on its own and explicitly names the behaviors and legacy compatibility risks that matter.
- No broad refactor code changes were made here beyond minimal characterization scaffolding if strictly needed.

## Tests
- Verify both new ticket files exist and have valid frontmatter.
- If minimal characterization coverage was added here, run only that focused check and record the result in `TICKET-010-[FILL_ME seam-slug].md`.
```

### `TICKET-010-[FILL_ME seam-slug].md`

Reuse this template verbatim for `020`, `030`, `040`, and later. Only the seam scope, files, and verification steps should change.

```md
---
title: "[FILL_ME Refactor theme]: canonicalize [FILL_ME seam slug]"
agent: "codex"
done: false
goal: "Replace one cluster of overlapping contracts with a single canonical contract without regressing real behavior, then bootstrap the next ticket."
---

## Tasks
- Restate the seam at the top of this ticket before changing code:
  - current competing contracts:
  - desired canonical contract:
  - real user-visible flows:
  - persisted/runtime artifacts that may still contain legacy data:
- Add or tighten characterization coverage for the seam before deleting adapters, where practical.
- Introduce or extract the canonical helper, path, schema, type, or entrypoint for this seam.
- Migrate only the callers needed for this seam to use the canonical contract.
- Treat new writes and primary entrypoints as canonical first.
- Do not remove legacy readers or compatibility layers for persisted artifacts unless at least one of these is true:
  - there is migration evidence that old data is gone or converted
  - there is strong proof no external caller still depends on the old contract
  - the uncertainty has been explicitly deferred to the user ticket and the code keeps a safe compatibility fallback
- Remove wrappers, aliases, or shims only when they are proven dead for this seam.
- Update docs, comments, prompts, and tests touched by this seam so they describe the canonical contract only, unless compatibility behavior is intentionally retained.
- Do not widen scope to adjacent seams just because they are nearby. Create the next ticket instead.
- Before closing this ticket:
  - if another seam remains, write the next numbered ticket (`TICKET-020-...`, `TICKET-030-...`, etc.) using this same structure, but with explicit scope
  - if no seam remains, write `TICKET-800-[FILL_ME refactor-theme]-convergence.md`
  - append every unresolved compatibility question, migration doubt, or “probably safe but not proven” item to `TICKET-900-[FILL_ME refactor-theme]-user-review.md`

## Acceptance criteria
- Exactly one canonical contract for this seam is now the default path for all changed code.
- At least one representative user-visible workflow for this seam was re-verified.
- Any retained compatibility layer is explicitly named and justified.
- Any removed compatibility layer is backed by search evidence, tests, migration proof, or equivalent strong evidence.
- A self-contained follow-up ticket or convergence ticket exists before this ticket is marked done.

## Tests
- [FILL_ME focused tests for this seam]
- [FILL_ME one representative smoke path that exercises the seam the way a real user or automation would]
- [FILL_ME broader repo checks appropriate to the touched surfaces]
```

### `TICKET-800-[FILL_ME refactor-theme]-convergence.md`

```md
---
title: "[FILL_ME Refactor theme]: convergence cleanup and parity proof"
agent: "codex"
done: false
goal: "Prove the staged refactor has converged, remove only the leftovers that are now safe to delete, and hand remaining decisions to the user."
---

## Tasks
- Confirm there are no remaining in-scope seams where multiple live contracts still compete without an explicit reason.
- Remove only globally dead leftovers that became safe to delete after prior seam tickets completed.
- Re-run broad verification across all touched surfaces.
- Update docs, comments, templates, and operational notes to describe only the surviving canonical contracts.
- Finalize `TICKET-900-[FILL_ME refactor-theme]-user-review.md` with:
  - each unresolved item
  - evidence
  - blast radius
  - recommended action
  - whether more agent work should continue only after user approval
- If a new seam is discovered that is too large or risky to absorb here, create the next numbered implementation ticket instead of silently widening this ticket.

## Acceptance criteria
- No known in-scope seam still has multiple live contracts without an explicit reason.
- Broad regression evidence has been recorded.
- Remaining uncertainty lives only in the user review ticket.
- If more work remains, a new agent ticket exists and this ticket is not marked done.

## Tests
- [FILL_ME full lint/type/test/build commands for this repo]
- [FILL_ME at least one smoke path per touched user-facing surface]
```

### `TICKET-900-[FILL_ME refactor-theme]-user-review.md`

```md
---
title: "[FILL_ME Refactor theme]: user review for unresolved decisions"
agent: "user"
done: false
goal: "Let the user decide which unresolved compatibility, migration, or cleanup questions should continue or stop."
---

## Summary
- [FILL_ME one-paragraph status summary of the refactor chain and what is already complete.]

## Open questions
- [ ] [FILL_ME Question 1]
  - Evidence:
  - Risk if changed or removed:
  - Cost of keeping compatibility:
  - Recommended action:
  - Next ticket if approved:
- [ ] [FILL_ME Question 2]
  - Evidence:
  - Risk if changed or removed:
  - Cost of keeping compatibility:
  - Recommended action:
  - Next ticket if approved:

## Acceptance criteria
- Every unresolved item is concrete, evidence-backed, and understandable without rereading the full refactor history.
- The user can decide continue / stop / defer for each item.

## Tests
- N/A
```

## Definition of done
- [ ] The generated chain starts with a bootstrap ticket, expands seam-by-seam, and ends with a user review ticket.
- [ ] Each implementation ticket is self-contained and scoped to exactly one seam.
- [ ] Compatibility uncertainty is surfaced explicitly instead of being resolved by assumption.
- [ ] The convergence ticket exists only when no further seam ticket should be created first.
