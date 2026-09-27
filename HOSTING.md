# Host Nimbus so other devices can open it

Two different products live in this repo. Pick one.

## A. Easy path — standalone HTML (no server)

Use `static-drop/` (includes `index.html` + full `prix.html`). Drag the whole folder, not just one file.

This version is tabs + home + local games + full Prix + settings. It does **not** run the full proxy, vault DB, or Grok auth stack. Prix talks to whatever keys / fallbacks are inside `prix.html`. CloudMoon only works if that site allows the iframe and the device can reach it.

### 1. Netlify Drop (fastest, free)

1. Go to https://app.netlify.com/drop
2. Drag the `static-drop` folder onto the page
3. You get a `https://something.netlify.app` URL
4. Open that URL on any phone / Chromebook / PC

### 2. Cloudflare Pages (free, stays up)

1. Make a GitHub repo, upload this project (or just `static-drop`)
2. https://dash.cloudflare.com → Workers & Pages → Create → Pages
3. Connect the repo
4. Build command: leave empty if you uploaded `static-drop` as the root
5. Output directory: `/` or `static-drop`

### 3. GitHub Pages (free)

1. New GitHub repo
2. Put `static-drop/index.html` at the repo root as `index.html` (or enable Pages on `/docs` and copy the folder there)
3. Settings → Pages → Deploy from branch

### 4. Same Wi-Fi, no account

On the computer that has the files:

```bash
cd static-drop
npx --yes serve -l 3000
```

Then on your phone: `http://COMPUTER_LAN_IP:3000`

Or double-open `nimbus.html` in a browser on that computer. Opening a raw `file://` on another device will not work. You need a URL.

---

## B. Full app (proxy, accounts, store, vault)

This is the Vite + TanStack app in `src/`. It was built for Grok Build / Vercel (`nitro` preset is already `vercel` in `vite.config.ts`).

### Already hosted

If Grok publish is still live:

- https://longbeach-algebra.grok.me

That URL works on any device that can reach it. Custom domain `longbeach-algebra.org` was pending an A record `@ → 64.239.109.1`.

### Deploy yourself to Vercel

1. Install Node 22 and Vercel CLI: `npm i -g vercel`
2. In this folder:

```bash
npm install
npx vercel
```

3. Follow the prompts. Production URL will look like `https://nimbus-xyz.vercel.app`.

You will likely need env vars for auth / database if you want accounts to work outside Grok. Local games and the HUD still work without that.

### Local network (full app)

```bash
npm install
npm run dev
```

Phone on the same Wi-Fi → `http://COMPUTER_LAN_IP:8080`

The firewall on the host PC must allow inbound port 8080.

---

## Which one should you use

| Goal | Use |
|---|---|
| Just open Nimbus on your phone tonight | `static-drop` + Netlify Drop |
| Same Wi-Fi only | `npm run dev` or `serve` |
| Full proxy + accounts like the Grok site | Vercel or keep `*.grok.me` |
| School Chromebook with a filter | A public URL only helps if the host is not blocked |

Do not email yourself a `.html` file and expect Prix / proxy / CloudMoon to behave. Host it.
