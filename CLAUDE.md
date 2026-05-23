# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project purpose

This is a learning sandbox for studying [Phaser 3](https://phaser.io/) — a JavaScript HTML5 game framework. Each experiment lives in its own standalone `.html` file so it can be opened directly in a browser without a build step.

## How to run

Open any `.html` file directly in a browser (double-click or drag into browser). No server, no build tool, no npm required unless a specific demo needs one.

If a file uses ES modules or loads local assets via `fetch`, a local server is needed:

```powershell
# Python (if installed)
python -m http.server 8080

# Node (if installed)
npx serve .
```

Then open `http://localhost:8080/<file>.html`.

## File conventions

- One `.html` file per concept or experiment.
- Phaser is loaded from CDN inside each file — no local install needed:
  ```html
  <script src="https://cdn.jsdelivr.net/npm/phaser@3/dist/phaser.min.js"></script>
  ```
- Game config and scene code live inline in a `<script>` tag within the same HTML file to keep each demo self-contained and easy to read.

## Phaser 3 basics to know

- Entry point is `new Phaser.Game(config)` where `config` contains `type`, `width`, `height`, `scene`.
- A scene object has three lifecycle methods: `preload()`, `create()`, `update()`.
- Assets are loaded in `preload()`, objects are created in `create()`, and per-frame logic runs in `update()`.
- Physics is opt-in: set `physics: { default: 'arcade' }` in config to enable Arcade Physics.
