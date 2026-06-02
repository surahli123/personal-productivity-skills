# Using Agent Skills

Pick the right workflow skill before starting agent work.

This skill helps an agent pause just long enough to choose the smallest useful workflow for the current phase: clarify, shape, specify, implement, debug, test, review, document, or wrap up.

It is a routing skill, not a universal process. It should make the next action clearer, not add ceremony.

## When To Use It

Use `using-agent-skills` when:

- the task could fit several skills
- the work is non-trivial and the right workflow is unclear
- a session is starting from a handoff
- you want the agent to name its workflow before editing
- you are packaging or reviewing other skills

Skip it for one-line edits, direct shell lookups, or simple factual answers.

## What It Does

The skill asks the agent to:

1. identify the current task phase
2. choose one primary workflow skill
3. add a secondary skill only when it affects the current work
4. execute the selected workflow
5. verify the result before claiming completion

## Routing Map

| Current Task | Use |
| --- | --- |
| unclear request or missing boundary | an interview or requirements skill |
| rough idea that needs shaping | an idea refinement skill |
| new feature or meaningful change | a spec or goal-contract skill |
| approved plan ready for code | an incremental implementation skill |
| failing behavior | a debugging skill |
| tests or proof are the main need | a test-driven or verification skill |
| code review requested | a code review skill |
| handoff, closeout, or durable notes | a documentation or session-wrapup skill |

## Example

```text
User: Continue from this handoff and proceed.

Agent:
Selected path: using-agent-skills -> session-wrapup/git workflow.
Reason: the handoff says to inspect PR state before deciding whether to edit the open PR or start a new branch.
Next action: check PR state and local branch status, then follow the branch action in the handoff.
```

## Good For

- preventing workflow drift
- making handoff sessions start cleanly
- keeping bounded work from turning into broad cleanup
- choosing between implementation, debugging, testing, review, and documentation paths

## Not For

- replacing the selected skill's actual workflow
- making every task multi-step
- avoiding a necessary user question
- deciding product strategy without project evidence

## Attribution

This public package is adapted from a local personal workflow note named `using-agent-skills`. No private configuration, secrets, or installed skill files are included.

See [`NOTICE.md`](NOTICE.md) for the reuse boundary.
