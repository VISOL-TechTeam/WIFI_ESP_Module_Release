## v0.2.6
- POWRAY TEST UI cleanup (details toggle; hide topics/MAC/hex by default)
- A9 status parse/display fix; MQTT disconnect on status request fixed (CMD loopback + no binary printf)
- Compact dimming grid; auto CONT 0% on tab leave / page unload
- Password show/hide + confirm on SoftAP / STA / MQTT (+ login eye)
## v1.2.5
- SoftAP HTTPS stabilization, POWRAY TEST wrap/A9 parse/dim-boost UI
## v1.2.4
- SoftAP POWRAY TEST tab (MQTT CONT_ALL/CMD/A9/diagnostics)
## v1.2.3
- SoftAP HTTPS :443, APSTA IP conflict fix, MainAP ARP L2 forward, continuous reconnect

## v1.2.2
- SoftAP STA↔STA L2 forward so ESP clients on MainAP SoftAP can reach PC MQTT broker

## v1.2.1
- SoftAP logo inline, About Visol Inc, web app.bin upload, Check Latest crash fix

## Archive note (2026-08-06)
- Renamed from **v1.2.6** → **v0.2.6** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.6`; binary image internal version strings remain the original `1.2.6` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).