# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

A single-file web game (`tictactoe.html`) — no build tools, no dependencies, no package manager. Open the file directly in a browser to play.

## Running the game

```bash
open tictactoe.html
```

## Architecture

Everything lives in one file with three sections:

- **CSS** (`<style>`) — dark theme using `#1a1a2e` / `#16213e` palette; X is red (`#e94560`), O is teal (`#a8dadc`)
- **HTML** — a 3×3 grid of `.cell` divs (`data-i="0"` through `data-i="8"`), a status line, and a scoreboard
- **JS** (`<script>`) — plain vanilla JS; `board[]` is a flat 9-element array, `WINS` lists all 8 winning index triplets, `checkWin()` scans them after each move

State is held in three module-level variables: `board`, `current` (whose turn), and `over` (game ended). The `scores` object persists across `init()` calls so the scoreboard survives new games.

## Git workflow

Commit after every meaningful change and push to `https://github.com/Cgoode44/tic-tac-toe`. Keep commit messages descriptive (what changed and why, not just "update file").
