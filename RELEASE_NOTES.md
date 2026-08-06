> 제품은 POWRAY와 연동합니다. 권장 POWRAY FW: **≥ 1.4.6**. SoftAP 포털·플래시 안내는 [README.md](README.md).

## Version policy (2026-08-06)
- **Production mainline:** root [`v1.0.0/`](v1.0.0/) (rebaseline of former development **1.3.3**).
- **Archived development line:** former root `v1.x.x` → [`dev/v0.x.x/`](dev/) (major 1→0). OTA "latest" ignores `dev/`.

## Tools
- `Tools/Visol_WIFI_Module_FW_Uploader.exe` — PC GUI uploader

## v1.0.0 (production)
- First production mainline (content from former v1.3.3)
- SoftAP /sta: 잠금 상태에서도 비밀번호 표시(눈 아이콘)
- 연결 테스트 안정화: MQTT pause / SoftAP disconnect 처리 강화
- Flash **4MB**
- Historical notes for archived 0.x.x live under each `dev/v0.*` folder and below (legacy section kept for search)

## Legacy notes (pre-rebaseline labels)
The sections below retain historical changelog text. Folder paths for those builds are now under `dev/` with major version 0 (e.g. former v1.3.2 → `dev/v0.3.2/`).

## v1.3.3
- SoftAP /sta: 잠금 상태에서도 비밀번호 표시(눈 아이콘) 사용 가능
- 연결 테스트 안정화: MQTT pause / SoftAP disconnect 처리 강화 (POWERON_RESET 감소)
- Flash **4MB**
- **Superseded by production v1.0.0**; archive: `dev/v0.3.3/`

## v1.3.2
- SoftAP-safe STA nearby AP scan; empty STA SSID = portal-only (no connect loop)
- SoftAP `/sta` captive-safe HTML form POST for scan/test (no `<script>` / no `/static` second GET)
- SoftAP `/sta` UI: portal theme (cards/tabs/buttons), Edit→lock then Save STA, password show/hide when unlocked
- Config Device ID: boot sync `mqtt_cfg` ← `proto_cfg` when desynced
- Flash **4MB** — archive: `dev/v0.3.2/`

## v1.3.1
- SoftAP client join: STA disconnect deferred off the WiFi event handler (esp_timer)
- SoftAP-up STA reconnect backoff + portal TX power relief
- Fixes POWERON_RESET / unusable SoftAP portal when STA has no AP (e.g. reason=201) and phone joins SoftAP
- Prefer `http://192.168.2.1` (portal) / `http://192.168.100.1` (MainAP)
- Rebuild: flash size corrected to **4MB** (image header was wrongly 16MB). Requires **full/factory reflash** — app-only OTA will not fix bootloader/image header mismatch.
- Archive: `dev/v0.3.1/`

## v1.3.0
- SoftAP HTTPS :443 is redirect-only: TLS accept → 302 to `http://<softap-ip>/…` (path/query preserved); no portal HTML on HTTPS
- SoftAP HTTP :80 still serves the full multipage portal
- Prefer `http://192.168.100.1` (MainAP) / `http://192.168.2.1`; self-signed warning may appear once on https before redirect
- If heap is too low for TLS redirect, :443 is skipped; HTTP portal remains available
- Archive: `dev/v0.3.0/`

## Older 1.2.x / 1.1.x / 1.0.0
See individual folders under [`dev/`](dev/) (`v0.2.x`, `v0.1.x`, `v0.0.0`) and historical detail previously listed in this file's git history.
