# v0.2.1

- SoftAP portal logo inline (captive-safe), About: Visol Inc / Since 2026 / License
- Manual FW upload (app.bin) on settings FW tab
- Fix Check Latest Tmr Svc stack overflow; manifest raw-first fallback
- SoftAP STA session / OTA auth and portal UX fixes


## Archive note (2026-08-06)
- Renamed from **v1.2.1** → **v0.2.1** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.1`; binary image internal version strings remain the original `1.2.1` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
