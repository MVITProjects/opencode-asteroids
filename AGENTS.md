# AGENTS.md

## Commands

- Run locally: `npx serve .` (any static server works; opening `index.html` directly also works — no external asset loading).
- No build, test, lint, or typecheck exists, and no `package.json`. This is intentional (no dependencies, no bundler) — don't add tooling unless asked.
- Verification is manual: run the server and play in the browser (arrows + Space, Space also restarts after game over).

## Architecture

- Single-page static game: `index.html` is the only entry point; all logic lives in `game.js` (vanilla ES6).
- `game.js` is loaded via a plain `<script>` tag, not an ES module. New JS files must be added to `index.html` manually and in order; there are no imports/exports.
- Screen size 800×600 is duplicated: `W`/`H` constants in `game.js` and the `width`/`height` attributes of the `<canvas>` in `index.html`. Change both together.
- Per-size asteroid behavior uses lookup arrays indexed by `size` (3 = large, 1 = small): `RADII`, `SPEEDS`, `POINTS` at the top of `game.js`. Note `POINTS[1] = 100` — small asteroids score most.
- For single-shot input (shoot, restart) use `pressed('Space')`, which consumes a just-pressed flag. Reading `keys['Space']` directly fires every frame.

## Conventions

- All user-facing text (including the in-game HUD) is in English. Keep it that way.
- Style: single quotes, semicolons, 2-space indent, section banner comments (`// ── Name ──`).
