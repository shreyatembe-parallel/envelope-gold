# Gullak · Gold Reveal

A tap-to-open envelope → dynamic postcard → swipe-up gold-coin reveal animation.

Open `index.html` in any browser — no build step.

## The flow
1. Compose modal (To / Message / From) — **demo only**.
2. Tap the closed envelope → short beat → it opens.
3. Postcard rises and settles centre; the envelope shrinks & fades away.
4. A gold coin peeks out from behind the postcard.
5. **Swipe up** (touch, mouse-drag, or trackpad) → postcard shrinks/tilts, coin settles on top.
6. Brighter sunburst (slowly rotating) + looping sparkles + final CTA.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire demo (HTML + CSS + JS, self-contained) |
| `Back.svg`, `Middle.svg`, `Bottom.svg` | Envelope body layers |
| `Top-Close.svg`, `Top-Open.svg` | Closed / open flap faces |
| `empty.png` | Empty postcard (dynamic text drawn on top) |
| `gold-coin.png` | The gold coin |
| `.nojekyll` | Tells GitHub Pages to serve all files as-is |

## For the dev team
The script is split into an **Animation Core** and a **Demo Harness**:
- `renderPostcard({ to, message, from })` — paints text + auto-sizes the message by length.
- `playReveal()` — runs tap-to-open → settled.
- `revealGold()` — the swipe-up step.
- `OPEN_PAUSE` — the beat before the envelope opens.

In production, drop the modal and feed real data straight into `renderPostcard(data)`.

## Deploy to GitHub Pages

This folder is a self-contained git repo. Publish it:

```bash
# from inside this folder
git init
git add .
git commit -m "Gold reveal animation"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment**
- Source: **Deploy from a branch**
- Branch: **main** / **/ (root)** → Save

Live at `https://<you>.github.io/<repo>/` within a minute or two.

> GitHub Pages is case-sensitive — the asset filenames in `index.html` match the files
> exactly (e.g. `Top-Close.svg`, `gold-coin.png`), so don't change their casing.
