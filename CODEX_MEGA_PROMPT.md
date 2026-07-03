# Codex Mega Prompt: Copperline

Use this prompt when handing the repo to Codex.

---

You are working in the GitHub repository `toiletslayer/copperline`.

Project name: **Copperline**

## Goal

Create a browser-based CapStash-inspired copper conduit visualizer based on the open-source Three.js 3D Pipes project:

- https://github.com/1j01/pipes

Copperline should preserve the satisfying procedural growth of classic 3D Pipes, but visually and behaviorally transform it into a dark industrial copperline network with glowing relay nodes and intentional loopback connections.

This is meant for OBS/browser-source livestream visuals, GitHub Pages hosting, and local mini PC use.

## Critical constraints

Do not overbuild this.

Use:

- static HTML
- CSS
- plain JavaScript
- Three.js

Avoid unless absolutely necessary:

- React
- Next.js
- Vue
- Vite
- Webpack
- backend server
- database
- auth
- analytics
- TypeScript migration

The project must remain GitHub Pages compatible and easy to run locally with a static file server.

## Phase 1: Import upstream base

Import/adapt the upstream project from:

```text
https://github.com/1j01/pipes
```

Requirements:

1. Preserve upstream license and attribution.
2. Add attribution notes in `ATTRIBUTION.md` if needed.
3. Keep the original app running before making major theme changes.
4. Do not remove upstream notices.
5. Do not rewrite the project structure unnecessarily.
6. Verify the app can run locally.

Expected local run:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Phase 2: Copperline visual theme

Convert the visual identity from classic/random 3D Pipes to Copperline.

### Color palette

Use a controlled copper palette instead of random rainbow colors.

Suggested constants:

```js
const COPPERLINE_THEME = {
  copper: 0xb87333,
  darkCopper: 0x5a2f16,
  hotGlow: 0xff7a1a,
  warmHighlight: 0xffb86b,
  oxidizedGreen: 0x2f7f64,
  background: 0x050403,
};
```

### Materials

Replace random pipe materials with copper/bronze materials.

Preferred style:

- metallic-looking copper or bronze pipes
- warm specular highlights
- subtle emissive orange/brown
- occasional green oxidation accents
- glowing orange relay nodes

Avoid:

- random rainbow pipe colors
- candy cane materials
- goofy novelty objects

## Phase 3: Remove/replace novelty behavior

Remove or disable visual features that break the Copperline mood:

- teapots
- candy cane pipes
- random novelty coloring

Replace those with:

- glowing relay node
- copper coupling
- oxidized connector
- rare larger core junction

Use simple Three.js geometry first. Do not spend too much time on custom models.

## Phase 4: Inner glow / data flow

Add a simple visual cue that the copperline is carrying energy or data.

Acceptable first-pass implementations:

- smaller inner cylinder with transparent orange glow
- glowing line along the pipe center
- pulsing material opacity
- animated emissive relay nodes

Do not build complex custom shaders in the first pass unless it is simple and stable.

## Phase 5: Loopback behavior

This is the most important behavior change.

The original 3D Pipes behavior tends to reject occupied grid positions to avoid collisions.

Copperline should allow occasional intentional reconnection to existing occupied grid nodes.

Add a tweakable option:

```js
loopConnectionChance: 0.15
```

When a pipe attempts to move into an occupied grid position:

1. Usually still avoid messy collisions.
2. But sometimes allow the connection if it makes a clean junction.
3. Add/update a relay/coupling node at the junction.
4. Draw the connecting segment.
5. Continue or terminate cleanly depending on what looks best.

Goal: closed loops, circuit-like returns, braided conduit networks.

Not goal: random spaghetti, z-fighting, broken geometry.

## Phase 6: CRT overlay / livestream polish

Add lightweight CSS overlays:

- scanlines
- vignette
- maybe subtle grain/noise if easy

Keep it performant.

It should look good as a fullscreen OBS Browser Source.

## Phase 7: Settings and tuning

Make these values easy to find and edit:

```js
speedMin
speedMax
loopConnectionChance
glowIntensity
pipeRadius
jointRadius
maxPipeCount
backgroundMode
crtOverlayEnabled
oxidationChance
relayNodeChance
```

A UI panel is optional. Clear constants are enough for the first version.

## Phase 8: Stability

This may run for long sessions.

Avoid:

- memory leaks
- unbounded object creation
- too many unique materials
- too many lights
- excessive per-frame allocations

Prefer:

- material reuse
- object caps
- periodic reset
- simple geometry
- stable render loop

## Deliverables

After completing the first implementation, report:

1. Files changed.
2. How to run locally.
3. How to enable GitHub Pages.
4. Where to tweak copper colors.
5. Where to tweak loop chance.
6. Where to tweak speed.
7. Where to tweak glow intensity.
8. Any known limitations.

## Commit style

Make small readable commits if possible:

1. Import upstream base
2. Add attribution/docs
3. Apply Copperline palette/materials
4. Replace novelty joints with relay nodes
5. Add loopback connection behavior
6. Add CRT overlay
7. Add tuning docs

## Final vibe check

When running, Copperline should feel like:

> a living copper circuit organism growing inside a dark CapStash mining/data machine.

It should not feel like:

> a rainbow Windows screensaver clone with a new name.
