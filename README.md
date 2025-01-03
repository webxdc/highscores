# Highscores

[![npm package](https://img.shields.io/npm/v/@webxdc/highscores.svg)](https://npmjs.com/package/@webxdc/highscores)
[![CI](https://github.com/webxdc/highscores/actions/workflows/ci.yml/badge.svg)](https://github.com/webxdc/highscores/actions/workflows/ci.yml)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)

Library to facilitate the process of creating score-based webxdc games.
It can handle multiple scoreboards at the same time.

## Install

```
npm install @webxdc/highscores
```

## Usage

Quick overview of the API:

```js
import "@webxdc/highscores";

// always do this first, only use the API after init() finishes
await window.highscores.init();

// get current player's highscore
const score = window.highscores.getScore();
console.log(`your score: ${score}`);

// this will cause an announcement in chat only if it's a new highscore
window.highscores.setScore(score + 100);

const scoreboard = window.highscores.getHighScores();
scoreboard.forEach((player) => {
  console.log(`${player.pos}. ${player.name} - ${player.score}`);
});
```

The `webxdc.js` lib also needs to be included in your `index.html`:

```html
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <script src="webxdc.js"></script>
    <script type="module">
      import "@webxdc/highscores";
      // you can use window.highscores here
    </script>
  </head>
  <body>
    ...
  </body>
</html>
```

Check [dist/highscores.d.ts](https://github.com/webxdc/highscores/blob/main/dist/highscores.d.ts) file for documentation of the available API.

For a full example check the [example/index.html](https://github.com/webxdc/highscores/blob/main/example/index.html) file.
