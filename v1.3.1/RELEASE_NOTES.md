## v1.3.1
- SoftAP client join: STA disconnect is deferred (esp_timer) instead of calling `esp_wifi_disconnect` inside the WiFi event handler
- While SoftAP is up, STA reconnect uses backoff so full-band scans do not starve the portal
- SoftAP portal session: slightly lower TX power; restore when SoftAP is idle
- Fixes unexpected `POWERON_RESET` / unusable Config portal when STA cannot find AP (e.g. reason=201) and phone joins SoftAP
- Prefer `http://192.168.2.1` (portal) / `http://192.168.100.1` (MainAP)
- **Rebuild:** flash size corrected to **4MB** (was wrongly 16MB in image header). Requires **full/factory reflash** — app-only OTA will not fix bootloader/image header mismatch.
