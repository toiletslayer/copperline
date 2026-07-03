# Copperline Roadmap

## Milestone 0 — Repo setup

Status: in progress

- Add planning docs
- Add Codex mega prompt
- Add attribution notes
- Keep the repo simple and public

## Milestone 1 — Import upstream base

Goal: get the original browser project running in this repo before changing the visuals.

Tasks:

- Import/adapt `https://github.com/1j01/pipes`
- Preserve license and attribution
- Confirm static local run works
- Confirm no build system is required unless upstream already uses one
- Document local run instructions

Exit criteria:

- `index.html` opens locally
- pipes render in browser
- README has local run steps

## Milestone 2 — Copperline visual pass

Goal: make it look like Copperline instead of rainbow 3D Pipes.

Tasks:

- Add copper/bronze palette
- Replace random materials
- Add dark background
- Remove candy cane / novelty styling
- Make joints copper couplings or simple relay nodes

Exit criteria:

- Visual identity clearly reads as copper conduit system
- No major behavior changes yet

## Milestone 3 — Relay nodes and glow

Goal: add the data/energy feeling.

Tasks:

- Replace teapot behavior with relay/core nodes
- Add warm orange glow accents
- Add inner glow line or cylinder inside pipe segments
- Add subtle pulsing to relay nodes if stable

Exit criteria:

- Pipes feel alive, not just recolored

## Milestone 4 — Loopback behavior

Goal: create intentional Copperline loops.

Tasks:

- Add `loopConnectionChance`
- Allow occasional reconnection to occupied grid nodes
- Add/update junction node when loop connects
- Avoid messy overlaps and z-fighting
- Tune default chance around `0.10` to `0.20`

Exit criteria:

- Closed loop routes appear naturally
- Geometry remains clean

## Milestone 5 — CRT / OBS polish

Goal: make it stream-ready.

Tasks:

- Add scanline overlay
- Add vignette
- Tune for 16:9 fullscreen
- Test as OBS Browser Source or browser window capture
- Add optional UI toggle or CSS class for CRT overlay

Exit criteria:

- Looks good at 1920x1080 fullscreen
- No major performance hit

## Milestone 6 — Stability pass

Goal: run for long sessions.

Tasks:

- Cap active objects
- Reuse materials
- Add reset behavior if needed
- Watch for memory growth
- Avoid too many lights
- Document best OBS settings

Exit criteria:

- Can run overnight without obvious crashes or runaway memory use

## Milestone 7 — GitHub Pages deployment

Goal: free hosted demo.

Tasks:

- Enable GitHub Pages from main branch/root or docs folder
- Confirm URL works
- Add Pages URL to README

Expected URL:

```text
https://toiletslayer.github.io/copperline/
```

## Later ideas

Only after the browser version is good:

- Electron/Tauri desktop wrapper
- Fullscreen kiosk mode helper
- Preset modes: Classic Copperline, Loop Network, CapStash Core
- Audio-reactive glow
- Recorded video loop pack
- Godot visual-language port for game use
