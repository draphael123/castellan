# Castellan 🏰

A 3D fantasy castle-kingdom builder. Raise a kingdom, grow your population — and hold the walls when the raiders come.

**Play:** https://castellan.vercel.app (single file, no build step)

## Phase 1 (current)

- 3D fantasy city builder — Three.js, single `index.html`, no dependencies beyond a CDN import
- 10 building types: Keep, House, Farm, Lumber Camp, Quarry, Gold Mine, Storehouse, Barracks, Archer Tower, Wall
- Living economy: wood / stone / gold / food, population growth tied to housing + food, tax income, starvation
- **Raids**: once your population reaches 10, raiding parties march on your keep — each raid bigger and tougher than the last
- Defense: barracks train soldiers (auto-respawn), towers shoot arrows, walls physically block raiders (who then batter them down)
- **Loot** for every raider slain + a bonus haul for each raid repelled
- Wandering villagers, floating loot popups, WebAudio sound, autosave to localStorage

## Controls

| Input | Action |
|---|---|
| WASD / arrows | Pan camera |
| Q / E, middle-drag | Rotate |
| Scroll | Zoom |
| 1–9 | Select building |
| Click | Place |
| X | Demolish (40% refund) |
| Esc / right-click | Cancel |

## Roadmap

- **Phase 2 — Barracks expansions:** upgrade tiers (better soldiers, more slots), soldier types (pikemen, archers, knights)
- **Phase 3 — Invasions:** send your army to raid enemy territories for loot (timer-resolved at first, then playable battles)
- Walls with gates, rally flags, difficulty curve tuning, day/night, bigger raid variety (siege units, flankers)

## Dev

```bash
python -m http.server 5722 -d .
```

Debug handle in the console: `CS.step(dt,n)`, `CS.grant()`, `CS.raid(true)`, `CS.place(type,cx,cz)`, `CS.shot({tx,tz,yaw,dist})` → JPEG dataURL (drives the sim headlessly; rAF pauses in background tabs).
