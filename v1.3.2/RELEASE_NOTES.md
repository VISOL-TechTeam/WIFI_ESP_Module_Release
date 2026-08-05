# ESP WIFI MQTT Firmware v1.3.2 (4MB)

## SoftAP portal JS inline (captive fix)

Phone SoftAP/captive browsers often fetch only the HTML (GET /sta) and never issue a second GET for /static/sta.js (same class of failure as logo). Refresh does not help if the browser never requests JS.

**Fix:** SoftAP responses embed common.js + page JS in the same HTTP response (chunked after HTML). Scan/Test handlers work with a single GET. STA-IP access still uses /static/*.js. CFG_PAGE_BUF stays 20KB (HTML only).

Also: SoftAP-safe STA scan, empty-SSID connect block, HIT logs for WiFi APIs and GET /static/*.

## Artifacts

- `ESP_WIFI_MQTT-v1.3.2-app.bin` — OTA @ 0x20000
- `ESP_WIFI_MQTT-v1.3.2-factory.bin` — full flash @ 0x0 (4MB layout)
- `bootloader.bin`, `partition-table.bin`, `ota_data_initial.bin`
- `manifest.json` + `manifest.sig`, `SHA256SUMS.txt`

Flash size: **4MB**. Dual OTA partitions.
