# Project state

Last updated: 2026-10-19

## Where things stand
The full game is built in `index.html`. All 28 completion checks passed in Claude's automated test, and your browser checks G1–G8 passed. G9 (real phone) is not tested. The two prototype folders are kept as separate test files.

- Repo: `ehawk61/alien-tic-tac-toe-ai`
- Working branch: `claude/charming-hypatia-zrpaus`
- No pull request open.

## Files
| File | Purpose |
|---|---|
| `index.html` | The game. |
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
9. Built the full game in `index.html` from `game-rules.md`. All 28 completion checks passed (automated).
10. You checked the game in your browser: G1–G8 passed. G9 (real phone) not tested.

## Confirmed choices
Confirmed on 2026-10-19 (already written into `game-rules.md`):
1. No "Start" button: picking the first cell starts the first battle.
2. No "Continue" button after a battle: the board unlocks straight away.
3. "Restart game" is shown on every screen, including the final result.

## Prototype differences from the final game
- Board prototype: uses "Play again" instead of "Restart game" (shown at all times). No instructions screen, health or alien moves.
- Battle prototype: uses "Restart battle", which restarts one battle only. No board, no X or O. After a battle ends there is nothing to do except restart.

## Next step
Not agreed yet. Waiting on your decision about the two open items below.

## Open items
- Completion check 13 in `game-rules.md` says "three correct replies in a row", but two already win a battle (the alien has 2 health). The wording needs a fix.
- On a phone the first screen needs scrolling down to reach the bottom of the board and "Restart game". It's allowed by the rules (no sideways scrolling), but it could be tightened.
