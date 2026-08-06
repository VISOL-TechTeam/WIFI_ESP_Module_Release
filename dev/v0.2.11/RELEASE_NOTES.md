## v0.2.11
- Fix POWRAY A9 status: frame[2:3] is model (not GroupID); Device ID at [4:5]; GroupID from MQTT config (was showing model e.g. 24 as GroupID)
- SoftAP HTTPS: single TLS session, shorter handshake timeout; quiet captive-portal CONN_EOF/timeout ERROR spam (HTTP :80 unchanged)

## Archive note (2026-08-06)
- Renamed from **v1.2.11** → **v0.2.11** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.11`; binary image internal version strings remain the original `1.2.11` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
