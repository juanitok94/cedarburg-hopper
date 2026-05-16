# Cedarburg Hopper — Claude Code Project Brief
> John Kean · Peachy Kean DevOps LLC · Asheville, NC
> Last updated: May 15, 2026

## What This Is
Cedarburg Hopper is a mobile-first digital walking passport
for Washington Avenue, Cedarburg, Wisconsin. 10 stops,
south to north. Users walk the avenue, stamp each stop,
discover a hidden collection. No auth, no login,
localStorage only.

## Live URLs
- Production: cedarburg-hopper.vercel.app
- Repo: github.com/juanitok94/cedarburg-hopper
- Local: localhost:3000 (npm run dev in C:\cedarburg-hopper)

## Tech Stack
- Next.js App Router
- TypeScript (strict)
- Tailwind CSS 4
- localStorage for all user state
- Static JSON data files (no database)
- Vercel for deployment (auto-deploy on git push)

## Design Principles — Non-Negotiable
1. Hygge — warmth, slowness, belonging
2. Camino — journey, earned progress, south to north
3. Krug — don't make me think, clarity first
4. Mobile-first — primary user is holding a phone
   on Washington Avenue. Desktop is graceful enhancement only.
5. Human first — if it feels like a generic app,
   it's wrong. It should feel like Cedarburg.

## Color System — Do Not Change
- Parchment background: #FAF6F0  (--color-parchment)
- Espresso dark:        #2A1810  (--color-espresso)
- Gold accent:          #B8893A  (--color-gold)
- Rust primary:         #8B3A2E  (--color-rust)
- Ink body text:        #1F1A14  (--color-ink)
- Sage secondary:       #7A8B6E  (--color-sage)

## Typography — Do Not Change
- Playfair Display — headings (font-serif)
- Crimson Pro — body text (font-serif)
- IBM Plex Mono — labels, UI elements (font-mono)

## Two ICPs
1. TOURISTS — visiting Cedarburg, want authentic small-town
   Wisconsin character, not chains, not tourist traps.
   Respond to discovery, walking, feeling like an insider.
2. BUSINESS OWNERS — independent shop owners on Washington Ave
   who want foot traffic and to feel proud of being
   featured, not marketed at.

## The Route
Washington Avenue runs south to north through historic
downtown Cedarburg. The Covered Bridge divides the route
into two zones.

### Zone 1 — South of the Bridge (stops 1–5)
| # | Stop |
|---|------|
| 1 | C. Wiesler's Tavern |
| 2 | Cedarburg Cultural Center |
| 3 | Union House |
| 4 | Rivoli Theatre |
| 5 | Handen Distillery |

### Zone 2 — The Mill End (stops 6–10)
| # | Stop |
|---|------|
| 6 | Cedarburg Coffee Roastery |
| 7 | Fiddleheads Coffee |
| 8 | The Stilt House |
| 9 | Cedarburg Art Museum |
| 10 | Cedar Creek Winery |

## The Mill Five
A hidden collection flagged in shops.json (`"hygge": true`).
Not yet wired into the UI. Do not modify hygge flags
in shops.json without confirming with John first.

## File Structure
src/
  app/
    page.tsx          — homepage
    map/page.tsx      — interactive map
    passport/page.tsx — stamp collection
    stop/[slug]/      — individual stop pages
    globals.css       — design tokens and base styles
    layout.tsx        — root layout, metadata, fonts
  data/
    shops.json        — canonical data, source of truth
    layers.json       — map filter layers
    badges.json       — achievement badges
    trivia.json       — trivia questions per stop
  lib/
    stamps.ts         — localStorage stamp logic

## Standing Rules for Claude Code
1. Always check TypeScript compiles before finishing
   (npx tsc --noEmit)
2. Never modify shops.json stop numbers or core/bonus
   status without explicit confirmation from John
3. Never change colors, fonts, or design tokens
4. Mobile-first — test layout at 390px width thinking
5. Always localhost review before git push
6. Commit message format:
   feat: for new features
   fix: for corrections
   refactor: for restructuring

## Current Build Status (May 15, 2026)
- ✅ Homepage with zone labels and hero copy
- ✅ Passport page
- ✅ Stop pages (individual)
- ✅ Map page
- ✅ Color tokens in globals.css
- ✅ Metadata: title and description
- ✅ stamp.welcomeLine and stamp.subLine for anchor stops
   (Wiesler's, Rivoli, Cedar Creek Winery)
- ⬜ stamp copy for remaining stops
- ⬜ The Mill Five wired into UI
- ⬜ BottomNav
- ⬜ Shop photos
- ⬜ Progress visualization on passport page
- ⬜ Dark mode (post user testing)

## Photo Library
Photos location: public/images/shops/
Naming convention: {shop-id}-exterior.jpg,
{shop-id}-interior.jpg, {shop-id}-interior-2.jpg
All shop photos still needed.
