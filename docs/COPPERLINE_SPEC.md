# Copperline Spec

## One-sentence goal

Copperline is a static browser visualizer that evolves the classic 3D Pipes concept into a CapStash-inspired copper conduit network: dark, industrial, looped, glowing, and livestream-friendly.

## Base project

Upstream inspiration and likely starting codebase:

- https://github.com/1j01/pipes

Use the upstream project as the first technical base unless there is a very strong reason not to.

## Hard constraints

Keep the first version simple:

- Static site only
- HTML/CSS/JavaScript
- Three.js is expected
- No backend
- No database
- No auth
- No analytics
- No React/Next/Vite rewrite unless absolutely necessary
- Must work from GitHub Pages
- Must run locally with a basic static server
- Must be OBS/browser-source friendly

## Target environment

Primary machine:

- Mini PC or always-on Windows desktop
- Browser window or OBS Browser Source
- Long-running sessions for livestream visuals

Primary output:

- Fullscreen 16:9 animated browser visual
- 1920x1080 target first
- 4K compatibility later if performance allows

## Visual mood

Copperline should look like a living conduit system inside a dark mining/data machine.

Keywords:

- copper
- bronze
- dark industrial
- glowing hot orange
- relay nodes
- loopback conduits
- electrical/data flow
- CRT overlay
- subtle grime
- old terminal feed
- mining-rig internals

## Core color palette

Recommended defaults:

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

## Behavior goals

The original 3D Pipes style grows randomized pipe routes through a 3D grid.

Copperline should keep that satisfying procedural growth, but change the meaning:

- Pipes become copper conduits.
- Dead ends become rare.
- Reconnecting to existing paths becomes allowed sometimes.
- Closed loops should form intentionally.
- Junctions should feel like relay/coupling nodes.
- Some segments should pulse as if energy/data is flowing.

## Loop behavior

The major behavior change is allowing intentional reconnection.

Original-style behavior usually rejects occupied grid positions.

Copperline should add:

```js
loopConnectionChance: 0.15
```

When a new segment would hit an occupied position:

1. If reconnecting would make a clean junction, allow it sometimes.
2. Add or update a connector/relay node at that junction.
3. Draw the segment anyway.
4. Avoid ugly overlaps, z-fighting, or impossible geometry.

The point is not chaos. The point is intentional-looking conduit loops.

## Pipe materials

Replace random rainbow materials with controlled copper materials.

Recommended material direction:

- Main pipe: copper/bronze MeshPhongMaterial or MeshStandardMaterial
- Specular/highlight: warm copper/gold
- Emissive: low dark orange/brown
- Inner glow: optional MeshBasicMaterial or line overlay
- Oxidation: rare green accent material, not everywhere

## Joints and nodes

Remove or disable whimsical/non-Copperline objects such as:

- teapots
- candy cane pipes
- random novelty coloring

Replace with:

- copper coupling joints
- glowing relay nodes
- occasional oxidized connector
- rare larger core node
- optional hex/capacitor-like node later

## CRT overlay

Add a CSS overlay, not a heavy rendering feature.

Suggested effects:

- scanlines
- mild vignette
- subtle noise texture if easy
- optional chromatic/glow effect later

Keep this light so it does not hurt performance.

## Controls / tweakable options

Expose the following in code clearly, and optionally in UI later:

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

## Performance goals

Prioritize stability over flash.

Must avoid:

- unbounded geometry growth
- memory leaks during long livestream sessions
- creating too many materials
- creating too many lights
- runaway object counts

Recommended approach:

- reuse materials
- cap active pipe count
- remove old objects or reset scene periodically
- avoid excessive per-frame allocations

## Deployment goals

Local:

```bash
python -m http.server 8000
```

GitHub Pages:

```text
https://toiletslayer.github.io/copperline/
```

## Non-goals for milestone 1

Do not build yet:

- desktop app
- Windows screensaver `.scr`
- full game engine port
- backend control panel
- wallet integration
- CapStash node integration
- music engine
- complex shader system

Those can come later only after the base visual works.
