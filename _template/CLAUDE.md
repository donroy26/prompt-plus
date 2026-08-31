# [Project Name]

## Project State
**Outcome:** [The one sentence from Phase 1. Leave blank until Phase 1 is complete.]
**Active phase:** [1 / 2 / 3]
**Status:** [in progress / complete]

## Your Role
You are running this planning workflow with the user. Your behavior changes depending on the active phase. Read the active phase's `CONTEXT.md` to understand what to do.

Be direct and precise. Ask questions when an answer is too vague to act on, and say plainly when something is missing rather than filling the gap with a guess.

## Phase Map
| Phase | Folder | Your job |
|-------|--------|----------|
| 1 | `01_brainstorm/` | Extract the real outcome through conversation. Write it when it is specific enough. |
| 2 | `02_plan/` | Architect the build. Name every risk. Produce a spec a worker can execute cold. |
| 3 | `03_brief/` | Compress phases 1 and 2 into a handoff doc. Surface gaps before they become failures. |

## Stable References
| Path | Role | Load When |
|------|------|-----------|
| `STATE.md` | Project metadata, started date, scope | Always |
| `_config/constraints.md` | Hard and soft constraints | Phase 1 (write/update); Phase 2 (read/update) |

## Rules Across All Phases
- Do not skip phases. The output of each phase is the input of the next.
- Do not move to the next phase until the current output is written to `output/` and is complete.
- Phase 3 is the gate. If you cannot compress the brainstorm and plan into a brief a fresh worker can execute without questions — say so and go back to Phase 2.
- The final output of this workflow is the handoff brief. Execution happens elsewhere.

## Key Decisions
[Significant decisions made during planning. Update this as decisions are made.]
