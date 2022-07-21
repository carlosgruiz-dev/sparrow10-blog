---
title: "Tic-Tac-Toe (Part 1)"
date: 2022-07-20T21:31:28Z
draft: false
tags: ["programming", "games"]
---

[Tic-tac-toe][1]  is a popular game that everyone has played once. But playing and explaining the
game to a computer are different things. So, this article is a kind of explanation for
non-programmers about how we reason about automating routines or creating programs.

Let's start with the central part of the game, the board. Our board is a 3x3 table where we place
our moves. If we want the computer to understand what is happening on the board, we must identify
the possible positions. In this case, we use an MS Excel-like representation to make it more
intuitive.

|       | col 1 | col 2 | col 3 |
|:-----:|:-----:|:-----:|:-----:|
| row 1 |  p1   |  p2   |  p3   |
| row 2 |  p4   |  p5   |  p6   |
| row 3 |  p7   |  p8   |  p9   |

Now is easier to see when a user wins. One way to know if a player has three positions in a row is
to use a simple sum operation to calculate the state of the winning positions on the board. In
other words, if `Player X` adds `1` point and `Player O` subtracts `1` to the row. `Player X` wins
if it sums total `3`, and `Player O` wins if it computes -3. With this we create this winning
conditions for our game like follows.

```text
Player X = 1
Player O = -1
```

## Winning options

### Winning rows

```text
p1 + p2 + p3 = [+3 / -3]
p4 + p5 + p6 = [+3 / -3]
p7 + p8 + p9 = [+3 / -3]
```

### Winning columns

```text
p1 + p4 + p7 = [+3 / -3]
p2 + p5 + p8 = [+3 / -3]
p3 + p6 + p9 = [+3 / -3]
```

### Winning diagonal

```text
p1 + p5 + p9 = [+3 / -3]
p7 + p5 + p3 = [+3 / -3]
```

## The loop

Now comes the game loop, when every player has its turn and mark a place in the board. So the game
loop sounds like this:

```text
1. A player selects a position available in the board
2. The game checks if there is a winner
  - If so, celebrates and the game ends.
3. The game checks if the board have more additional spaces left.
  - If so, changes the current user and start step 1 again.
  - If not, game ends with no winner.
```

So, that's it. In another post we will create our tic-tac-toe game in a spreadsheet, and when we do, you will
be officially a programmer.

See you next time.

[1]: https://en.wikipedia.org/wiki/Tic-tac-toe
