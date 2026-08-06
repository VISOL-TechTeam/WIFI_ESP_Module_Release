# ESP_WIFI_MQTT v0.0.0 (archived from v0.0.0)

Settings-page GitHub OTA (check/install/status) when STA has internet; SoftAP HTTPS disabled to avoid mbedtls heap OOM.

Built from Visol_WIFI_Module_V_ESP @ e6fd640.

## Archive note (2026-08-06)
- Renamed from **v1.0.0** → **v0.0.0** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.0.0`; binary image internal version strings remain the original `1.0.0` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
