# prompt-plus — Phase 2: Implementation Plan

## Your Job
Architect the build. Take the outcome from Phase 1 and break it into stages with clear acceptance criteria, dependencies, and named risks. Produce a plan specific enough that a fresh worker could execute any stage without asking for clarification.

Read `../01_brainstorm/output/outcome.md` before doing anything else. That is your input. Also read `../_config/constraints.md` to inherit hard constraints; update it if Phase 2 reveals new ones.

## How to Run This Phase

Work through these with the user:

**Stages:** What are the discrete pieces of work? What does each one produce? What must exist before it can start?

**Acceptance criteria:** For each stage — how do you know it is done? Make this verifiable, not subjective.

**Risks:** What could go wrong at each stage? What would fail silently? What is the one failure that means nothing ships? Name these explicitly. A risk named in the plan does not ambush the executor.

**Build order:** What is the correct sequence? Which things can run in parallel? Which have hard dependencies?

**The gate:** What is the single condition that, if failed, means the project does not ship regardless of what else is complete?

If the user cannot answer a question, that is a gap in the plan. Surface it now — gaps in the plan become failures at execution.

## When Phase 2 Is Done

Every stage has: a name, what it produces, what it depends on, acceptance criteria, and at least one named risk. You can describe the build order. You know the gate.

Ask yourself: could a worker open this plan and execute any given stage without asking you a single question about scope? If no, keep going.

## Output

Write `output/implementation-plan.md` with this structure:

```
## Outcome
[Copy from Phase 1 output — the one sentence.]

## Stages

### Stage [N]: [Name]
**Produces:** [what this stage outputs]
**Depends on:** [what must exist first, or "nothing"]
**Acceptance criteria:**
- [ ] [verifiable criterion]
**Risk:** [what could go wrong, and the signal that it has]

## Build Order
1. [Stage N] — [why it comes first]
2. [Stage N+1] — [dependency]

## Hard Constraints
- [Non-negotiable constraints]

## Risks Register
- **[Risk]:** [why it matters] — [mitigation or stop condition]

## The Gate
[One sentence. The condition that means nothing ships.]
```

After writing, update Active phase to 3 in `CLAUDE.md`. Delete `output/_here.md`.
