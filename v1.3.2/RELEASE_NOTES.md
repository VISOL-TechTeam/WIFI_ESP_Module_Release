## v1.3.2
- SoftAP client connected: STA "scan nearby APs" uses SoftAP-safe scan (passive + home channel dwell, non-blocking)
- During portal scan, SoftAP hold disconnect is deferred; SCAN_DONE race fixed; connecting STA aborted before scan so WIFI_STATE does not block SoftAP portal scan
- Connect-test sends explicit `application/x-www-form-urlencoded` body; clearer start/result logs
- **Fix scan zero-reaction:** SoftAP STA page no longer disables Scan/Test/Edit buttons (disabled = silent click, no serial). Scan and connect-test work **without Edit**; empty STA SSID OK
- UI feedback via status box (captive browsers often block `alert`); sta.js load-fail fallback; JS `?v=1.3.2a`; HTTP portal sockets 4
- Serial: `HIT POST /api/wifi/scan` on every scan HTTP hit (before auth); `GET /sta softap=` inject log
- Empty STA SSID: never `esp_wifi_connect()` / retry (SoftAP portal-only)
- Flash size remains **4MB** — overwrite refresh of v1.3.2 artifacts
