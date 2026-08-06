## v0.3.0
- SoftAP HTTPS :443 is redirect-only: TLS accept → 302 to `http://<softap-ip>/…` (path/query preserved); no portal HTML on HTTPS
- SoftAP HTTP :80 still serves the full multipage portal
- Prefer `http://192.168.100.1` (MainAP) / `http://192.168.2.1`; self-signed warning may appear once on https before redirect
- If heap is too low for TLS redirect, :443 is skipped; HTTP portal remains available

## Archive note (2026-08-06)
- Renamed from **v1.3.0** → **v0.3.0** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.3.0`; binary image internal version strings remain the original `1.3.0` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).