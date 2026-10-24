# Neon Warp

A fast-paced, arcade-style tunnel runner that runs entirely in your browser. Pilot a ship through a glowing neon wormhole, dodge obstacles, grab boost orbs, and take down bosses to earn permanent upgrades.

Built with [Three.js](https://threejs.org/) and the Web Audio API in a single HTML file. No build step, no dependencies to install.

## Play

Open `index.html` in any modern browser. That's it.

> **Note:** Three.js (r128) is loaded from the cdnjs CDN, so you'll need an internet connection the first time you load the game.

Or serve it locally:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve
```

Then visit `http://localhost:8000`.

### Deploy with GitHub Pages

1. Go to **Settings → Pages** in your repo.
2. Under **Source**, choose your main branch and the root folder.
3. Your game will be live at `https://<your-username>.github.io/<repo-name>/`.

### Use the Vercel link

Go to https://neonwarp.vercel.app/

## Controls

| Input | Action |
|-------|--------|
| Mouse move | Steer the ship |
| Touch drag | Steer the ship (mobile) |

Your ship follows your cursor or finger through the tunnel. Weapons fire automatically during boss fights.

## Gameplay

- **Survive** as long as you can. Your score climbs continuously, and the tunnel speeds up over time.
- **Dodge** the red cubes. Hitting one ends your run.
- **Collect** golden orbs to trigger **Overdrive**: double speed and invincibility to obstacles for a few seconds. Cubes you plow through are destroyed.
- **Fight bosses** every 5,000 points. A warning flashes, then a giant wireframe guardian approaches. Your auto-cannons engage and you need to shoot it down before it reaches you. Colliding with a boss ends your run unless Overdrive is active.
- **Level up** after each boss kill (+2,000 bonus points) and choose a permanent upgrade for the rest of the run.

### Ships

| Ship | Perk |
|------|------|
| **Stinger** | Agile control, with the fastest steering response |
| **Vanguard** | Shielded hull that absorbs one obstacle hit |
| **Spectre** | Long Overdrive, with 50% longer boosts |

### Level-Up Upgrades

| Upgrade | Effect |
|---------|--------|
| **Cannons** | +20% fire rate |
| **Engines** | +15% base speed |

### Themes

Pick a look from the start menu:

- **Neon Nights**: purple tunnel, cyan ship
- **Emerald Grid**: green tunnel, teal ship
- **Solar Flare**: amber tunnel, yellow ship

## Features

- Three selectable ships with unique perks
- Three color themes
- Boss encounters with auto-firing weapons
- Permanent upgrade choices after each boss
- Procedural synthesized soundtrack and sound effects (toggleable)
- Persistent high score saved in `localStorage`
- Mouse and touch support
- Single-file, zero-build codebase

## Project Structure

```
.
└── index.html   # HTML, CSS, and JavaScript for the entire game
```

## Tech Stack

- **Three.js r128** for 3D rendering
- **Web Audio API** for generated music and sound effects
- Vanilla JavaScript, HTML, and CSS

## Browser Support

Works in current versions of Chrome, Firefox, Safari, and Edge. Requires WebGL support. Audio starts after you click **Initiate Warp**, in line with browser autoplay policies.

## Customization

Everything lives in `index.html`, so tweaking the game is straightforward:

- **Themes:** edit the `themes` object near the top of the script to add or change color palettes (then add a matching `.theme-opt` button in the start menu).
- **Ships:** modify `updatePlayerModel()` to change ship geometry, agility, shield, or boost duration.
- **Difficulty:** adjust the obstacle spawn chance, starting `speed`, speed ramp (`speed += 0.0001`), or `nextBossScore` increment in `animate()`.
- **Boss health:** change the `health` value in `spawnBoss()`.

## Contributing

Issues and pull requests are welcome. Ideas for future updates include new ship types, additional boss patterns, more power-ups, and a pause menu.

## License

Add a license of your choice (e.g., MIT) to the repo and reference it here.
