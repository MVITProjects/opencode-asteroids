# Asteroids

Clone of the classic arcade **Asteroids** implemented in pure HTML5 Canvas, with no dependencies or bundler.

## Description

Spaceship in an asteroid field with edge wrapping (toroidal space). Destroy asteroids to earn points: large ones split into medium, medium into small. Includes special power-ups and unique asteroid types like the falling star.

## Technologies

- **HTML5 Canvas** — 2D rendering
- **JavaScript (ES6+)** — Game logic in a single file `game.js`
- No frameworks, no bundler, no dependencies

## How to Run

Open `index.html` directly in the browser (double-click), or use a local server:

```bash
npx serve .
```

Then visit `http://localhost:3000`.

## Controls

| Key       | Action     |
| --------- | ---------- |
| `←` `→`   | Rotate ship|
| `↑`       | Thrust    |
| `Space`   | Shoot     |

## Scoring

| Asteroid | Points |
| --------- | ------ |
| Large     | 20     |
| Medium    | 50     |
| Small     | 100    |

## Features

- 3 lives with temporary invincibility on respawn (blinking)
- Asteroids split into smaller fragments when destroyed
- Explosion particles when destroying asteroids
