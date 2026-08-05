## v1.3.2
- SoftAP client connected: STA "scan nearby APs" uses SoftAP-safe scan (passive + home channel dwell, non-blocking) so the portal stays up
- During portal scan, SoftAP hold disconnect is deferred to avoid RF spike / POWERON_RESET
- Scan API returns clear JSON errors; STA page shows progress/failure messages (no silent fail)
- Empty STA SSID: never `esp_wifi_connect()` / retry — SoftAP portal-only mode (stops NO_AP_FOUND spam)
- Static portal JS/CSS served with `Cache-Control: no-cache`; VIA_SOFTAP injected before script load
- Flash size remains **4MB**
