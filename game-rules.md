# Game rules: Alien Tic-Tac-Toe

## Rules (exactly as given)
* Solo 3x3 board. Selecting an empty cell locks the board and starts a battle for that cell.
* Win the battle: X in that cell. Lose: O. No automatic opponent move.
* Three X in a line wins; three O loses; full board with no line is a draw. Lines: 1-2-3, 4-5-6, 7-8-9, 1-4-7, 2-5-8, 3-6-9, 1-5-9, 3-5-7.
* Battle: 2 health each. Alien shows Laser, then Shield, then Claw. Correct replies: Shield, Blast, Dodge. Correct costs the alien 1 health; wrong costs the player 1. One accepted response per exchange; "Next exchange" button only when both sides have health; battle ends immediately at 0.
* "Restart game" button always available during play; it clears everything.
* No timers, sound, backend, or downloaded assets.

## What the rules mean in practice

### The board
Cells are numbered like this:

```
1 | 2 | 3
4 | 5 | 6
7 | 8 | 9
```

- An empty cell can be selected. A cell with X or O cannot.
- While a battle is running, the whole board is locked: no cell can be selected.

### A battle
- Each battle starts fresh: player health 2, alien health 2.
- Each turn of a battle is called an exchange. The alien shows one move per exchange, in this order:

| Exchange | Alien shows | Correct reply |
|---|---|---|
| 1st | Laser | Shield |
| 2nd | Shield | Blast |
| 3rd | Claw | Dodge |

- The player always gets the same three reply buttons: **Shield**, **Blast**, **Dodge**.
- Correct reply: alien loses 1 health. Wrong reply: player loses 1 health.
- Only the first reply in each exchange counts. Any extra presses or taps are ignored.
- Every exchange costs someone 1 health, so a battle always ends within 3 exchanges. The order above never needs to repeat.
- When either side reaches 0 health the battle ends at once, with no "Next exchange" button.
  - Alien at 0: the player wins the battle and the cell gets **X**.
  - Player at 0: the player loses the battle and the cell gets **O**.

### The whole board
After each new X or O, the game checks the board in this order:
1. Three X in any line listed above: **you win the game**.
2. Three O in any line listed above: **you lose the game**.
3. All 9 cells filled with no line: **draw**.
4. Otherwise: the board unlocks and the player picks the next empty cell.

Only one mark is added at a time, so a single new mark can't create an X line and an O line together. If the 9th mark completes a line, the result is a win or a loss, not a draw.

### Restart game
- The "Restart game" button is on screen in every state.
- Pressing it clears the board, health, alien move and messages, and returns to the Instructions state.

## States

| State | What the player sees | Allowed actions | What happens next |
|---|---|---|---|
| **Instructions** | Short how-to-play text and an empty, unlocked board. | Select any empty cell. Restart game. | Selecting a cell → Choose response (battle for that cell starts). |
| **Choose cell** | Board with existing X/O marks, unlocked. A message to pick an empty cell. | Select an empty cell. Restart game. | Selecting a cell → Choose response. |
| **Choose response** | Locked board with the battle cell highlighted. Both health values. The alien's current move. Reply buttons Shield, Blast, Dodge. | Press one reply button (only the first press counts). Restart game. | If both sides still have health → Exchange feedback. If either side hits 0 → Battle finished. |
| **Exchange feedback** | Locked board. The alien's move, the player's reply, whether it was correct, who lost health, updated health. Reply buttons disabled. "Next exchange" button. | Next exchange. Restart game. | Next exchange → Choose response with the alien's next move. |
| **Battle finished** | Feedback for the last exchange. Battle result ("You won the battle: X" or "You lost the battle: O"). The mark is in the cell. No "Next exchange" button. Board unlocked. | Select an empty cell. Restart game. | If the new mark ends the game → Board finished. Otherwise, selecting an empty cell → Choose response. |
| **Board finished** | Full or partly filled board. Final result: "You win", "You lose" or "Draw". The winning line is highlighted when there is one. Board locked. | Restart game. | Restart game → Instructions. |

The Board finished check happens straight away when the mark is placed, so the player never sees Battle finished with an unlocked board on a finished game.

## Keyboard behavior
- Every cell, reply button, "Next exchange" and "Restart game" is a real button. Tab and Shift+Tab move between them.
- Enter or Space activates the focused button.
- Cells are in reading order 1 to 9.
- Locked cells and filled cells can't be activated. Disabled reply buttons are skipped.
- Where focus goes:
  - After selecting a cell: the **Shield** reply button.
  - After a reply: "Next exchange" if it is shown, otherwise the battle result message.
  - After "Next exchange": the **Shield** reply button.
  - After "Restart game": cell 1.
- The focused button always has a clearly visible outline.
- Messages (alien move, feedback, results) are announced to screen readers when they change.

## Touch behavior
- One tap selects a cell or presses a button. Nothing depends on hovering.
- Cells and buttons are at least 44 by 44 pixels so they are easy to hit.
- A double tap or rapid repeat tap on a reply button counts as one reply.
- The board, health, alien move, reply buttons and "Restart game" fit on a phone screen in portrait (about 360 pixels wide) without scrolling sideways.

## Completion checks
Each check is something you can see or do in the browser. Results go in `test-report.md` as Passed, Failed or Not tested.

### Setup
1. Double-clicking `index.html` opens the game with no internet connection.
2. On first load: instructions shown, 9 empty cells, "Restart game" visible, no reply buttons active.
3. No sound plays and there is no countdown or timer anywhere.

### Starting a battle
4. Selecting an empty cell highlights it and shows health 2 for both sides and the alien move "Laser".
5. During a battle, selecting any cell does nothing.
6. A cell that already has X or O can't be selected.

### Exchanges
7. Alien moves appear in the order Laser, Shield, Claw.
8. Replying Shield to Laser, Blast to Shield and Dodge to Claw lowers alien health by 1.
9. Any other reply lowers player health by 1.
10. After a reply the reply buttons are disabled. Pressing or tapping them again changes nothing.
11. "Next exchange" appears only when both health values are above 0.
12. When a health value reaches 0 the battle ends at once with no "Next exchange" button.

### Battle results
13. Two correct replies in a row: cell gets X.
14. Two wrong replies in a row: cell gets O.
15. After a battle (game not over) the board unlocks and a new empty cell can be picked. A new battle starts at health 2 each with "Laser".
16. No O ever appears except from a lost battle.

### Board results
17. Three X in each of the 8 lines (1-2-3, 4-5-6, 7-8-9, 1-4-7, 2-5-8, 3-6-9, 1-5-9, 3-5-7) shows "You win".
18. Three O in a line shows "You lose".
19. Nine marks with no line shows "Draw".
20. A 9th mark that completes a line shows win or lose, not draw.
21. After a win, loss or draw, no cell can be selected.

### Restart
22. "Restart game" is visible in every state.
23. Pressing it at any point (mid-battle, after feedback, after a game result) empties the board, clears health and messages and shows the instructions again.

### Keyboard
24. The whole game can be played to a result with only Tab, Shift+Tab, Enter and Space.
25. Focus moves as listed in Keyboard behavior, and the focus outline is always visible.

### Touch and phone
26. On a phone (or a browser set to 360 pixels wide) everything fits with no sideways scrolling.
27. The whole game can be played to a result by tapping.

### Build rules
28. The project has one game file, `index.html`, with no links to other websites.
