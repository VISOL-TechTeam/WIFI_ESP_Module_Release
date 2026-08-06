# v0.2.3

- SoftAP HTTPS :443 restored (self-signed ECDSA; SAN 192.168.4.1 / 192.168.5.1 / visol.local)
- Fix client APSTA SoftAP/STA same-subnet conflict (portal moves to 192.168.5.1 when STA on 192.168.4.0/24)
- MainAP L2 forward: ARP/BC flood + unicast STA-to-STA (Main AP only)
- Bind MQTT sockets to STA netif on client boards
- Remove WiFi/MQTT retry count from Config UI and firmware (continuous reconnect)
- Flash both MainAP and client ESP with 1.2.3 for STA-to-STA MQTT to PC broker

## Archive note (2026-08-06)
- Renamed from **v1.2.3** → **v0.2.3** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.3`; binary image internal version strings remain the original `1.2.3` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).