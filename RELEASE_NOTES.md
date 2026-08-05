> 제품은 POWRAY와 연동합니다. 권장 POWRAY FW: **≥ 1.4.6**. SoftAP 포털·플래시 안내는 [README.md](README.md).

## Tools
- Refresh `Tools/Visol_WIFI_Module_FW_Uploader.exe` from firmware repo `tools/gui_updater` (latest GUI build)

## v1.3.2
- SoftAP-safe STA nearby AP scan; empty STA SSID = portal-only (no connect loop)
- **Scan zero-reaction fix:** Scan/Test stay clickable without Edit; HIT serial logs; sta.js fallback; HTTP sockets 4; JS `?v=1.3.2a`
- Flash **4MB** — refresh/overwrite of `v1.3.2/` artifacts

## v1.3.1
- SoftAP client join: STA disconnect deferred off the WiFi event handler (esp_timer)
- SoftAP-up STA reconnect backoff + portal TX power relief
- Fixes POWERON_RESET / unusable SoftAP portal when STA has no AP (e.g. reason=201) and phone joins SoftAP
- Prefer `http://192.168.2.1` (portal) / `http://192.168.100.1` (MainAP)
- Rebuild: flash size corrected to **4MB** (image header was wrongly 16MB). Requires **full/factory reflash** — app-only OTA will not fix bootloader/image header mismatch.

## v1.3.0
- SoftAP HTTPS :443 is redirect-only: TLS accept → 302 to `http://<softap-ip>/…` (path/query preserved); no portal HTML on HTTPS
- SoftAP HTTP :80 still serves the full multipage portal
- Prefer `http://192.168.100.1` (MainAP) / `http://192.168.2.1`; self-signed warning may appear once on https before redirect
- If heap is too low for TLS redirect, :443 is skipped; HTTP portal remains available

## v1.2.12
- SoftAP config portal: split tabs into pages (/config /softap /sta /mqtt /powray /fw /about)
- Shared /static CSS/JS; CFG page BSS 64KB→20KB (~44KB saved)
- Keep Edit/lock, APIs, auth, /logo.png; captive portal → /

## v1.2.11
- Fix POWRAY A9 status: frame[2:3] is model (not GroupID); Device ID at [4:5]; GroupID from MQTT config (was showing model e.g. 24 as GroupID)
- SoftAP HTTPS: single TLS session, shorter handshake timeout; quiet captive-portal CONN_EOF/timeout ERROR spam (HTTP :80 unchanged)

## v1.2.10
- POWRAY A9 status: ID/GroupID (frame Group[2]+ID[2]); current Current1..3 deci-amps (e.g. 418 → 41.8A)
- ALIVE / RSSI / IP results shown inline under diagnosis buttons
- Remove SUB_TOPICS button from POWRAY TEST
- MQTT connected box lists SUB1 Broadcast, SUB2 CMD, SUB3 System, PUB1 System_R, PUB2 Data

## v1.2.9
- Fix critical `uart1_j1_rx` stack overflow on POWRAY TEST status (0xA9) when MQTT + SoftAP HTTPS are active
- Move UART RX large buffers / MQTT pub scratch / protocol parse+TX buffers off the RX task stack (BSS)
- Defer POWRAY status/hex parsing to `mqtt_pub_task`; increase `uart1_j1_rx` stack 6KB → 8KB

## v1.2.8
- SoftAP LAN: MainAP `192.168.100.1/24`, config portal SoftAP `192.168.2.1/24`
- MQTT MainAP broker example: `mqtt://192.168.100.100`
- APSTA conflict: if STA owns SoftAP /24, portal moves to `192.168.3.1` (alt; not 100.x)
- Password confirm: SoftAP settings only (removed from STA / MQTT; show/hide eye kept)
- GitHub OTA: discover highest semver `vX.Y.Z/` folder on release repo `main` (no Release tags / `/releases/latest`)
- Keep MQTT + SoftAP HTTPS pause during OTA check/install for TLS heap
- HTTPS SAN updated for `192.168.100.1` / `.2.1` / `.3.1`

## v1.2.7
- SoftAP LAN: MainAP `192.168.1.1/24`, config portal SoftAP `192.168.2.1/24`
- APSTA conflict: if STA owns SoftAP /24, portal moves to `192.168.3.1` (alt)
- HTTPS SAN updated for new SoftAP IPs; MQTT MainAP broker examples `192.168.1.x`
- GitHub OTA check/install: temporarily stop MQTT + SoftAP HTTPS to free TLS heap
- mbedTLS `SSL_IN_CONTENT_LEN=8192`, dynamic free config; clearer `tls_oom` errors

## v1.2.6
- POWRAY TEST UI cleanup (details toggle; hide topics/MAC/hex by default)
- A9 status parse/display fix; MQTT disconnect on status request fixed (CMD loopback + no binary printf)
- Compact dimming grid; auto CONT 0% on tab leave / page unload
- Password show/hide + confirm on SoftAP / STA / MQTT (+ login eye)
## v1.2.5
- SoftAP HTTPS stabilization, POWRAY TEST wrap/A9 parse/dim-boost UI
## v1.2.4
- SoftAP POWRAY TEST tab (MQTT CONT_ALL/CMD/A9/diagnostics)
## v1.2.3
- SoftAP HTTPS :443, APSTA IP conflict fix, MainAP ARP L2 forward, continuous reconnect

## v1.2.2
- SoftAP STA↔STA L2 forward so ESP clients on MainAP SoftAP can reach PC MQTT broker

## v1.2.1
- SoftAP logo inline, About Visol Inc, web app.bin upload, Check Latest crash fix
