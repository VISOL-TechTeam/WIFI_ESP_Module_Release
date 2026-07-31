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
