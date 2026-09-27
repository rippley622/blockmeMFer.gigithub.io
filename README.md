# Nimbus

Private browser HUD: cloaked tabs, panic cover, local games, Prix, CloudMoon iframe, accounts.

This folder is the Nimbus project only. Grok Build skills, screenshots, `.vercel` build output, and workspace junk were stripped.

## What’s in here

| Path | What it is |
|---|---|
| `src/` | Real app (React + TanStack Start) |
| `public/` | Cloaks, store icons, standalone HTML copies |
| `scripts/` + `server/` + `migrations/` | Build, deploy middleware, auth/vault SQL |
| `nimbus.html` | One-file hub. Drop this anywhere. |
| `prix.html` | Full Prix chat UI (also `src/apps/prix.html` and `public/prix.html`) |
| `cloudmoon.html` / `open-cloudmoon.html` | Iframe wrapper for CloudMoon |
| `static-drop/` | Ready-to-host folder (`index.html` = hub, `prix.html` = full Prix) |
| `nimbus-catchup.md` | Short project brief |

Live Grok URL (if still up): https://longbeach-algebra.grok.me

## Run the full app locally

Needs Node 22+.

```bash
npm install
npm run dev
```

Dev server binds `0.0.0.0:8080`. On the same Wi-Fi, other devices open:

```
http://YOUR_COMPUTER_LAN_IP:8080
```

Find that IP on Windows with `ipconfig`, on Mac/Linux with `ifconfig` or `ip addr`.

## Host it so phones / other PCs can open it

See `HOSTING.md`.
