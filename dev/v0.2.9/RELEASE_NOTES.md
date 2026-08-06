## v0.2.9
- Fix critical `uart1_j1_rx` stack overflow on POWRAY TEST status (0xA9) when MQTT + SoftAP HTTPS are active
- Move UART RX large buffers / MQTT pub scratch / protocol parse+TX buffers off the RX task stack (BSS)
- Defer POWRAY status/hex parsing to `mqtt_pub_task`; increase `uart1_j1_rx` stack 6KB → 8KB

## Archive note (2026-08-06)
- Renamed from **v1.2.9** → **v0.2.9** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.9`; binary image internal version strings remain the original `1.2.9` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).