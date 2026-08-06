# v0.2.2

- SoftAP STA↔STA L2 forwarding: other SoftAP clients (e.g. ESP B) can reach PC MQTT broker on MainAP LAN
- Doc/MainAP.md: STA↔STA root cause, firmware fix, topology alternatives
- Version bump to 1.2.2

## Archive note (2026-08-06)
- Renamed from **v1.2.2** → **v0.2.2** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.2`; binary image internal version strings remain the original `1.2.2` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
