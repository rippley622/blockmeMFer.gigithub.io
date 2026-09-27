# Nimbus — catch-up for Grok

Paste this into Grok on the Chromebook so it knows the project. This is a summary, not the full repo.

## What this is

**Nimbus** is a web app (Vite + React + TanStack Router). The user (Kevin) has been building it in Grok Build.

Published URL: `https://longbeach-algebra.grok.me`  
Custom domain in progress: `longbeach-algebra.org` (Grok Domain tab, **Pending verification**). To finish: at the registrar, add A record, name `@`, value `64.239.109.1`, then refresh verification.

## What to keep working on

These parts are in-bounds:

- **Prix** — in-app AI chat (Grok-like UI). Still in development; show a notice that it may not work well on the live site. User wants Prix to feel like Grok (streaming, thinking steps, not the same reply every time). Prix HTML lives as an in-app page (`/prix.html`).
- **Local games** that run in the app with no outside site: 2048, Snake, Dino, Mines, Clicker.
- **Home / HUD** — search bar, tiles, theme colors (accent, bg, panel), optional wallpaper image, bookmarks.
- **Account** — email + password and Google sign-in in the app. Developer account is `kjhamelburg@gmail.com`.
- **CloudMoon HTML** — a tiny standalone page that only iframes `https://web.cloudmoonapp.com/`. It is not a copy of CloudMoon. If the iframe is blank, CloudMoon is blocking frames or the network cannot reach that host. User has `cloudmoon.html` for this.

## What Chromebook Grok cannot do

- It does not have this Grok Build workspace, so it cannot edit the live Nimbus code unless the user pastes files.
- A single HTML file cannot recreate CloudMoon’s games (those need CloudMoon’s servers).
- Prix needs a reachable AI API; opening a local file often breaks fetch.

## How the user talks to you

Keep replies short. They iterate fast: “fix this”, screenshots, then the next feature. Prefer changing the existing app over new architecture.

If they ask you to write code, they will need to paste files from the project or keep using Grok Build for the real repo.

## Suggested next work (if they ask “what next”)

1. Prix reliability and UI (thinking steps, fewer repeat answers).
2. Polish local games and home tiles.
3. Theme / wallpaper / bookmarks.
4. Explain DNS in general if they are learning domains (A record, `@`, registrar vs Grok).

Do not assume extra features beyond what is listed here unless the user asks.
