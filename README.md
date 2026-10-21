# Midnight Loop

A 3D night-city racing game that runs in the browser. It's built with plain JavaScript and Three.js, with no build step and no install.

- 3 laps, 8 checkpoints per lap
- 2 AI rivals racing for position
- Live telemetry HUD: speed, gear, RPM, throttle, brake, lap delta, next checkpoint
- Real-time minimap
- 3 cameras: chase, far chase, hood
- Keyboard on desktop, touch buttons on phones
- Best lap is saved in the browser

## Play locally

Double-click `index.html`. It opens in your browser and runs fully offline, because Three.js and the fonts are included in this folder.

If your browser blocks local files, start a small server in this folder and open http://localhost:8000:

```
python -m http.server 8000
```

## Controls

| Key | Action |
|---|---|
| W / ↑ | Throttle |
| S / ↓ / Space | Brake, reverse |
| A D / ← → | Steer |
| C | Change camera |
| R | Reset car to the track |
| P | Pause |
| M | Sound on/off |
| H | Hide/show HUD |

**Watch autopilot** on the start screen lets the car drive itself. It's useful for screen recordings.

## Put it online with GitHub Pages

1. Create a new public repository on GitHub, e.g. `midnight-loop`.
2. Upload everything in this folder (`index.html`, `lib/`, `fonts/`, `README.md`) to the repository root.
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, and choose `main` / `(root)`.
4. After a minute the game is live at `https://<your-username>.github.io/midnight-loop/`.

Netlify, Vercel and Cloudflare Pages also work: drag and drop this folder.

## Files

```
index.html          the whole game (HTML, CSS, JavaScript)
lib/three.min.js    Three.js r128 (3D engine)
fonts/              Chakra Petch + JetBrains Mono (HUD fonts)
```

## Customize

All of these are in `index.html`:

- **Track shape:** edit the `pts` list of `[x, z]` points under `// ---------- track ----------`.
- **Number of laps:** change `const LAPS = 3`.
- **Billboards:** edit the `ADS` list (text and neon colour).
- **Rival difficulty:** change the last number in `newRacer(...)` for each rival (about 0.9 is easy, 1.05 is hard).
- **Sky colours:** edit the gradient stops under `// dusk sky`.

## Credits

- [Three.js](https://threejs.org), MIT licence (`lib/THREE-LICENSE.txt`)
- Chakra Petch and JetBrains Mono fonts, SIL Open Font Licence (`fonts/`)
