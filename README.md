# RapidSMP – Horror Modpack — Official Site

Promo site for the Minecraft horror modpack **RapidSMP – Horror** (v2.4.0, Minecraft 1.21.4, Fabric).

- **Default language:** English, with a Turkish (TR) toggle in the navbar.
- **Download:** visitors download `downloads/RapidSMP-Horror-2.4.0.zip` directly from the site and import it into the CurseForge app (Create Custom Profile → Import).
- **Trust:** the download section shows the VirusTotal result (0/65) and the file's SHA-256 checksum.

## Updating the pack

When you release a new version:

1. Put the new zip in `downloads/` and update the file name in `index.html` (download + CTA buttons) if it changed.
2. Update `CONFIG` at the top of [js/main.js](js/main.js): `packVersion`, `mcVersion`, `fileSize`, `virustotalUrl` (re-scan the new zip on VirusTotal).
3. Update the SHA-256 shown in `index.html` (get it with `Get-FileHash <zip> -Algorithm SHA256`).
4. If mods changed, edit the `MODS` / `TEXTURE_PACKS` / `SHADERS` arrays in `js/main.js` — every card, count and stat on the site is generated from them.

## Other TODOs

- `CONFIG.discordUrl` in `js/main.js` — add your Discord invite.
- Screenshots live in `assets/screenshots/` (ss-1.webp … ss-4.webp) and are listed in the `GALLERY` array in `js/main.js` — add or replace entries there.

## Run locally

```bash
python -m http.server 8321
```

Then open `http://localhost:8321`.

## Structure

- `index.html` — single-page site (English base text, `data-i18n` keys)
- `css/style.css` — horror theme (black / blood red)
- `js/main.js` — mod/pack data, EN+TR translations, filtering, animations
- `assets/logo.png` — pack logo (extracted from the modpack's profile image)
- `downloads/` — the modpack zip served to visitors
