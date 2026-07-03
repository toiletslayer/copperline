# Copperline

Copperline is a CapStash-inspired browser visualizer built from the spirit of
the classic 3D Pipes screensaver.

The goal is to turn the open-source 3D Pipes browser project by 1j01 into a
darker, copper/bronze conduit system with glowing data flow, loopback
junctions, relay nodes, CRT-style overlays, and livestream-friendly visuals.

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

## Local run

Run Copperline locally from the repository root with a basic static server:

```bash
python -m http.server 8000 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8000/
```

If port 8000 is already in use, choose another port:

```bash
python -m http.server 8080 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8080/
```

No build step is required. The current app is static HTML, CSS, JavaScript,
Three.js libraries, and image assets, so it remains compatible with GitHub
Pages.

## GitHub Pages goal

The repo should eventually deploy as a static GitHub Pages site.

Preferred public URL shape:

```text
https://toiletslayer.github.io/copperline/
```

## Main docs

- `docs/COPPERLINE_SPEC.md` - visual and technical spec
- `CODEX_MEGA_PROMPT.md` - prompt to hand Codex
- `ROADMAP.md` - phased build plan
- `TODO.md` - next-step prompts and review checklist
- `ATTRIBUTION.md` - upstream/license notes
- `docs/CODEX_PHASE_1_PROMPT.md` - focused Phase 1 prompt

## Upstream base

Phase 1 imports the original static browser app from
[1j01/pipes](https://github.com/1j01/pipes) without applying the Copperline
theme yet.

- Imported upstream commit: `86e8eb1418f937ef43f9acbd871085c5160714fc`
- Upstream author: Isaiah Odhner
- Upstream license: MIT, preserved in [LICENSE](LICENSE)
- Original upstream README: [UPSTREAM_README.md](UPSTREAM_README.md)
