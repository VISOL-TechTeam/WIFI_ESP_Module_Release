# ESP_WIFI_MQTT v1.3.3

## Changes
- SoftAP `/sta`: password show/hide (eye) remains available even when the form is locked
- Connect-test stability: stronger MQTT pause / SoftAP disconnect handling to reduce unexpected POWERON_RESET during STA connect tests

## Artifacts
- ESP_WIFI_MQTT-v1.3.3-app.bin — OTA / app partition image
- ESP_WIFI_MQTT-v1.3.3-factory.bin — full flash image
- manifest.json / manifest.sig — signed OTA manifest
- bootloader.bin, partition-table.bin, ota_data_initial.bin
- SHA256SUMS.txt

## Flash
- App-only OTA from previous 1.3.x is fine for these changes
- Factory / full reflash: use ESP_WIFI_MQTT-v1.3.3-factory.bin (4MB flash)
