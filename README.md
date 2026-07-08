# TACTIC

A small browser platformer (vanilla HTML/CSS/JS, no build tools needed) made for a school
assignment. Inspired by "Level Devil"-style rage-platformers, but reframed: each level's
"gotcha" mechanic represents a different way a tic can present in Tourette Syndrome.

## How to run

Just open `index.html` in any modern browser (double-click it, or serve the folder with
any static file server, e.g. `npx serve .` or `python3 -m http.server`).

Note: This game saves your level progression and accomplishments in your browser. Anyone using the same browser and device will share the same saved progress. To start fresh, open the game in an Incognito/Private window, use a different browser or browser profile, or clear this site's browser data.

## Controls

- Left / Right arrow (or A / D): move
- Up arrow / Space / W: jump
- Esc: pause menu (restart from checkpoint, or return to the main menu)
- ⟲ button (top-right): restart from your latest checkpoint

## The map

All 5 "tic" sections are stitched together into one continuous, side-scrolling
map — walk right and you'll pass through all of them in order, with the
camera following you the whole way. There's no more "loading the next level":
you just keep going.

1. **Irregular Small Tics** — a flashing red block appears without warning; jump over it.
2. **Cause-and-Effect Tics** — the floor looks perfectly normal, but jumping near certain
   spots causes the ground there to collapse a moment later. Triggered by your own action.
3. **Delayed Tics** — two platforms swing back and forth on their own timing; you have to
   read and time your jump to their rhythm rather than your own.
4. **Persistent Tics** — a gap that keeps widening once you've crossed it, so hesitating
   costs you.
5. **Blinking Tics** — a tall vertical climb while your own character flickers in and out
   of view.

Each of the 5 sections still ends at a mailbox, but touching one no longer "finishes a
level" — it sets that mailbox as your checkpoint. If you die anywhere on the map, you
respawn at the most recent mailbox you've touched (or at the very start of the map if you
haven't reached one yet), not at the beginning of the whole thing. Reaching the final
mailbox at the end of the map completes the game.

## Files

- `index.html` — page structure / HUD / overlays
- `css/style.css` — visual styling, including the title-screen background art
- `js/levels.js` — source data for the 5 original sections (ground layout, hazards, moving
  platforms, mailbox, intro text), plus the `buildWorld()` step that stitches them into one
  continuous `WORLD` map
- `js/game.js` — game engine: input, physics, collision, camera, rendering, and the
  checkpoint/respawn system

| files                                | source             |
| ------------------------------------ | ------------------ |
| `assets/images/mailman.png`          | Created in Copilot |
| `assets/images/mailbox.png`          | Created in Copilot |
| `assets/images/levelbg.png`          | Created in Copilot |
| `assets/images/titlebg.png`          | Created in Copilot |
| `assets/sounds/background_music.mp3` | Created in Copilot |
| `assets/sounds/button_click.mp3`     | Created in Copilot |
| `assets/sounds/game_music.mp3`       | Created in Copilot |
| `assets/sounds/jump_sound.mp3`       | Created in Copilot |
| `assets/sounds/mailbox_bell.mp3`     | Created in Copilot |
