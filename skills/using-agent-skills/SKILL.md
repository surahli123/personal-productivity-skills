---
name: using-agent-skills
description: Choose the right agent workflow skill before starting a task, especially when several skills could apply or the task phase is unclear.
---

# Using Agent Skills

Use this skill at the start of non-trivial agent work to route the task to the smallest workflow that can finish it well.

The point is not to activate every relevant skill. The point is to pick the next useful workflow, follow it, verify the result, and stop before drifting into adjacent work.

## Workflow

1. Identify the task phase.
2. Pick one primary skill for the current phase.
3. Add a secondary skill only when it changes the work you will do now.
4. State the chosen skill path briefly.
5. Execute the selected workflow.
6. Verify with the evidence that matches the task.
7. Report the outcome, verification, and any remaining risk.

## Skill Routing

```text
Task arrives
    |
    +-- unclear intent or missing boundaries
    |       -> interview / requirements clarification skill
    |
    +-- rough idea, needs shaping
    |       -> idea refinement skill
    |
    +-- new feature or meaningful change
    |       -> spec / goal contract skill
    |
    +-- approved plan, needs implementation
    |       -> incremental implementation skill
    |
    +-- tests or verification are the main work
    |       -> test-driven or verification skill
    |
    +-- failing behavior or production symptom
    |       -> debugging skill
    |
    +-- review requested
    |       -> code review / quality skill
    |
    +-- docs, handoff, or decision record
            -> documentation / session wrapup skill
```

## Operating Rules

- Prefer one primary skill over a long chain.
- Ask only when missing information materially changes the outcome or creates risk.
- Keep scope tied to the user's named phase, slice, or artifact.
- Prefer existing project patterns over new abstractions.
- Treat verification as part of the task, not a follow-up.
- Stop when the selected workflow is complete and verified.

## Common Pairings

Use these pairings when the task genuinely crosses phases:

| Situation | Primary | Secondary |
| --- | --- | --- |
| Vague request that should become executable | goal contract | requirements clarification |
| Code change with uncertain behavior | incremental implementation | test-driven development |
| Bug with unclear root cause | debugging | test-driven development |
| Public skill or documentation package | documentation | code review |
| End-of-session handoff | session wrapup | git workflow |

## Failure Modes

Avoid these patterns:

- invoking a skill because its name is familiar rather than because the task needs it
- chaining many skills before doing the first useful step
- widening a bounded task into a general improvement pass
- skipping verification because the chosen skill was "just process"
- treating skill routing as a substitute for reading the relevant files

## Output

When you use this skill, report:

- selected skill path
- why that path fits the current task
- verification evidence
- any next skill that should run later, if it stayed out of scope now
