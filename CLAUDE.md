# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Vanilla JavaScript Tetris on HTML5 Canvas. No dependencies (`package.json` only holds a `dev` script), no build step, no test suite, no linter. User-facing text (README, UI strings like `PAUSA`, `Reiniciar`, `Puntuación`) is in Spanish — keep it that way.

## Running

Open `index.html` directly in a browser, or serve the folder statically with `npm run dev` (preferred). Verification is manual: play the game in the browser.

## Gotchas

- **Board** is a `ROWS × COLS` matrix; each cell is `0` or a piece type index `1–7`. The same index is used in `PIECES` shapes and to look up `COLORS`, so the three arrays must stay aligned (index 0 is `null` in both `PIECES` and `COLORS`).
- **`updateHUD()`** must be called after score/lines/level change.
- **Canvas sizing is not derived**: if `COLS`, `ROWS`, or `BLOCK` change, update `width`/`height` of `<canvas id="board">` in `index.html` to `COLS*BLOCK × ROWS*BLOCK`. The next-piece preview assumes a 4×4 grid of 30px cells (`#next-canvas` is 120×120).
