# Project state

Last updated: 2026-10-19

## Where things stand
Planning is finished. A board-only prototype exists in `prototype-board/index.html`. The real game (`index.html`) has not been started.

- Repo: `ehawk61/alien-tic-tac-toe-ai`
- Working branch: `claude/charming-hypatia-zrpaus`
- No pull request open.

## Files
| File | Purpose |
|---|---|
| `CLAUDE.md` | Rules for how Claude works on this project. |
| `game-brief.md` | One-page summary of the game and its scope. |
| `game-rules.md` | Exact rules, screen states, keyboard and touch behavior, completion checks. |
| `project-state.md` | This file: where the project is and what comes next. |
| `test-report.md` | Result of every completion check: Passed, Failed or Not tested. |
| `prototype-board/index.html` | Temporary board-only prototype. Battles are replaced by "Test battle win" and "Test battle loss" buttons. Not the final game. |

## Checkpoints done
1. Added `CLAUDE.md` with the project rules.
2. Added 11 more rules to `CLAUDE.md`.
3. Wrote `game-brief.md` and `game-rules.md`.
4. Pointed `CLAUDE.md` at `game-brief.md`. Created `project-state.md` and `test-report.md`.
5. Confirmed three design choices. Built the board-only prototype. All 16 automated checks passed; your browser checks are still to do.

## Confirmed choices
Confirmed on 2026-10-19 (already written into `game-rules.md`):
1. No "Start" button: picking the first cell starts the first battle.
2. No "Continue" button after a battle: the board unlocks straight away.
3. "Restart game" is shown on every screen, including the final result.

## Prototype differences from the final game
- Uses "Play again" instead of "Restart game". It is shown at all times.
- Has no instructions screen, health or alien moves yet.

## Next step
You check the prototype in your browser (steps in `test-report.md`). After that, not agreed yet. A likely next step is a battle-only prototype.
