# TWRPG Toolkit

A static, fan-made toolkit for **TWRPG (TWRPG) v0.76a** — build planner, item codex, and a worked hero guide. Everything was datamined directly from the map (`twrpgv0.76a_eng.w3x`): items, stats, abilities, crafting recipes, and drop tables.

No backend, no database, no build step. Just static HTML files.

## Pages

| File | What it is |
|------|-----------|
| `index.html` | Landing page linking the four tools. |
| `builder.html` | **Build Maker** — pick any of the 32 heroes, fill 5 gear slots (grade-filtered, weapon-type aware), see combined stats + farm list, name it, save locally, and share via link. |
| `boss.html` | **Boss Drops** — every creature's loot table with per-kill rates and tier; search by boss or item. |
| `codex.html` | **Item Codex** — all 501 epic items across Deltirama → Arcana, with stats, recipes, drop mobs + rates, and a click-through crafting tree. |
| `characters.html` | **Characters** — all 37 heroes: skill kit, suggested combo, chain/combo mechanics, and specialty items. |

## How sharing works (no database)

- **Share a build:** the build (hero + item codes + name) is encoded into the URL hash (`#b=…`). The link *is* the data — open it on any device and the exact build reconstructs. Nothing is uploaded.
- **Personal saves:** stored in the browser via `localStorage` (this device only).

## Deploy to GitHub Pages

1. Create a repo and add these files at its root (keep `.nojekyll` — it stops GitHub from reprocessing the files).
2. Push:
   ```bash
   git init
   git add .
   git commit -m "TWRPG toolkit"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
3. Repo → **Settings → Pages** → Source: `Deploy from a branch`, Branch: `main` / `/ (root)` → Save.
4. Site goes live at `https://<you>.github.io/<repo>/` in a minute or two.

Sharing and saving work identically on the live site.

## Notes

- Only external dependency is Google Fonts (loaded via `<link>`); everything else — data included — is inlined, so pages work offline once cached.
- Drop rates shown are **base** per-kill chances; in-game magic-find, party, and boss modifiers raise them.
- Unofficial fan project. Not affiliated with the map's authors. Game content belongs to its creators.
