## v1.3.0
- SoftAP HTTPS :443 is redirect-only: TLS accept → 302 to `http://<softap-ip>/…` (path/query preserved); no portal HTML on HTTPS
- SoftAP HTTP :80 still serves the full multipage portal
- Prefer `http://192.168.100.1` (MainAP) / `http://192.168.2.1`; self-signed warning may appear once on https before redirect
- If heap is too low for TLS redirect, :443 is skipped; HTTP portal remains available
