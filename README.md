# Doom_demo
Demo of the 1990s video game Doom

MVP — playable corridor shooter

Goal: walk a level in first person and shoot one enemy type.

Functional: first-person movement (keyboard) on a 2D plane; one JSON grid map; wall collision; one enemy that chases; one hitscan weapon that kills; player health with death/restart; win on clear-all or exit trigger; HUD for health/ammo.

Technical (stack-specific):

Rendering: Canvas2D software raycaster (DDA grid traversal, vertical wall columns, flat shading).
Fixed-timestep loop (accumulator) with requestAnimationFrame; input via keyboard events.
Map + entity state in plain TS structs/arrays; Vite dev server; a couple of Vitest unit tests for the raycaster math and collision.

Done when: npm run dev, move around, shoot/kill enemies, take damage, win or lose in the browser.

# Iteration 1 — visual & content fidelity

Goal: the recognizable Doom look and level vocabulary.

Functional: textured walls/floors/ceilings; sector-based map (variable floor/ceiling heights, steps, pits); billboarded animated sprite enemies/items; doors, switches, lifts, keycards; multiple enemy and weapon types; pickups (ammo/health/armor); distance light falloff and per-sector light levels; sound effects + music; menu and multi-level progression.

Technical:

First rendering upgrade: move to WebGL2. Render walls/floors as textured columns/quads and sprites as camera-facing billboards from a texture atlas; do distance shading in the fragment shader. (Software texturing in JS won't hold framerate — this is the reason to jump to the GPU now.)
Extend the map format from grid to sectors + linedefs (JSON); write a small loader.
Web Audio API for SFX/music with a simple asset loader; sprite animation via atlas frame tables.

Done when: a textured, lit, multi-room level with doors, keys, several enemy/weapon types, and sound plays end to end.
