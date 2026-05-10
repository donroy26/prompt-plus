# AI Planning Workflow

If you've ever handed an AI tool a vague prompt and gotten back a clear-looking output that didn't match what you actually needed, this template is for you. It's a folder structure that forces the planning to happen before the AI starts producing, so the work that comes out reflects what you actually wanted.

The output of this workflow is a brief, not the implementation. Execution happens wherever you want, with whatever tool you want, once the thinking is done.

## Why this exists

A vague prompt gives you vague output. That's true whether you're working in Claude Code, ChatGPT, Cursor, or anywhere else. Iterating on a half-baked idea burns time. The real fix is to separate the planning from the execution. Do the thinking first, write it down, and only then hand it to an executor. The folder structure here is what holds the state between phases so you don't have to keep re-explaining yourself across sessions.

## The three phases

| Phase | Goal | Output |
|---|---|---|
| 1 — Brainstorm | Find the real outcome | One sentence: what done looks like |
| 2 — Plan | Architect the build, name risks | A staged implementation plan |
| 3 — Brief | Compress phases 1+2 into a handoff | A document a fresh worker can execute cold |

Phase 3 is the gate. If you can't compress the brainstorm and plan into a brief that someone with no memory of the prior phases could execute without asking you any questions, then you don't yet understand the outcome. That's actually a useful signal. Go back to phase 2 and keep working until you do.

The brief is the workflow's final output. It doesn't write code or produce content. It produces the document that lets an executor (you, another AI session, a teammate, or future-you) do that work without guessing.

## The AI collaborator

By default, the workflow ships with **Prompt Queen** — a confident, modern persona who runs the planning sessions with you. She's evidence-driven and direct: she'll push back on vague answers in Phase 1 because that's where the planning succeeds or fails. She brings personality without sacrificing precision.

Her voice intensity scales with the phase. Phase 1 is conversational and probing. Phase 2 dials down to architectural focus. Phase 3 (the brief) stays voice-neutral so whoever executes the work can read it cold without translating anyone's personality.

She lives in `_config/persona.md`. To swap her out for a different voice, edit that one file. The phase instructions are persona-agnostic, so changing personas doesn't change how the workflow runs — only how it sounds while running.

## How to use it

1. Copy `_template/` and rename it to something descriptive, like `2026-newsletter-redesign/`.
2. Open the folder in Claude Code, Cursor, ChatGPT projects, or any AI session that can read folder contents.
3. The AI reads `CLAUDE.md` first. That file tells it which phase is active and what its job is.
4. Work through phase 1 with the AI, then write the outcome to `01_brainstorm/output/outcome.md`.
5. Update `CLAUDE.md` to mark phase 2 active, then write the plan to `02_plan/output/implementation-plan.md`.
6. Mark phase 3 active, then compress everything into `03_brief/output/handoff-doc.md`.
7. Hand the brief off to whatever, or whoever, executes it.

Each phase has its own `CONTEXT.md` telling the AI what to do in that phase. The behavior shifts deliberately. Phase 1 is conversational and probing, phase 2 is architectural, and phase 3 is compression. You're not handing the same context to the AI three times. You're moving through stages where the work itself is different.

## An example: launching a new website section

In phase 1, the AI asks what problem the section solves, who it's for, what would make it a failure even if it shipped, and what the smallest version of "done" looks like. The conversation lands somewhere specific, like: "A landing-page section that converts inbound podcast listeners into newsletter subscribers, measured by signups within 30 days of launch."

In phase 2, that outcome gets broken into stages: copy draft, layout design, email-tool integration, deploy, measure. Each stage gets acceptance criteria like "copy passes an 8-second skim test," along with dependencies and named risks like "the design tool may not export cleanly to the CMS." The plan also identifies the gate, which is the single failure mode that means nothing ships.

In phase 3, both of those get compressed into one brief. Scope, the files and systems involved, hard constraints, risks, build order, acceptance criteria, and a stop condition. A freelancer or another AI session can open that brief cold and start work without coming back to you with questions.

## Benefits

A few things have made the upfront effort worth it for me.

The outcome gets specific. Phase 1 doesn't let you out with something like "improve onboarding." It pushes you until the outcome is verifiable, and that specificity carries through the rest of the work.

Risks surface early. Phase 2 forces you to name what could fail at each stage. A risk named in the plan isn't going to ambush the executor later.

The brief itself is a forcing function. If you can't write phase 3 cleanly, the plan is incomplete. That's how you know you're not ready, before you've spent hours building the wrong thing.

State lives on disk. The folder is the memory. A new session can read the folder and know where things stand without you having to recap.

It's tool-agnostic. The whole thing is markdown files and a folder convention. It works in Claude Code, ChatGPT, Cursor, or even a plain text editor with no AI at all.

The shape stays the same across projects. Every project follows the same structure, so picking up someone else's work, or your own from six months ago, takes minutes instead of hours.

## Folder structure

```
_template/
├── CLAUDE.md          # Workflow map, active phase, project state, key decisions
├── STATE.md           # Project name, started date, scope
├── _config/
│   ├── persona.md     # The AI collaborator's voice (default: Prompt Queen)
│   └── constraints.md # Hard and soft project constraints
├── 01_brainstorm/
│   ├── CONTEXT.md     # What the AI does in phase 1
│   └── output/        # outcome.md lives here
├── 02_plan/
│   ├── CONTEXT.md
│   └── output/        # implementation-plan.md lives here
└── 03_brief/
    ├── CONTEXT.md
    └── output/        # handoff-doc.md lives here, the final artifact
```

## Conventions

The numbered folders are phases, in order, and the output of each phase is the input of the next. I'd recommend working through them in sequence. The `_config/` folder holds reference material that applies across phases — the AI persona, hard constraints, and environment details. The `_template/` folder is the blank version, so copy it for each new project rather than editing it directly, unless you're improving the template itself. Each phase has a `CONTEXT.md` for instructions and an `output/` folder for the deliverable. The phase 3 brief is the final output, and implementation happens outside this workflow.

## When this is overkill

Not every task needs this. If you're asking AI to write a quick email or fix a typo, just ask. This workflow is for work that benefits from explicit planning, like features, content series, system designs, or anything where the cost of starting in the wrong direction is real. That being said, you can also adapt it. If you only need phases 1 and 2 for a smaller piece of work, that's fine too. The structure is meant to serve you, not the other way around.
