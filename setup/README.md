<h1>
  <span class="headline">Tic Tac Toe Lab</span>
  <span class="subhead">Setup</span>
</h1>

## Setup

Open your Terminal application and navigate to your `~/code/ga/labs` directory:

```bash
cd ~/code/ga/labs
```

Navigate to [this Tic Tac Toe Starter Code Repo](https://github.com/SEB-PT-10/tic-tac-toe) and fork it.

Click on the green `Code` button, and copy the `HTTP` link to your forked repo.  (Double check that you see YOUR username in the link)

Clone your newly created repo into your `~/code/ga/labs` directory with the `git clone` command:

```bash
git clone https://github.com/<your-username>/tic-tac-toe.git
```

> Note: In the link above, where it says `<your-username>`, you should see the username from your GitHub account.

Next, `cd` into your new cloned directory, `tic-tac-toe`:

```bash
cd tic-tac-toe
```

Open the contents of the directory in VS Code:

```bash
code .
```

### Starter code

There is some starter code associated with this lab.

#### HTML

Take a moment to review this starter HTML. Specifically take note of these elements that will be important to the logic of this game:

- There is an `<h2>` element provided where you can display messages to the user. It has an `id` of `"message"`.
- A game board has also been created inside of the `<section>` element. It has a `"board"` class.
- The game board is made up of nine `<div>` elements. These elements all share the same class: `sqr`, and also have unique ids ranging from `0` to `8`.
  > 🧠 Think about why these might be numbered starting from 0 instead of 1. What data type have we used that starts from 0 instead of 1? This will come into play later.
- Using `id` and/or `class` attributes will help you target elements for styling and wiring up your click event listeners. These have already been added for you in this lab!

#### CSS

You've seen quite a bit of CSS like this before, there are no declarations here that we need to discuss.


#### JS

There are some useful guidelines in the javaScript for helping you organize your code.  You may not necessarily need to use every section and you're free to disregard these guidelines if you so choose.

## Start the app

Open the `index.html` file in your browser and access the console output in your browser's dev tools.
