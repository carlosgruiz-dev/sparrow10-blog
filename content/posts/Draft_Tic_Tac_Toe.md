---
title: "Tic-Tac-Toe"
date: 2022-07-14T00:31:28Z
draft: true
tags: ["programming", "games"]
---

[Tic-tac-toe][1] is a very well known game. But, what happen if you want to reason about to
program the it? People know how to fry eggs, or make a sandwich, but sometimes they have a hard
time to express this simple actions like a sequence of steps. Lets try to describe this game
in a way you can create you first computer game.

Lets start with a plan, the steps we are going to follow to create the game:

- Describe the board
- Rules of the game
- How a player wins?
- Playing the game (The loop)
- The programming
- Lets play

## The Board

|       | col 1 | col 2 | col 3 |
|:-----:|:-----:|:-----:|:-----:|
| row 1 |  p1   |  p2   |  p3   |
| row 2 |  p4   |  p5   |  p6   |
| row 3 |  p7   |  p8   |  p9   |

## The Rules

### The players

```text
X = 1
O = -1
```

## Winning options

### Winning ows

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

### `have_a_winner` function

### `is_board_full` function

0. select fist player
1. player marks possition
2. if `have_a_winner`
   1. annouce winner
   2. end the game
3. if `is_board_full`
   1. announce no winner
   2. end the game
4. switch player
5. go to 1

## The solution

## The solution using FP

[1]: https://en.wikipedia.org/wiki/Tic-tac-toe
