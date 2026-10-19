# Test report

Each check comes from "Completion checks" in `game-rules.md`.
Result is one of: **Passed**, **Failed**, **Not tested**.
"Checked by" says who ran it: Claude (automated) or you (in the browser).

Last updated: 2026-10-19. The game (`index.html`) is built. The 28 checks below were run automatically by Claude and all passed. Your browser checks for the game (G1–G8) also passed; G9 (real phone) is not tested.

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| 1 | Double-clicking `index.html` opens the game with no internet connection. | Passed | Claude (automated) | 2026-10-19 | Opened from disk with the browser set to offline. |
| 2 | First load: instructions, 9 empty cells, "Restart game" visible, no reply buttons active. | Passed | Claude (automated) | 2026-10-19 |  |
| 3 | No sound and no countdown or timer anywhere. | Passed | Claude (automated) | 2026-10-19 | Checked the code for timers and sound. |
| 4 | Selecting an empty cell highlights it, shows health 2 for both and alien move "Laser". | Passed | Claude (automated) | 2026-10-19 |  |
| 5 | During a battle, selecting any cell does nothing. | Passed | Claude (automated) | 2026-10-19 |  |
| 6 | A cell with X or O can't be selected. | Passed | Claude (automated) | 2026-10-19 |  |
| 7 | Alien moves appear in the order Laser, Shield, Claw. | Passed | Claude (automated) | 2026-10-19 | All 17 possible battles played step by step (5 won, 12 lost). |
| 8 | Shield to Laser, Blast to Shield, Dodge to Claw lowers alien health by 1. | Passed | Claude (automated) | 2026-10-19 | All 17 possible battles played step by step. |
| 9 | Any other reply lowers player health by 1. | Passed | Claude (automated) | 2026-10-19 | All 17 possible battles played step by step. |
| 10 | After a reply, reply buttons are disabled and repeat presses change nothing. | Passed | Claude (automated) | 2026-10-19 | Also checked after every reply in all 17 battles. |
| 11 | "Next exchange" appears only when both health values are above 0. | Passed | Claude (automated) | 2026-10-19 | All 17 possible battles played step by step. |
| 12 | At 0 health the battle ends at once with no "Next exchange". | Passed | Claude (automated) | 2026-10-19 | All 17 possible battles played step by step. |
| 13 | Two correct replies in a row: cell gets X. | Passed | Claude (automated) | 2026-10-19 | Tested Shield then Blast. Wording corrected from "three" on 2026-10-19 (the alien has only 2 health). |
| 14 | Two wrong replies in a row: cell gets O. | Passed | Claude (automated) | 2026-10-19 |  |
| 15 | After a battle (game not over) the board unlocks; the next battle starts at health 2 each with "Laser". | Passed | Claude (automated) | 2026-10-19 |  |
| 16 | No O ever appears except from a lost battle. | Passed | Claude (automated) | 2026-10-19 | The alien never places a mark on its own. |
| 17 | Three X in each of the 8 lines shows "You win". | Passed | Claude (automated) | 2026-10-19 | All 8 lines checked. |
| 18 | Three O in a line shows "You lose". | Passed | Claude (automated) | 2026-10-19 | All 8 lines checked. |
| 19 | Nine marks with no line shows "Draw". | Passed | Claude (automated) | 2026-10-19 |  |
| 20 | A 9th mark that completes a line shows win or lose, not draw. | Passed | Claude (automated) | 2026-10-19 |  |
| 21 | After a win, loss or draw, no cell can be selected. | Passed | Claude (automated) | 2026-10-19 | Checked after a win, a loss and a draw. |
| 22 | "Restart game" is visible in every state. | Passed | Claude (automated) | 2026-10-19 | Checked in instructions, choose response, exchange feedback, battle finished and board finished. |
| 23 | "Restart game" at any point empties the board, clears health and messages, shows instructions. | Passed | Claude (automated) | 2026-10-19 | Checked mid-battle, after feedback, after a battle and after a game result. |
| 24 | The whole game can be played with only Tab, Shift+Tab, Enter and Space. | Passed | Claude (automated) | 2026-10-19 | Played three battles to a win. |
| 25 | Focus moves as listed in Keyboard behavior; focus outline always visible. | Passed | Claude (automated) | 2026-10-19 | Outline checked at every step. |
| 26 | At 360 pixels wide everything fits with no sideways scrolling. | Passed | Claude (automated) | 2026-10-19 | Smallest button 44 px. On the first screen the instructions push the board partly below the bottom of a 740 px tall phone screen, so you scroll down; no sideways scrolling. |
| 27 | The whole game can be played to a result by tapping. | Passed | Claude (automated) | 2026-10-19 | Simulated taps, not a real phone. |
| 28 | One game file, `index.html`, with no links to other websites. | Passed | Claude (automated) | 2026-10-19 | Prototype folders are separate test files, not part of the game. |

