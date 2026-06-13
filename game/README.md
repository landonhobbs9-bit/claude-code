# Shadowdelve — a Pixel Diablo Lite

A tiny, self-contained action-RPG dungeon crawler. You play a lone **Warrior**
descending floor by floor through a cursed dungeon, hacking down skeletons,
bats, brutes and fire-throwing demons, grabbing gold and potions, and leveling
up with roguelite **boons**.

Everything is one file: **`game/index.html`**. No build step, no assets, no
libraries — all pixel art is drawn procedurally on a `<canvas>`.

## Play

Just open `game/index.html` in any modern browser, or serve the folder:

```bash
cd game
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Controls

**Desktop**
- Move: `WASD` / Arrow keys
- Attack: `Space` or click
- Dash (i-frames): `Shift`
- Drink potion: `Q`

**Mobile / touch** (controls appear automatically on touch devices)
- Left virtual **stick** to move
- **⚔ ATK** to swing your sword
- **DASH** to roll through danger
- **❤** to drink a healing potion

## Features

- Procedurally generated dungeon (rooms + corridors) that grows each floor
- Animated pixel-art warrior with sword-swing, walk cycle, shield & helmet
- 4 enemy types: skeleton, cave bat, brute, ranged demon
- Melee arc combat with knockback, crits, hit-flash and screen shake
- XP/leveling with a choice of randomized boons (damage, lifesteal, crit,
  attack speed, range, vitality, speed, alchemy)
- Gold and potion drops, health/mana HUD bars, kill counter
- Minimap, vignette lighting, floating combat text
- Responsive canvas that adapts to portrait (mobile) and landscape (desktop)

Clear every enemy on a floor to open the glowing **stairs**, then delve deeper.
How far can you go?
