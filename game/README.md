# Shadow Crypt — a Diablo·Lite pixel ARPG

A tiny top-down dungeon crawler starring a pixel-art **warrior**. Pure HTML5
canvas, zero dependencies, zero external assets — every sprite is drawn
procedurally. Built to be **mobile-friendly** (touch joystick + buttons) while
still playing well with mouse + keyboard on desktop.

## Play

Just open `index.html` in any modern browser — phone or desktop.

Or serve it locally:

```bash
cd game
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Controls

**Mobile / touch**
- Drag the **left half** of the screen to move (a virtual joystick appears).
- Tap the red **⚔ rune** (bottom-right) to attack.
- Tap the blue **✚ flask** to drink a healing potion.

**Desktop**
- **WASD** / arrow keys to move.
- **Space** or **click** to attack (auto-aims at the nearest enemy or your cursor).
- **Q** to drink a potion.

## Gameplay

- Descend through procedurally generated crypts. Each floor is a new layout of
  rooms and corridors.
- Slay **skeletons** and **demon imps**. Every 4th depth spawns a **Crypt Lord** boss.
- Clear all enemies on a floor to automatically **descend** to the next, deeper level.
- Collect **gold**, crack open **chests**, and grab **potions**.
- Gain **XP** and **level up** — more max HP, full heal, and stronger attacks.
- Enemies scale with depth. See how far down you can go before you die.

## Tech notes

- Single self-contained file: `index.html` (markup, CSS, and game logic).
- Fixed-timestep-ish `requestAnimationFrame` loop with delta clamping.
- Axis-separated circle-vs-tilemap collision so you slide along walls.
- Sprites are defined as tiny ASCII grids + palettes and rasterized to cached
  offscreen canvases, rendered with `image-rendering: pixelated`.
