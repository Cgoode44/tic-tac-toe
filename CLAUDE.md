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

After every meaningful unit of work — a new feature, a bug fix, a refactor — commit and push immediately to `https://github.com/Cgoode44/tic-tac-toe`. Do not batch multiple changes into one commit. The goal is that no work is ever lost and the repo always reflects the latest state.

Commit message rules:
- Subject line: short imperative phrase describing *what* changed (e.g. `Add AI opponent with easy difficulty`)
- Body (when needed): one or two lines explaining *why*, not just *what*
- Always append `Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>`

Never finish a session without pushing. If a task spans multiple steps, commit at each stable checkpoint rather than waiting until everything is done.
