## How to work in this repo

- Plan before editing: outline the approach and surface tradeoffs first. Do not hide confusion behind a confident edit.
- Simplicity first: smallest change that works, no premature abstraction (YAGNI).
- Surgical changes only: touch only what the task names; don't refactor unrelated code.
- State the goal and the definition of done up front; loop until verified against it.
- Ask when the spec is ambiguous; do not guess and ship the guess as fact.
- Stay in scope: no drive-by edits to neighboring code just because you're in the file.
- Tests are truth: run tests and they must pass before you claim done.
- Be concise: short answers, no recap of work you just did unless asked.

## Stack

- The shared stack and the conventions are in `plan.md` (sections 1.2 and 1.6) in the `general` repository. Do not repeat them here.
- Add here only what the plan does not say: the Go version, the libraries chosen in this repository, and the build tooling.
- Prefer the repo's existing libraries over reaching for a new dependency.
- Don't infer the build tooling or the module layout. Read the repo.

## What burned us before

<!-- Guide for the agent: nothing is recorded yet. Do not add anything here on your own and do not invent incidents.
     When the user tells you to add an entry, write one short line: what went wrong, and the check that would have caught it.
     Example of the shape (not a real incident): "A job reported success while some records were skipped. Verify counts after bulk operations." -->

## Keep this file honest

- When you get corrected, add the lesson to this file (update CLAUDE.md) so the next session starts ahead.

## Purpose and place

This repository is the `challenge` service (the short name from section 1.3 of the plan). Internal logic: TBD. Add the link to the `challenge` part of section 2.1 of the plan here once that section is written.

## Link to `general`

The plan lives in the [`general`](https://github.com/rso-project-team-14/general) repository (`rso-project-team-14/general`). `plan.md` there is the source of truth.

## Documents from `general` this repository depends on

These files in the `general` repository (`rso-project-team-14/general`, branch `main`) describe what this repository implements. Each one has a content hash on line 3. "Last read hash" is the hash from the last time the file was read in full.

| File | Link | Last read hash |
|---|---|---|
| `plan.md` | `https://github.com/rso-project-team-14/general/blob/main/plan.md` | `23e237c0af42cecb5f290d9ba240c572279362ba0a5a3bd613c868d92cf468ea` |
| `api/challenge.md` | `https://github.com/rso-project-team-14/general/blob/main/api/challenge.md` | _none yet_ |
| `docs/stages/stage-1-demo.md` | `https://github.com/rso-project-team-14/general/blob/main/docs/stages/stage-1-demo.md` | _none yet_ |

Before implementing a feature, check each file in the table:
1. Read only line 3 of the file. For example: `curl -s https://raw.githubusercontent.com/rso-project-team-14/general/main/plan.md | sed -n 3p`. It looks like `<!-- sha256: ... -->`.
2. If the hash is the same as "Last read hash", the file did not change. Do not re-read it.
3. If it is different, or the recorded hash is `none yet`, read the whole file and apply the changes that concern this repository. Then write the new hash into the table.

The `changelog/` directory in `general` is a historical record for people. Do not use it to detect changes. Read an entry only when you need to understand why something was changed.

## Repository specifics

Only what the plan does not say. If this repository has to differ from the plan, record the deviation here and report it as a change in `general`.

- **Go version, libraries, build tooling:** TBD. Nothing is chosen yet.
- **Internal layout:** the Go service structure from section 1.4 of the plan. No additions yet.
- **Deviations from the conventions in 1.6:** none yet.
- **Implementation choices for the events (1.7) and data rules (1.8):** none yet. How this service applies the startup database setup of 1.8, and whether it uses `migrations/`, is TBD.

## Commands

TBD until local development (section 1.5 of the plan) is decided. Only commands beyond the Makefile targets of section 1.4 go here, for example how to lint and how to run the service.

## Rules for Claude

- Stay within this service's responsibility.
- Do not resolve an open decision from 1.12 silently. Raise it as an issue or a change in `general`.
- If the plan looks wrong or contradicts the code, say so instead of quietly diverging from it.
- Never commit secrets.
