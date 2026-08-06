# v0.2.4

- SoftAP portal **POWRAY TEST** tab (same MQTT topics/payloads as WIFI_MQTT_Test_Tool)
- Controls: Broadcast CONT_ALL, Single CONT_CMD, Status Request (A9)
- Diagnostics: ALIVE / RSSI / IP / SUB_TOPICS on Devices/Broadcast
- Shows MQTT connected status; send disabled when disconnected
- Flash MainAP and client boards with 1.2.4 for portal testing


## Archive note (2026-08-06)
- Renamed from **v1.2.4** → **v0.2.4** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.4`; binary image internal version strings remain the original `1.2.4` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).