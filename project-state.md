# Project state

Last updated: 2026-10-19

## Where things stand
Planning is finished. Two prototypes exist: board-only in `prototype-board/index.html` and battle-only in `prototype-battle/index.html`. The real game (`index.html`) has not been started.

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
| `prototype-battle/index.html` | Temporary battle-only prototype: one battle with health, alien moves, replies, "Next exchange" and "Restart battle". No board. Not the final game. |

## Checkpoints done
1. Added `CLAUDE.md` with the project rules.
2. Added 11 more rules to `CLAUDE.md`.
3. Wrote `game-brief.md` and `game-rules.md`.
4. Pointed `CLAUDE.md` at `game-brief.md`. Created `project-state.md` and `test-report.md`.
5. Confirmed three design choices. Built the board-only prototype. All 16 automated checks passed.
6. You checked the prototype in your browser: B1–B6 passed. B7 (real phone) not tested.
7. Built the battle-only prototype. All 11 automated checks passed.
8. You checked the battle prototype in your browser: C1–C7 passed.

## Confirmed choices
Confirmed on 2026-10-19 (already written into `game-rules.md`):
1. No "Start" button: picking the first cell starts the first battle.
2. No "Continue" button after a battle: the board unlocks straight away.
3. "Restart game" is shown on every screen, including the final result.

## Prototype differences from the final game
- Board prototype: uses "Play again" instead of "Restart game" (shown at all times). No instructions screen, health or alien moves.
- Battle prototype: uses "Restart battle", which restarts one battle only. No board, no X or O. After a battle ends there is nothing to do except restart.

## Next step
Not agreed yet. Suggested: join both prototypes into the real `index.html`, following `game-rules.md` (instructions, board, battles, "Restart game").
