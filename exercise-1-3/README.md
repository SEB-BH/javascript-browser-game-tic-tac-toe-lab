<h1>
  <span class="headline">Tic Tac Toe Lab</span>
  <span class="subhead">Hint Set A</span>
</h1>

## Hint set A: Working with individual squares

This approach follows the core **Cozy Cafe Part 5** task: select an element, give it text, and update that text after a click.

Start with one square. Make it work before repeating the pattern.

<details markdown="1">
<summary>Hint 1: Select each square separately</summary>

In Cozy Cafe, you selected the rose latte, croissant, and cheesecake status elements individually.

Use the same approach for the nine game squares. Store each selected square in its own variable.

The square IDs are numbers written as strings. You can select them with:

```js
document.getElementById('0');
```

Pass the ID without `#`.

Also select the message element and reset button.

**Reminders:**

- Cozy Cafe, **Part 5**: individual element references.
- [Cheatsheet: Another option — select by ID](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#another-option-select-by-id).

</details>

<details markdown="1">
<summary>Hint 2: Make one square respond to a click</summary>

Start with the first square only.

Give it a click listener that changes its `textContent` to `'X'`.

This follows the same pattern as a cafe button changing a status to `'Sold Out'`.

Once that works, replace the fixed `'X'` with a variable that remembers the current player.

Display the starting player in the message element.

**Reminders:**

- Cozy Cafe, **Part 5**: individual click listeners.
- [Cheatsheet: Respond to an Event](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#10-respond-to-an-event).

</details>

<details markdown="1">
<summary>Hint 3: Repeat the pattern for the other squares</summary>

Give the second square its own listener. Inside that listener, change the second square’s text.

Continue one square at a time until all nine work.

When repeating code, check both places:

- Which square receives the listener?
- Which square gets its `textContent` changed?

Each listener should update its own square.

**Reminder:**

- Cozy Cafe, **Part 5**: each sold-out button updates the status next to it.

</details>

<details markdown="1">
<summary>Hint 4: Remember the game’s progress</summary>

The marks are already stored in the squares’ `textContent`.

You also need to remember:

- Which player is taking the current turn.
- How many valid moves have been made.
- Whether the game has ended.

Possible variable names are `currentPlayer`, `moveCount`, and `gameOver`.

Their starting values could be `'X'`, `0`, and `false`.

Keep these variables outside the listeners so all the listeners and helper functions can use them.

</details>

<details markdown="1">
<summary>Hint 5: Allow only valid moves</summary>

Before placing a mark, check two things:

1. Is this square empty?
2. Is the game still running?

An empty square has `textContent` equal to `''`.

Only carry out the move when both conditions are true. You can combine the conditions with `&&`.

Apply the same rule to every square’s listener.

**Reminder:**

- [Control Flow: logical operators](https://seb-bh.github.io/javascript-control-flow/boolean-logic/#logical-operators).

</details>

<details markdown="1">
<summary>Hint 6: Switch players and count valid moves</summary>

Inside each listener’s valid-move condition:

1. Put the current player’s mark in that square.
2. Increase the move count by one.
3. Switch to the other player.
4. Update the turn message.

Use `if...else` to switch between X and O.

You can put the switching and turn-message instructions in a function that each listener calls.

When winner and tie checks are added, switch players only if the game is still running.

**Reminder:**

- [Control Flow: branching](https://seb-bh.github.io/javascript-control-flow/branching/).

</details>

<details markdown="1">
<summary>Hint 7: Check whether the current player completed one row</summary>

After a valid move, the current player may have completed a winning line.

Start with the top row.

Check whether all three top-row squares contain the current player’s mark.

For example, one part of that check could be:

```js
square0El.textContent === currentPlayer
```

You also need to check the other two squares. Connect the three checks with `&&`.

If all three contain the current player’s mark:

- Record that the game is over.
- Display that player as the winner.

Perform this check before switching players.

Because you are checking for `'X'` or `'O'`, empty squares cannot satisfy these conditions.

**Reminders:**

- [Intro to the DOM: modifying text](https://ga-curriculum.github.io/intro-to-the-dom/modifying-an-element/#modifying-text).
- [Control Flow: equality operators](https://seb-bh.github.io/javascript-control-flow/boolean-logic/#equality-operators).

</details>

<details markdown="1">
<summary>Hint 8: Repeat the winner check for the other lines</summary>

Once the top-row check works, write a separate check for the middle row.

Continue with the bottom row, the three columns, and the two diagonals.

Use the winning-groups table to choose the correct three squares for each check.

You can put all eight checks in a function called after every valid move.

Separate `if` statements are fine. Check each group of three before moving on.

**Reminder:**

- [Functions: declaring and calling functions](https://seb-bh.github.io/intro-to-javascript-functions/fundamentals/).

</details>

<details markdown="1">
<summary>Hint 9: Use the move count to detect a tie</summary>

There are nine squares.

If nine valid moves have been made and nobody has won, the game is a tie.

Check both conditions before:

- Recording that the game is over.
- Displaying the tie message.

Check for a winner before checking for a tie. The ninth move might complete a winning line.

Only valid moves should increase the move count.

**Reminder:**

- [Control Flow: logical operators](https://seb-bh.github.io/javascript-control-flow/boolean-logic/#logical-operators).

</details>

<details markdown="1">
<summary>Hint 10: Keep the actions in the correct order</summary>

Inside each square’s valid-move condition, follow this order:

```text
Place the current player's mark.
Increase the move count.
Check for a winner.
Check for a tie.
Switch players only if the game is still running.
```

Your player-switching function can check whether the game is still running before changing the player or turn message.

This preserves the winner or tie message when the game ends.

**Reminder:**

- [Functions: calling helper functions](https://seb-bh.github.io/intro-to-javascript-functions/return-values/#bringing-it-all-together).

</details>

<details markdown="1">
<summary>Hint 11: Reset each square and each variable</summary>

Create a reset function.

Inside it:

- Clear the first square’s `textContent`.
- Repeat for the other eight squares.
- Restore X as the current player.
- Restore the move count to zero.
- Record that the game is running again.
- Display X’s turn.

Connect the reset button to this function using a named handler.

Call the same function once after your function definitions to set up the starting game.

**Reminders:**

- [Cheatsheet: clearing text](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#4-read-or-change-text).
- [Cheatsheet: Use a Named Event Handler](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#11-use-a-named-event-handler).

</details>

## Final checks

Test that:

- X starts on an empty board.
- Valid moves alternate between X and O.
- Clicking an occupied square does not change the turn.
- Each of the eight winning lines works.
- Both X and O can win.
- A full board with no winner produces a tie.
- A winning ninth move produces a win.
- Clicks after the game ends do not change anything.
- Reset works during a game and after a win or tie.

### Useful test games

Start a fresh game before each test. Click the square IDs in the order shown.

| Test | Click order | Expected result |
|---|---|---|
| X wins across the top | `0, 3, 1, 4, 2` | X wins |
| O wins across the top | `3, 0, 4, 1, 8, 2` | O wins |
| Tie | `0, 1, 2, 4, 3, 5, 7, 6, 8` | Tie game |
| Win on the ninth move | `0, 1, 2, 3, 4, 5, 7, 6, 8` | X wins |

If something is not working, use console logs and the cheatsheet’s [Quick Troubleshooting](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#quick-troubleshooting) section.

## Level Up: Reduce repetition

Once your game works, consider these changes one at a time:

- Store the selected squares in a collection.
- Use a loop to attach listeners.
- Share one click handler and use `event.target.id`.
- Store the moves in a board array.
- Use a rendering function to display the array.
- Store the winning groups in an array and loop through them.

Make one change, then test the game again.
