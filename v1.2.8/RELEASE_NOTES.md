## v1.2.8
- SoftAP LAN: MainAP `192.168.100.1/24`, config portal SoftAP `192.168.2.1/24`
- MQTT MainAP broker example: `mqtt://192.168.100.100`
- APSTA conflict: if STA owns SoftAP /24, portal moves to `192.168.3.1` (alt; not 100.x)
- Password confirm: SoftAP settings only (removed from STA / MQTT; show/hide eye kept)
- GitHub OTA: discover highest semver `vX.Y.Z/` folder on release repo `main` (no Release tags / `/releases/latest`)
- Keep MQTT + SoftAP HTTPS pause during OTA check/install for TLS heap
- HTTPS SAN updated for `192.168.100.1` / `.2.1` / `.3.1`
