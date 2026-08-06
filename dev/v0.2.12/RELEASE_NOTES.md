## v0.2.12
- SoftAP config portal: split tab UI into separate pages (/, /config, /softap, /sta, /mqtt, /powray, /fw, /about)
- Shared CSS/JS via /static/portal.css, /static/common.js (+ page-specific JS); POWRAY JS only on /powray, OTA JS only on /fw
- Shrink s_cfg_page_buf BSS 64KB → 20KB (~44KB saved); keep Edit/lock UX, /api/*, auth cookies, /logo.png
- Captive portal still lands on / (Config page)


## Archive note (2026-08-06)
- Renamed from **v1.2.12** → **v0.2.12** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.12`; binary image internal version strings remain the original `1.2.12` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
