# Test report

Each check comes from "Completion checks" in `game-rules.md`.
Result is one of: **Passed**, **Failed**, **Not tested**.
"Checked by" says who ran it: Claude (automated) or you (in the browser).

Last updated: 2026-10-19. The game hasn't been built yet, so nothing has been tested.

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| 1 | Double-clicking `index.html` opens the game with no internet connection. | Not tested | | | |
| 2 | First load: instructions, 9 empty cells, "Restart game" visible, no reply buttons active. | Not tested | | | |
| 3 | No sound and no countdown or timer anywhere. | Not tested | | | |
| 4 | Selecting an empty cell highlights it, shows health 2 for both and alien move "Laser". | Not tested | | | |
| 5 | During a battle, selecting any cell does nothing. | Not tested | | | |
| 6 | A cell with X or O can't be selected. | Not tested | | | |
| 7 | Alien moves appear in the order Laser, Shield, Claw. | Not tested | | | |
| 8 | Shield to Laser, Blast to Shield, Dodge to Claw lowers alien health by 1. | Not tested | | | |
| 9 | Any other reply lowers player health by 1. | Not tested | | | |
| 10 | After a reply, reply buttons are disabled and repeat presses change nothing. | Not tested | | | |
| 11 | "Next exchange" appears only when both health values are above 0. | Not tested | | | |
| 12 | At 0 health the battle ends at once with no "Next exchange". | Not tested | | | |
| 13 | Three correct replies in a row: cell gets X. | Not tested | | | |
| 14 | Two wrong replies in a row: cell gets O. | Not tested | | | |
| 15 | After a battle (game not over) the board unlocks; the next battle starts at health 2 each with "Laser". | Not tested | | | |
| 16 | No O ever appears except from a lost battle. | Not tested | | | |
| 17 | Three X in each of the 8 lines shows "You win". | Not tested | | | |
| 18 | Three O in a line shows "You lose". | Not tested | | | |
| 19 | Nine marks with no line shows "Draw". | Not tested | | | |
| 20 | A 9th mark that completes a line shows win or lose, not draw. | Not tested | | | |
| 21 | After a win, loss or draw, no cell can be selected. | Not tested | | | |
| 22 | "Restart game" is visible in every state. | Not tested | | | |
| 23 | "Restart game" at any point empties the board, clears health and messages, shows instructions. | Not tested | | | |
| 24 | The whole game can be played with only Tab, Shift+Tab, Enter and Space. | Not tested | | | |
| 25 | Focus moves as listed in Keyboard behavior; focus outline always visible. | Not tested | | | |
| 26 | At 360 pixels wide everything fits with no sideways scrolling. | Not tested | | | |
| 27 | The whole game can be played to a result by tapping. | Not tested | | | |
| 28 | One game file, `index.html`, with no links to other websites. | Not tested | | | |
