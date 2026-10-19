# Game brief: Alien Tic-Tac-Toe

## What it is
A one-player tic-tac-toe game in the browser. You never play against a computer opponent placing its own marks. Instead, every square you pick starts a short battle against an alien. Win the battle and the square becomes your X. Lose it and the square becomes the alien's O. Get three X in a line to win the game.

## Who it is for
Anyone with a web browser, on a computer or a phone. Players don't need an account, an install or an internet connection.

## How it is built
- One file, `index.html`, with all styles and scripts inside it.
- Plain HTML, CSS and JavaScript. No frameworks, build steps, backend, accounts, paid APIs or downloaded assets.
- Opens by double-clicking `index.html`.

## In scope
- A 3x3 board with squares numbered 1 to 9 (top row 1-2-3, middle row 4-5-6, bottom row 7-8-9).
- Battles with health, alien moves and three reply buttons.
- Win, lose and draw results for the whole board.
- A "Restart game" button.
- Mouse, keyboard and touch play.
- Readable text, enough color contrast and a layout that fits a phone screen.

## Out of scope
- A computer opponent that places marks on its own.
- Timers, sound, scores saved between visits, or multiplayer.
- Images, fonts or code loaded from other websites.

## Where the details live
- Exact rules, screen states, controls and completion checks: `game-rules.md`.
- The game counts as done when every completion check in `game-rules.md` is recorded as Passed in `test-report.md`.
