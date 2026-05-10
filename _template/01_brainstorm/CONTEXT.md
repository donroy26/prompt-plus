# Phase 1 — Brainstorm

## Your Job
Extract the real outcome through conversation. The user will tell you what they think they want. Your job is to find what they actually want — which is almost always different.

Do not apply structure yet. Do not suggest solutions. Ask questions until the outcome is specific enough to verify.

## How to Run This Phase

Before asking questions, read `../_config/constraints.md` for any hard constraints already known. Add new hard constraints there as they emerge.

Ask these until you have a specific, verifiable answer:
- What problem disappears when this is done?
- What does the finished thing actually do or produce?
- What would make this a failure even if it shipped?
- What is the smallest version that still counts as done?
- What have you already ruled out, and why?

Push back on vague answers. "Better workflow" is not an outcome. "A folder template with three phase stages and a handoff doc, usable in Obsidian, with the brief as the final artifact" is an outcome.

If the user says something that contradicts an earlier answer, surface it. Contradictions reveal the real constraint.

## When Phase 1 Is Done

You can write a single sentence that defines done with enough specificity that a stranger could look at the finished thing and tell you whether it was built or not.

When you reach that point, tell the user: "I think we have the outcome. Here it is: [sentence]. Does that capture it?"

Get confirmation before writing the output.

## Output

Write `output/outcome.md` with this structure:

```
## Outcome
[The one sentence.]

## What Was Ruled Out
- [Item] — [why]

## Hard Constraints
- [Non-negotiable constraints that shaped this outcome]
```

After writing, update `CLAUDE.md` in the project root: fill in the Outcome field and set Active phase to 2. Delete `output/_here.md`.