## Board prototype (`prototype-board/index.html`)
This is a temporary prototype, not the final game, so its results don't count toward the 28 checks above.

### Automated checks run by Claude
Run on 2026-10-19 in a headless Chromium browser (Playwright), against the file opened directly from disk.

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| P1 | First load: 9 empty cells, test buttons disabled, "Play again" visible. | Passed | Claude (automated) | 2026-10-19 | |
| P2 | Selecting a cell highlights it, locks all 9 cells and enables the test buttons. | Passed | Claude (automated) | 2026-10-19 | |
| P3 | Clicking another cell during a battle does nothing. | Passed | Claude (automated) | 2026-10-19 | |
| P4 | Only one resolution per battle: repeat or second test-button presses change nothing. | Passed | Claude (automated) | 2026-10-19 | |
| P5 | A filled cell can't be selected. | Passed | Claude (automated) | 2026-10-19 | |
| P6 | After a battle (game not over) the board unlocks. | Passed | Claude (automated) | 2026-10-19 | |
| P7 | All 8 lines of X show "You win!", highlight that line and lock the board. | Passed | Claude (automated) | 2026-10-19 | |
| P8 | All 8 lines of O show "You lose.", highlight that line and lock the board. | Passed | Claude (automated) | 2026-10-19 | |
| P9 | Full board with no line shows "Draw." (and no early result before the 9th mark). | Passed | Claude (automated) | 2026-10-19 | |
| P10 | A 9th mark that completes a line shows a win, not a draw. | Passed | Claude (automated) | 2026-10-19 | |
| P11 | After a game result cells ignore clicks; "Play again" clears the board after a result and mid-battle. | Passed | Claude (automated) | 2026-10-19 | |
| P12 | Keyboard only (Tab, Enter, Space) plays to a result; focus goes cell → "Test battle win" → message. | Passed | Claude (automated) | 2026-10-19 | |
| P13 | No outside websites used (no requests, no outside links). | Passed | Claude (automated) | 2026-10-19 | |
| P14 | No script errors. | Passed | Claude (automated) | 2026-10-19 | |
| P15 | At 360 px wide: no sideways scrolling, every button at least 44 px, everything on one screen. | Passed | Claude (automated) | 2026-10-19 | Smallest button exactly 44 px. |
| P16 | Simulated touch taps play to a result. | Passed | Claude (automated) | 2026-10-19 | Simulated, not a real phone. |

### Checks for you in your browser

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| B1 | Double-clicking `prototype-board/index.html` opens it in your browser. | Passed | You (browser) | 2026-10-19 | |
| B2 | Clicking a cell makes it highlighted and the other cells stop responding. | Passed | You (browser) | 2026-10-19 | |
| B3 | "Test battle win" puts X in the cell; "Test battle loss" puts O. Pressing again does nothing. | Passed | You (browser) | 2026-10-19 | |
| B4 | Three X in a row shows "You win!"; three O shows "You lose."; full board with no line shows "Draw." | Passed | You (browser) | 2026-10-19 | |
| B5 | "Play again" empties the board. | Passed | You (browser) | 2026-10-19 | |
| B6 | Keyboard only: Tab moves between buttons, Enter or Space presses them, and the orange focus outline is visible. | Passed | You (browser) | 2026-10-19 | |
| B7 | On a real phone: everything fits and tapping works. | Not tested | | | Optional: needs the file copied to the phone. |

## Battle prototype (`prototype-battle/index.html`)
This is a temporary prototype, not the final game, so its results don't count toward the 28 checks above.

