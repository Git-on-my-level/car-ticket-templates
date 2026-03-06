---
title: "<Distill a large problem into shared context docs and minimal child tickets>"
agent: "<strong planning agent>"
done: false
goal: "Turn a broad product, feature, refactor, or system initiative into durable shared context plus the next executable layer of child tickets, without implementing the solution directly."
---

## Parent problem
<Describe the large product / feature / system / refactor / initiative.>

## Desired outcome
<Describe what should be true when this initiative is eventually complete.>

## Constraints
- <Technical constraints>
- <Product / UX constraints>
- <Timeline / sequencing constraints>
- <Compatibility / migration constraints>
- <Other important limits or requirements>

## Relevant inputs
- Code / docs / artifacts to inspect:
  - <path>
  - <path>
  - <path>

## Shared context location
Create or update a scoped shared context folder under `contextspace/<initiative-slug>/`.

Suggested structure:

```text
contextspace/<initiative-slug>/
  overview.md
  spec.md
  decisions.md
  contracts.md
  open-questions.md
  plan.md
````

Use only the files that are actually needed. Do not create empty ceremony.

## Ticket numbering guidance

Reserve an ascending ticket range for this initiative and leave gaps for likely follow-up tickets.

## Execution mode

This is a planning and decomposition ticket, not an implementation ticket.

Do not implement the product or feature itself from this ticket unless a tiny non-production artifact update is needed to clarify the plan. The primary output is:

1. shared context docs in `contextspace/<initiative-slug>/`
2. child tickets in `.codex-autorunner/tickets/`
3. explicit lineage, scope, and dependency structure

## Lineage and context model

Treat parent/child as durable planning lineage, not hidden chat memory.

* The parent problem is the broader scope this ticket is distilling.
* Shared initiative-wide context should live in `contextspace/<initiative-slug>/`.
* Child tickets should reference the relevant shared context docs instead of repeating the full parent problem.
* Child tickets must still contain enough local context to run independently.
* Do not assume hidden runtime state is required to understand a child ticket.

Use this rule:

* If multiple sibling tickets need to know it, put it in `contextspace/<initiative-slug>/`.
* If only one ticket needs it to execute, put it in that ticket.

## Working method

### Phase 1 — Inspect and classify the scope

* Inspect the relevant codebase, docs, and artifacts first.
* Decide whether the current scope is already **atomic** or still **composite**.
* Treat the scope as **atomic** if a capable agent could complete it in one bounded implementation cycle with concrete files, deliverables, and testable acceptance criteria.
* Treat the scope as **composite** only if it clearly contains multiple independent concerns, surfaces, deliverables, or unresolved architecture decisions.
* When uncertain, prefer less decomposition over more decomposition.

### Phase 2 — Write shared context

Create or update the minimum useful set of shared context docs under `contextspace/<initiative-slug>/`.

Use these as needed:

* `overview.md` for problem framing and scope
* `spec.md` for target behavior and requirements
* `decisions.md` for key design choices and rationale
* `contracts.md` for interfaces, schemas, APIs, data contracts, or invariants
* `open-questions.md` for unresolved issues that need explicit handling
* `plan.md` for sequencing, milestones, and dependency structure

The shared context should capture information that would otherwise be repeated across multiple tickets.

### Phase 3 — Distill one level down

* Create the minimum number of child tickets needed.
* If the scope is already atomic, create exactly one leaf execution ticket and stop.
* If a child is still too broad, ambiguous, or cross-cutting, make that child another distillation ticket.
* If a child is concrete and bounded, make it a leaf execution ticket.
* Prefer the minimum viable child set. Do not split for elegance alone.

### Phase 4 — Separate planning from final validation

* This parent distillation ticket should finish once shared context and child tickets are created.
* Do not keep the parent distillation ticket open while children execute.
* If end-to-end validation is needed, create a separate final integration / review ticket near the end of the sequence.

## Decomposition rules

* One primary intent per child ticket.
* Sibling tickets should be minimally overlapping and collectively cover the parent scope.
* Preserve lineage explicitly.
* Every child ticket must state which shared context docs it depends on.
* Every child ticket must define its local ownership boundary.
* No child ticket may depend on a higher-numbered ticket.
* Stop decomposing when each remaining child can proceed without another major architecture decision.
* Do not create filler tickets such as vague polish / cleanup / follow-up tasks unless they are real standalone work items.

## Required outputs

### 1) Shared context docs

Create or update the relevant files under `contextspace/<initiative-slug>/`.

Across the shared docs, capture the initiative’s:

* problem statement
* goals
* non-goals
* constraints
* major boundaries / surfaces / subsystems
* interfaces or contracts, where relevant
* key design decisions
* open questions
* sequencing / milestone notes
* success criteria

### 2) Child tickets

Create child tickets in ascending numeric order under `.codex-autorunner/tickets/`.

Each child ticket must include:

#### Parent lineage

* Parent problem: <short name>
* Shared context docs to read first:

  * `contextspace/<initiative-slug>/<file>.md`
  * `contextspace/<initiative-slug>/<file>.md`

#### Scope of this ticket

* State exactly what this ticket owns.
* State what it explicitly does not own, if useful for avoiding overlap.

#### Tasks

* Provide a concrete task list for this ticket only.

#### Acceptance criteria

* Make completion observable and specific.

#### Tests / verification

* Include explicit checks, validation steps, or test expectations.

#### Dependency notes

* Call out prerequisites or ordering dependencies explicitly.

Choose for each child whether it is:

* a **distillation** ticket, or
* a **leaf execution** ticket

### 3) Final summary

At the end of this ticket, provide a concise summary listing:

* shared context docs created or updated
* child tickets created, in order
* which tickets are distillation tickets vs leaf execution tickets
* whether a final integration / review ticket was created
* unresolved questions isolated into explicit follow-up tickets

## Child ticket quality bar

A child ticket is only acceptable if:

* it has one clear objective
* it references the relevant shared context docs
* it contains enough local context to execute without hidden chat history
* it has explicit acceptance criteria
* it has concrete tests / verification
* it does not significantly overlap with sibling tickets

A child ticket is a valid **leaf** only when:

* the relevant files / modules / artifacts are reasonably identifiable
* the work can be completed in one bounded implementation cycle
* the acceptance criteria are concrete
* no further major architecture decomposition is needed

## Anti-patterns to avoid

* Do not implement the actual feature from this ticket.
* Do not repeat the full parent problem in every child ticket.
* Do not put ticket-specific execution details into `contextspace/<initiative-slug>/` unless multiple tickets truly need them.
* Do not rely on hidden chat context.
* Do not keep the parent ticket open as a blocker while children run.
* Do not create overlapping sibling tickets.
* Do not decompose endlessly for neatness.
* Do not create vague tickets like "finish feature" or "clean things up."

## Acceptance criteria

* A scoped shared context folder exists under `contextspace/<initiative-slug>/` with the minimum useful set of docs.
* Shared information needed across multiple child tickets lives in `contextspace/<initiative-slug>/` instead of being duplicated.
* The next layer of tickets exists in correct ascending order.
* Each child ticket references the relevant shared context docs and contains enough local execution context.
* Further distillation is used only where a child is still composite.
* Leaf tickets are concrete, bounded, and verifiable.
* Any final integration or review need is handled by a separate ticket, not by keeping this parent ticket open.

## Tests

* Verify every child ticket can be understood from its own body plus the referenced `contextspace/<initiative-slug>/` docs.
* Verify no child ticket depends on a higher-numbered ticket.
* Verify shared information used by multiple siblings was placed in `contextspace/<initiative-slug>/`.
* Verify ticket-specific execution details were kept in the child tickets.
* Verify each child ticket has frontmatter, tasks, acceptance criteria, and tests.
* Verify the decomposition uses the minimum necessary number of child tickets.
* Verify any remaining broad or cross-cutting child became another distillation ticket rather than a vague implementation ticket.
