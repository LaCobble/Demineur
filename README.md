# Minesweeper (Démineur)

[![CI](https://github.com/LaCobble/Demineur/actions/workflows/ci.yml/badge.svg)](https://github.com/LaCobble/Demineur/actions/workflows/ci.yml)
![Python](https://img.shields.io/badge/python-3.8%2B-3776AB?logo=python&logoColor=white)
![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

A console Minesweeper written in plain Python, with recursive flood fill, flags, a timer and a session scoreboard.

<p align="center">
  <img src="docs/images/2-flood-fill.webp" width="70%" alt="Minesweeper grid in the terminal after the first move">
</p>

## What it does

Minesweeper is the classic puzzle: uncover every safe square of the grid without stepping on a mine. Each uncovered square shows how many mines touch it. This version runs entirely in the terminal and uses only the Python standard library.

- Random grid generation with the chosen number of mines.
- Grid display with row and column coordinates.
- Recursive uncovering of empty areas (flood fill).
- Flags to mark suspected mines.
- Timer and move counter, shown at the end of the game.
- Scoreboard of the games played during the session, sorted by time.

The in-game text is in French.

## Screenshots

Real terminal sessions of `DEMINEUR.py` (difficulty 1, 30 × 30 grid), rendered as images. Hidden squares are `x`, flags `!`.

<table>
  <tr>
    <td width="50%"><img src="docs/images/1-new-game.webp" alt="New game: difficulty, grid size and the hidden grid"></td>
    <td width="50%"><img src="docs/images/2-flood-fill.webp" alt="First move uncovering a large empty area"></td>
  </tr>
  <tr>
    <td align="center"><sub>New game: choose the difficulty and the grid size</sub></td>
    <td align="center"><sub>First move: the recursive flood fill opens the empty area</sub></td>
  </tr>
  <tr>
    <td><img src="docs/images/3-flag.webp" alt="A flag placed on a suspected mine"></td>
    <td><img src="docs/images/4-win.webp" alt="Grid cleared, moves, time and scoreboard"></td>
  </tr>
  <tr>
    <td align="center"><sub>Typing <code>!</code> places a flag on a suspected mine</sub></td>
    <td align="center"><sub>Grid cleared: moves, time and the session scoreboard</sub></td>
  </tr>
</table>

## Getting started

### Prerequisites

- Python 3.8 or newer. No third-party package is needed.

### Run

```bash
git clone https://github.com/LaCobble/Demineur.git
cd Demineur
python DEMINEUR.py
```

### How to play

1. Choose the difficulty and the grid size (30 or 40):
   - difficulty 1: as many mines as the grid size,
   - difficulty 2: twice as many,
   - difficulty 3: three times as many.
2. On each turn, press **Enter** to uncover a square or type **!** to place a flag, then give the horizontal and vertical coordinates.
3. Uncovering a mine ends the game; uncovering every safe square wins it. Your number of moves and time are displayed, then you can view the scoreboard and play again.

## Project structure

```text
.
├── DEMINEUR.py   # the whole game: grid generation, display, flood fill, game loop, scoreboard
└── README.md
```

## What this project demonstrates

- Modelling a game board as a 2D matrix, and computing neighbour counts on its edges and corners.
- Recursion: uncovering connected empty squares.
- A simple game loop with input validation, timing (`time`) and dates (`datetime`).
- A hand-written selection sort to keep the scoreboard ordered.

## Context

Built in Python during the first semester of a two-year Computer Science degree (DUT Informatique), in the 2021–2022 school year. It is kept as it was written, as a portfolio piece; only the repository around it (documentation, CI) has been tidied up.

## Contributing

Issues and small pull requests are welcome: see [CONTRIBUTING.md](CONTRIBUTING.md) and the [Code of Conduct](CODE_OF_CONDUCT.md).

## License

[MIT](LICENSE) © LaCobble
