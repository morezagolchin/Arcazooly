# Arcazooly

Small browser games. Plain HTML, CSS and JavaScript: one file per game, no frameworks, no build step.
The look follows chessooly: same palette, boxes and patterned background, in light and dark mode.

```
index.html          home page: the list of games
snake/index.html    Snake
```

Open `index.html` in a browser, or serve the folder with any static server (for example `python3 -m http.server`).

## Adding a game

1. Copy `snake/index.html` to `<game>/index.html`.
2. Keep the two blocks marked **arcazooly shared style** and **arcazooly shared script** exactly as they are.
   They hold the palette, top bar, boxes, buttons, background pattern and the `bestScore` helper.
3. Replace everything after the `── Snake ──` markers (in the `<style>` and the `<script>`) and the page's `<main>` with the new game.
   Keep the top bar with the `← All games` link.
4. Set `const GAME = '<game>'` and save high scores with `bestScore.get(GAME)` / `bestScore.set(GAME, score)`.
   They're stored in localStorage as `arcazooly:<game>:best`.
5. Add a card for it to the list in `index.html`, with `data-best="<game>"` so its best score shows there.

Useful pieces already in the shared style: `.box` (a bordered panel), `.panel` (padding), `.label` (small uppercase heading),
`.hint` (muted text), `button` / `button.primary`, `kbd`, and `.touch-only` / `.key-only` to show things only on touch screens
or only with a mouse and keyboard.
