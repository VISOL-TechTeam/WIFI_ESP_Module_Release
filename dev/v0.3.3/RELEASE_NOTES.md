# ESP_WIFI_MQTT v0.3.3 (archived from v0.3.3)

## Changes
- SoftAP `/sta`: password show/hide (eye) remains available even when the form is locked
- Connect-test stability: stronger MQTT pause / SoftAP disconnect handling to reduce unexpected POWERON_RESET during STA connect tests

## Artifacts
- ESP_WIFI_MQTT-v0.3.3-app.bin — OTA / app partition image
- ESP_WIFI_MQTT-v0.3.3-factory.bin — full flash image
- manifest.json / manifest.sig — signed OTA manifest
- bootloader.bin, partition-table.bin, ota_data_initial.bin
- SHA256SUMS.txt

## Flash
- App-only OTA from previous 1.3.x is fine for these changes
- Factory / full reflash: use ESP_WIFI_MQTT-v0.3.3-factory.bin (4MB flash)

## Archive note (2026-08-06)
- Renamed from **v1.3.3** → **v0.3.3** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Folder path and text manifests/filenames may use `v0.3.3`; binary image internal version strings remain the original build (no rebuild).
- Rewritten `manifest.json` signatures may not verify (archive only — not used for production OTA).
