# $BLISS

The most seen image in history. Now it's a chart.

A single-file landing page for the $BLISS memecoin — the Windows XP "Bliss" hill,
pixelated live in the browser. No build step, no dependencies.

## Run locally

Just open `index.html`, or serve the folder:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## The hill image

Drop the real Bliss wallpaper in this folder as **`bliss.jpg`**. The page crops it to
cover the viewport, downscales it to a chunky pixel grid, then upscales it crisp —
so it renders as the recognizable hill in an 8-bit style. Until the file exists, the
page falls back to a procedurally drawn hill, so it never looks broken.

Tune the chunkiness with `pixelSize` in the `CONFIG` block (lower = bigger pixels).

## Launch checklist (edit the `CONFIG` block at the bottom of `index.html`)

```js
const CONFIG = {
  contract:  "",            // full mint address once launched
  twitter:   "https://x.com/...",
  pumpfun:   "",            // pump.fun coin url (also used for every Buy button)
  chart:     "",            // dexscreener / pump url for the Chart button
  hillImage: "bliss.jpg",
  pixelSize: 200,
};
```

## Deploy (Vercel)

1. Import this repo at [vercel.com/new](https://vercel.com/new).
2. Framework preset: **Other**. Build command: none. Output dir: `./` (root).
3. Deploy. Add your custom domain under **Settings → Domains**.

It's pure static, so it works on Netlify, Cloudflare Pages, or GitHub Pages too.
