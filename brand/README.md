# 🎨 Brand assets

Source files and exports for Card Vault. Every asset is built in HTML/CSS with the same design tokens as the website, so the identity stays pixel-consistent across the site, the token image and the social accounts.

**No official card artwork is used anywhere.** The identity is entirely original: Archivo Black wordmark, halftone screentone, ink-red accent. Reproducing publisher artwork on an avatar or banner is the fastest way to create an IP problem, and it is not necessary — see [README §13](../README.md#13--branding).

---

## Assets

| File | Size | Used for |
|---|---|---|
| `avatar.png` | 1000×1000 | **Pump.fun token image, Telegram channel photo, X profile picture** |
| `avatar-dark.png` | 1000×1000 | Alternative avatar, inverted (ink ground) |
| `x-header.png` | 1500×500 | X header |

One avatar covers all three platforms. Telegram and X crop it to a circle; the design is built to survive that crop.

### Why the light avatar is the default

Legibility was tested at 160 / 96 / 64 / 32 px with a circle crop applied. The ink-on-paper version holds the highest contrast at 32px, and because Pump.fun, Telegram and X are usually viewed in dark mode, a light avatar separates from the background instead of merging into it.

A card-silhouette concept was also tested and rejected: below 64px the card collapses into an unreadable rectangle.

---

## Design tokens

Identical to the website.

```
paper   #E9E7E2      ink     #0A0A0A
deep    #DFDCD5      soft    #55524C
rule    #C5C1B8      seal    #C41E1E

display   Archivo Black
body      Archivo
data      IBM Plex Mono
```

---

## Re-exporting

Assets render through headless Chrome at exact pixel dimensions. Edit the `.html` source, then re-export.

```bash
chrome --headless --disable-gpu --no-sandbox --hide-scrollbars --force-device-scale-factor=1 --virtual-time-budget=8000 --screenshot=avatar.png --window-size=1000,1000 file:///ABSOLUTE/PATH/brand/avatar.html
```

Notes:

* `--force-device-scale-factor=1` keeps output at exactly `--window-size`.
* `--virtual-time-budget=8000` gives Google Fonts time to load. Without it, Archivo Black falls back to Impact and the mark renders wrong.
* Chrome may refuse to write into a protected directory. Render to a temporary path and copy the file back.

---

## Still open

* X header safe zone assumes the profile picture overlaps the lower left. Check on a real profile before locking it.
* No favicon yet — derive it from `avatar.html` at 512×512 and 180×180 if the site needs one.
