# Copperline TODO

## Immediate next step

Give Codex the contents of `CODEX_MEGA_PROMPT.md` and ask it to begin with Phase 1 only.

Recommended first prompt:

```text
Read README.md, docs/COPPERLINE_SPEC.md, ROADMAP.md, ATTRIBUTION.md, and CODEX_MEGA_PROMPT.md. Begin with Phase 1 only: import/adapt the upstream 1j01/pipes project into this repository as the initial Copperline base. Preserve attribution and license information. Keep the app static and GitHub Pages compatible. Do not apply the Copperline theme yet. Verify local run instructions and update README if needed.
```

## After Phase 1 works

Then use:

```text
Now perform Phase 2 and Phase 3 from CODEX_MEGA_PROMPT.md: apply the Copperline copper/bronze visual theme, remove novelty/random styling, and replace teapot/candy-cane behavior with Copperline relay/coupling nodes. Keep changes small and readable.
```

## After the theme works

Then use:

```text
Now perform Phase 4: add loopback behavior with a tweakable loopConnectionChance. Pipes should occasionally reconnect to existing occupied grid nodes to create clean closed loops and relay junctions. Avoid messy overlaps or broken geometry.
```

## After loopback works

Then use:

```text
Now perform Phase 5 and Phase 6: add lightweight CRT/OBS polish and a stability pass for long-running sessions. Keep it static and GitHub Pages compatible.
```

## Human review checklist

- Does it still load locally?
- Does it look like copper conduits, not rainbow pipes?
- Are loops visible?
- Are relay nodes visible?
- Does the CRT overlay improve the stream vibe?
- Does it run without obvious slowdown?
- Can OBS capture it cleanly?
