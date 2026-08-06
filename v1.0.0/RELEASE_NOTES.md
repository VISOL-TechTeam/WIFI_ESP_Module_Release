# ESP_WIFI_MQTT v1.0.0

## Summary
- First **production** mainline release **1.0.0**.
- Functionally continues the former development line **v1.3.3** (SoftAP `/sta` password eye when locked; connect-test harden).
- Historical public **1.x.x** folders were renamed to **0.x.x** and archived under [`dev/`](../dev/).

## Changes (from former 1.3.3)
- SoftAP `/sta`: password show/hide (eye) available even when the form is locked
- Connect-test stability: stronger MQTT pause / SoftAP disconnect handling (fewer unexpected POWERON_RESET)
- Flash **4MB**

## Versioning note
- Devices using GitHub folder OTA only scan **root** `vX.Y.Z/` directories; archived builds under `dev/` are not selected for "latest".
- Binary images in `dev/` archives keep their original embedded app version strings (folder/manifest names only were rebased).

## Artifacts
- `ESP_WIFI_MQTT-v1.0.0-app.bin` — OTA / app partition image
- `ESP_WIFI_MQTT-v1.0.0-factory.bin` — full flash image
- `manifest.json` / `manifest.sig` — signed OTA manifest
- `bootloader.bin`, `partition-table.bin`, `ota_data_initial.bin`
- `SHA256SUMS.txt`

## Flash
- App-only OTA from previous 1.3.x is fine for these changes
- Factory / full reflash: use `ESP_WIFI_MQTT-v1.0.0-factory.bin` (4MB flash)
