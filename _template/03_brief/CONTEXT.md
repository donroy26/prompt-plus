# Phase 3 — Handoff Brief

## Your Job
Compress phases 1 and 2 into a single document a fresh worker can open cold and execute against — no memory of previous phases, no questions needed.

Read both inputs before writing anything:
- `../01_brainstorm/output/outcome.md`
- `../02_plan/output/implementation-plan.md`

## What the Brief Must Encode

Every handoff doc encodes two layers. Both must be present or the worker is guessing:

**Intent** — what done looks like. One sentence. From Phase 1.
**Context** — files, systems, constraints, risks, build order. From Phase 2.

## How to Write the Brief

Compress, do not summarize. The brief should contain everything the worker needs and nothing they do not. If a detail was in the plan but a worker does not need it to execute — leave it out. If a constraint is load-bearing — it must be in the brief.

As you write, run this check on every section: "Could a worker act on this without asking me anything?" If not, either add what is missing or remove the ambiguity.

## When the Brief Is Not Ready

If you reach a section and cannot write it cleanly without hedging or leaving gaps — the plan is incomplete. Stop. Tell the user which part of Phase 2 needs more work before you can finish the brief. Do not write a partial brief and call it done.

## When Phase 3 Is Done

A fresh worker with no prior context can open `output/handoff-doc.md` and answer all of these without asking you anything:
- What am I building?
- What does done look like?
- What files or systems am I working in?
- What are the acceptance criteria?
- What should make me stop and surface to the human?

## Output

Write `output/handoff-doc.md` with this structure:

```
# [Project Name] — Handoff Brief

## Intent
[One sentence: what done looks like. Specific enough to verify.]

## Scope
In scope: [list]
Out of scope: [list]

## Context

### Files and Systems
- [path or system]: [what it is and what the worker needs to know]

### Constraints
- [Hard constraint the worker must not violate]

### Risks
- [Risk]: [what to watch for and what to do if it happens]

## Build Order
1. [Stage 1] — produces [output]
2. [Stage 2] — depends on Stage 1 output

## Acceptance Criteria
- [ ] [Verifiable criterion]

## Stop Condition
Stop and surface to the user if: [the one condition that requires human judgment]
```

Delete `output/_here.md` after `handoff-doc.md` is written.

The brief is the final output of this workflow. Hand it off to whichever environment will execute the work.
