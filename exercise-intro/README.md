<h1>
  <span class="headline">Tic-Tac-Toe Lab</span>
  <span class="subhead">Exercise</span>
</h1>

**Learning objective:** By the end of this lab, you will be able to combine variables, functions, conditions, and DOM events to build a playable game.

## Introduction

Build a Tic-Tac-Toe game using the HTML and CSS provided.

Write your JavaScript in `app.js`. Use your previous lessons, your Cozy Cafe work, and the optional hints below.

## Requirements

Your game should:

- Start with an empty board.
- Let X play first.
- Display whose turn it is.
- Place the current player’s mark in the clicked square.
- Alternate players after each valid move.
- Prevent players from changing an occupied square.
- Detect a winner and display who won.
- Detect a tie and display a tie message.
- Prevent further moves after a win or tie.
- Let players reset the game.

An invalid click must not change the board or switch players.

## Resources

- Your completed **Cozy Cafe Lab, Part 5**.
- The [JavaScript DOM Cheat Sheet](https://seb-bh.github.io/cozy-cafe-lab/cheatsheet/).
- The lesson sections linked inside the hints.

## Choose your approach

Both approaches can meet the requirements.

| Approach | How it works | Hints |
|---|---|---|
| Individual squares | Select each square separately and change its `textContent` directly, like the core Cozy Cafe task. | [Hint set A](../exercise-1-3/README.md) |
| Arrays — Level Up | Store the moves in an array and use a rendering function to display them. | [Hint set B 🚀](../exercise-4-5/README.md)|

If you want to build one square at a time, start with **Hint set 2**. You can return to the array approach after your game works.

## Board positions

The squares have IDs from `0` to `8`:

| Left | Middle | Right |
|---|---|---|
| `0` | `1` | `2` |
| `3` | `4` | `5` |
| `6` | `7` | `8` |

## Winning groups

A player wins when their mark occupies all three positions in one of these groups:

| Winning line | Positions |
|---|---|
| Top row | `0`, `1`, `2` |
| Middle row | `3`, `4`, `5` |
| Bottom row | `6`, `7`, `8` |
| Left column | `0`, `3`, `6` |
| Middle column | `1`, `4`, `7` |
| Right column | `2`, `5`, `8` |
| Top-left to bottom-right diagonal | `0`, `4`, `8` |
| Top-right to bottom-left diagonal | `2`, `4`, `6` |

Use this table as a reference. You can write a separate condition for each winning line.

- [Hint Set A](../exercise-1-3/README.md)
- [Hint Set B](../exercise-4-5/README.md)
