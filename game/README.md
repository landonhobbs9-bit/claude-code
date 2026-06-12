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
- Tap the purple **skill runes** (arc above the attack rune) to use warrior moves.
- Tap the blue **✚ flask** to drink a healing potion.
- Tap the **🎒 bag** (top-right) to open the Character screen.

**Desktop**
- **WASD** / arrow keys to move.
- **Space** or **click** to attack (auto-aims at the nearest enemy or your cursor).
- **1–4** to use unlocked warrior skills.
- **Q** to drink a potion.
- **C** (or I / B) to open the Character screen, **Esc** to close.

## Gameplay

- Descend through procedurally generated crypts. Each floor is a new layout of
  rooms and corridors.
- Slay **skeletons** and **demon imps**. Every 4th depth spawns a **Crypt Lord** boss.
- Clear all enemies on a floor to automatically **descend** to the next, deeper level.
- Collect **gold**, crack open **chests**, and grab **potions**.
- Gain **XP** and **level up** — more max HP, full heal, and stronger attacks.
- Enemies scale with depth. See how far down you can go before you die.

## Loot & gear

- Enemies, chests, and bosses drop **randomized gear** that glows by rarity:
  **Common** → **Magic** → **Rare** → **Epic** → **Legendary**. Better rarities
  drop more often as you descend.
- Each item rolls a base stat for its slot plus random **affixes** (more affixes
  at higher rarity): Damage, Max HP, Armor, Crit, Attack/Move Speed, Life on Hit,
  and XP Gain.
- There are **7 equipment slots**: weapon, helmet, chest, gloves, boots, ring,
  amulet. Equipped stats are aggregated into your character (armor reduces damage
  taken, attack speed lowers your swing cooldown, etc.).
- Picked-up gear goes into a **limited bag** (24 slots). If the bag is full, loot
  stays on the ground until you make room.

### Character screen

Open it with the 🎒 button (or `C`). From here you can:
- See all your **derived stats**.
- Inspect any **equipped** item and **Unequip** it.
- Inspect any **bag** item, compare it against what's equipped, then **Equip** or
  **Discard** it. Equipping swaps the old item back into your bag.

## Warrior moves

As you level, you learn new Diablo/PoE-style abilities (each on a cooldown):

| Level | Move | Effect |
|------:|------|--------|
| 3 | 🌀 **Whirlwind** | Spin, striking every enemy around you |
| 5 | 💨 **Charge** | Dash forward, smashing and knocking back enemies |
| 7 | 💥 **Ground Slam** | Shockwave: AoE damage + heavy knockback |
| 9 | 📣 **War Cry** | +60% damage for 6s and an instant partial heal |

## Tech notes

- Single self-contained file: `index.html` (markup, CSS, and game logic).
- Fixed-timestep-ish `requestAnimationFrame` loop with delta clamping.
- Axis-separated circle-vs-tilemap collision so you slide along walls.
- Sprites are defined as tiny ASCII grids + palettes and rasterized to cached
  offscreen canvases, rendered with `image-rendering: pixelated`.
