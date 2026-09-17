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
