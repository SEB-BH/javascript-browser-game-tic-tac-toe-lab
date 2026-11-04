<h1>
  <span class="headline">Tic Tac Toe Lab</span>
  <span class="subhead">Hint Set B - Level Up 🚀</span>
</h1>

## Hint set 1: Using an array — Level Up

This approach extends the **Level Up** tasks in Cozy Cafe, Part 5.

The core cafe task did not require an array or a rendering function. Use the linked lessons if these connections are still new.

<details markdown="1">
<summary>Hint 1: Store the game’s data</summary>

One possible plan uses:

- `board`: an array of nine empty strings.
- `turn`: the current player, starting as `'X'`.
- `winner`: whether someone has won, starting as `false`.
- `tie`: whether the game is a tie, starting as `false`.

An empty string represents an empty square. A played square contains `'X'` or `'O'`.

The array indexes match the board positions shown above.

**Reminder:**

- [Arrays: accessing elements by index](https://seb-bh.github.io/intro-to-javascript-arrays/reading/#accessing-elements-at-any-position-in-an-array).

</details>

<details markdown="1">
<summary>Hint 2: Select the page elements</summary>

Select the collection of squares, the message element, and the reset button.

`querySelectorAll()` gives you a collection that you can access by index or loop through.

**Reminders:**

- [Cheatsheet: Select Multiple Elements](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#3-select-multiple-elements).
- [Intro to the DOM: selecting multiple elements](https://ga-curriculum.github.io/intro-to-the-dom/working-with-collections-of-elements/#selecting-multiple-elements).

</details>

<details markdown="1">
<summary>Hint 3: Display the array</summary>

Create a rendering function.

Loop through the board array using `forEach()`. Use each item’s index to find the corresponding square, then display the item using `textContent`.

The array item already contains the text you need: `'X'`, `'O'`, or `''`.

Call the function when the page loads. Temporarily change one array item to confirm it appears in the matching square.

**Reminders:**

- Cozy Cafe, Part 5 **Level Up**: use an availability array and a render function.
- [Arrays: `forEach()` and its index parameter](https://seb-bh.github.io/intro-to-javascript-arrays/forEach/#syntax).
- [Cheatsheet: Read or Change Text](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#4-read-or-change-text).

</details>

<details markdown="1">
<summary>Hint 4: Connect a click to an array position</summary>

Create a handler with an `event` parameter. Attach it to each square using a loop.

Inside the handler, read `event.target.id`. That ID identifies the board position to update.

Change that array item to the current player’s mark, then call your rendering function.

HTML IDs are strings. An ID such as `"2"` can still access position `2` in the array.

**Reminders:**

- Cozy Cafe, Part 5 **Level Up**: share one handler that edits the array.
- [Cheatsheet: Use a Named Event Handler](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#11-use-a-named-event-handler).
- [Cheatsheet: Use the Event Object](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#12-use-the-event-object).

</details>

<details markdown="1">
<summary>Hint 5: Reject invalid moves</summary>

Before changing the array, check whether the selected position already contains a mark.

Also check whether the game has ended.

If either makes the move invalid, stop the handler before changing the board or switching players.

A `return;` statement stops the function.

**Reminder:**

- [Functions: the `return` statement](https://seb-bh.github.io/intro-to-javascript-functions/return-values/#the-return-statement).

</details>

<details markdown="1">
<summary>Hint 6: Alternate players</summary>

After a valid move, use `if...else` to change `'X'` to `'O'`, or `'O'` to `'X'`.

Once you add winner and tie checks, switch players only if the game is still running.

Render after updating the game data.

**Reminder:**

- [Control Flow: branching](https://seb-bh.github.io/javascript-control-flow/branching/).

</details>

<details markdown="1">
<summary>Hint 7: Check one winning line first</summary>

Start with the top row.

Check that:

- `board[0]` is not empty.
- `board[0]` matches `board[1]`.
- `board[0]` matches `board[2]`.

All three conditions must be true, so connect them with `&&`.

If they are true, record that someone has won. Repeat the pattern for the other seven winning lines.

Check for a winner before switching players.

**Reminder:**

- [Control Flow: logical operators](https://seb-bh.github.io/javascript-control-flow/boolean-logic/#logical-operators).

</details>

<details markdown="1">
<summary>Hint 8: Check for a tie</summary>

Check for a winner first.

If nobody has won, count the empty strings in the board array using a loop.

If there are no empty strings, the game is a tie.

Start your empty-square counter at zero each time you perform this check.

**Reminder:**

- [Arrays: looping with `forEach()`](https://seb-bh.github.io/intro-to-javascript-arrays/forEach/#syntax).

</details>

<details markdown="1">
<summary>Hint 9: Put the game actions in order</summary>

Your click handler should follow this plan:

```text
Reject an invalid move.
Record the current player's mark.
Check for a winner.
Check for a tie.
Switch players if the game is still running.
Render the updated data.
```

Keep the winning player as the current player when the game ends. You can then use that value in the winner message.

**Reminder:**

- [Functions: calling helper functions](https://seb-bh.github.io/intro-to-javascript-functions/return-values/#bringing-it-all-together).

</details>

<details markdown="1">
<summary>Hint 10: Display the correct message</summary>

Your rendering function should display:

1. The winner, if someone has won.
2. Otherwise, a tie message if the game is a tie.
3. Otherwise, whose turn it is.

Changing a variable does not automatically update the page. Your rendering function must run again after the data changes.

**Reminder:**

- [Cheatsheet: Read or Change Text](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#4-read-or-change-text).

</details>

<details markdown="1">
<summary>Hint 11: Keep the completed game unchanged</summary>

Every click handler should check whether the game has already ended.

After a win, some squares may still be empty. Those squares must no longer accept moves.

Try clicking an empty square after winning. The board and message should remain unchanged.

**Reminder:**

- [Control Flow: logical operators](https://seb-bh.github.io/javascript-control-flow/boolean-logic/#logical-operators).

</details>

<details markdown="1">
<summary>Hint 12: Reset the data and render again</summary>

Create a function that restores the starting data and calls your rendering function.

Keep the state variables declared outside this function so the other functions can use them.

Call the function once to start the game, and pass it as the reset button’s click handler.

Attach the event listeners once, outside the reset function.

**Reminders:**

- [Cheatsheet: Use a Named Event Handler](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/#11-use-a-named-event-handler).
- [Functions: calling a function](https://seb-bh.github.io/intro-to-javascript-functions/fundamentals/#calling-a-function).

</details>
