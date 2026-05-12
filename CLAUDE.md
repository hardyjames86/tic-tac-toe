# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Single-file browser game (`tictactoe.html`). No build step, no dependencies, no package manager. Open the file directly in a browser to run it.

## Architecture

Everything lives in `tictactoe.html` — inline CSS, inline JS, and HTML in one file.

**Game state** (JS, bottom of file):
- `board` — 9-element array of `''`, `'X'`, or `'O'`
- `current` — whose turn it is (`'X'` or `'O'`)
- `over` — boolean, blocks clicks after win/draw
- `scores` — `{ X, O, D }` object, persists across rounds

**Win detection**: `WINS` is a hardcoded array of the 8 winning index triplets. `checkWin(board, player)` returns the matching triplet or `null`.

**Colour palette** (all in the `<style>` block):
- Background: `#2d1b4e`
- Cell background: `#16213e`, hover/win: `#0f3460`
- X accent / buttons: `#e94560`
- O accent / status text: `#a8dadc`

## Deploying

Push to GitHub and enable GitHub Pages on the `master` branch (root) to serve it as a live URL.