### Automated checks run by Claude
Run on 2026-10-19 in a headless Chromium browser (Playwright), against the file opened directly from disk.

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| T1 | Start: both health 2, alien shows Laser, replies enabled, no "Next exchange", "Restart battle" visible. | Passed | Claude (automated) | 2026-10-19 | |
| T2 | Every possible reply sequence follows the rules: Laser → Shield → Claw order; correct reply costs alien 1, wrong costs player 1; "Next exchange" only while both have health; ends at 0 with the right result. | Passed | Claude (automated) | 2026-10-19 | All 17 possible battles checked step by step (5 won, 12 lost). Battles last 2 or 3 exchanges. |
| T3 | Only the first reply in an exchange counts; extra clicks and double clicks are ignored. | Passed | Claude (automated) | 2026-10-19 | |
| T4 | "Next exchange" shows the next alien move and turns the replies back on. | Passed | Claude (automated) | 2026-10-19 | |
| T5 | At 0 health the battle ends at once; no "Next exchange" and replies stay off. | Passed | Claude (automated) | 2026-10-19 | |
| T6 | "Restart battle" resets health, alien move and messages while choosing, after feedback and after the battle ends. | Passed | Claude (automated) | 2026-10-19 | |
| T7 | Keyboard only plays to a result; focus goes Shield → "Next exchange" → Shield → message. | Passed | Claude (automated) | 2026-10-19 | |
| T8 | No timers, sound or outside websites. | Passed | Claude (automated) | 2026-10-19 | |
| T9 | No script errors. | Passed | Claude (automated) | 2026-10-19 | |
| T10 | At 360 px wide: no sideways scrolling, every button at least 44 px, everything on one screen. | Passed | Claude (automated) | 2026-10-19 | |
| T11 | Simulated touch taps play a battle to a result. | Passed | Claude (automated) | 2026-10-19 | Simulated, not a real phone. |

### Checks for you in your browser

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| C1 | Double-clicking `prototype-battle/index.html` opens it: You 2, Alien 2, alien shows Laser. | Passed | You (browser) | 2026-10-19 | |
| C2 | Win: Shield, Next exchange, Blast. Alien health goes 2 → 1 → 0 and "You won the battle!" shows with no "Next exchange". | Passed | You (browser) | 2026-10-19 | |
| C3 | Lose: Blast, Next exchange, Dodge. Your health goes 2 → 1 → 0 and "You lost the battle." shows. | Passed | You (browser) | 2026-10-19 | |
| C4 | Three exchanges: Shield, Next exchange, Dodge, Next exchange. The alien shows Claw. | Passed | You (browser) | 2026-10-19 | |
| C5 | After a reply, clicking another reply button does nothing. | Passed | You (browser) | 2026-10-19 | |
| C6 | "Restart battle" in the middle of a battle and after it ends goes back to 2 and 2 with Laser. | Passed | You (browser) | 2026-10-19 | |
| C7 | Keyboard only: Tab, Enter and Space play a whole battle, and the orange focus outline is visible. | Passed | You (browser) | 2026-10-19 | |

## Full game (`index.html`): checks for you in your browser

| # | Check | Result | Checked by | Date | Notes |
|---|---|---|---|---|---|
| G1 | Double-clicking `index.html` opens the game: title, message, "How to play", 9 empty squares, "Restart game". | Passed | You (browser) | 2026-10-19 | |
| G2 | Picking a square hides "How to play", highlights the square and shows You 2, Alien 2 and Laser. Other squares don't respond. | Passed | You (browser) | 2026-10-19 | |
| G3 | Winning a battle (Shield, Next exchange, Blast) puts X in the square, and you can pick another square. | Passed | You (browser) | 2026-10-19 | |
| G4 | Losing a battle (Blast, Next exchange, Dodge) puts O in the square. | Passed | You (browser) | 2026-10-19 | |
| G5 | Three X in a row shows "You win!" and highlights the line; no squares can be picked after. | Passed | You (browser) | 2026-10-19 | |
| G6 | Three O in a row shows "You lose."; a full board with no line shows "Draw.". | Passed | You (browser) | 2026-10-19 | |
| G7 | "Restart game" in the middle of a battle and after a result empties the board and shows "How to play" again. | Passed | You (browser) | 2026-10-19 | |
| G8 | Keyboard only: a whole game can be played with Tab, Shift+Tab, Enter and Space, with the orange outline always visible. | Passed | You (browser) | 2026-10-19 | |
| G9 | On a real phone: no sideways scrolling, tapping works. | Not tested | | | Optional. |
