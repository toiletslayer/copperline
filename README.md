# Copperline

Copperline is a CapStash-inspired browser visualizer built from the spirit of the classic 3D Pipes screensaver.

The goal is to turn the open-source 3D Pipes browser project by 1j01 into a darker, copper/bronze conduit system with glowing data flow, loopback junctions, relay nodes, CRT-style overlays, and livestream-friendly visuals.

Base inspiration / upstream project:

- https://github.com/1j01/pipes

## Project direction

Copperline should stay simple at first:

- Static HTML/CSS/JavaScript
- Three.js rendering
- No backend
- No framework unless there is a very strong reason
- GitHub Pages compatible
- OBS/browser-source friendly
- Runnable locally on a mini PC

## Intended use

Primary use case:

- A 24/7 browser-based visual loop for OBS / livestream use

Secondary use cases:

- GitHub Pages demo site
- Desktop wrapper later with Electron or Tauri
- Possible visual language for future CapStash-adjacent environments

## Visual identity

Copperline should feel like:

- glowing copper conduits
- dark industrial machine internals
- data/energy moving through pipe loops
- old CRT terminal feed
- CapStash-style underground/mining/electrical environment

It should not feel like:

- random rainbow toy pipes
- default Windows screensaver clone
- overbuilt modern web app
- React/Next/Vite boilerplate unless needed

## First development target

Milestone 1 is not a full rewrite.

Milestone 1 is:

1. Import/adapt the upstream `1j01/pipes` browser project.
2. Preserve upstream attribution and license information.
3. Keep the project static and easy to run.
4. Confirm it loads locally.
5. Then begin Copperline theming in small, readable commits.

## Local run goal

The final simple local run path should be something like:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## GitHub Pages goal

The repo should eventually deploy as a static GitHub Pages site.

Preferred public URL shape:

```text
https://toiletslayer.github.io/copperline/
```

## Main docs

- `COPPERLINE_SPEC.md` — visual and technical spec
- `CODEX_MEGA_PROMPT.md` — prompt to hand Codex
- `ROADMAP.md` — phased build plan
- `ATTRIBUTION.md` — upstream/license notes
