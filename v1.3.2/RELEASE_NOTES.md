## v1.3.2
- SoftAP client connected: STA "scan nearby APs" uses SoftAP-safe scan (passive + home channel dwell, non-blocking)
- During portal scan, SoftAP hold disconnect is deferred; SCAN_DONE race fixed; connecting STA aborted before scan so WIFI_STATE does not block SoftAP portal scan
- Connect-test sends explicit `application/x-www-form-urlencoded` body; clearer start/result logs
- Static portal JS Cache-Control no-cache + `?v=1.3.2` cache-bust; VIA_SOFTAP injected before scripts
- Empty STA SSID: never `esp_wifi_connect()` / retry (SoftAP portal-only)
- Flash size remains **4MB**
