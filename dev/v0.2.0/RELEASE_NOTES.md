# ESP_WIFI_MQTT v0.2.0 (archived from v0.2.0)

## 주요 변경 (since v1.1.1)

- **설정 페이지 탭 UI**: `Config | SoftAP | STA | MQTT | FW | About` 로 분리
  - 탭별 Edit/Save로 설정 저장
  - MQTT Test/Reconnect, FW Check/Install, About Restart 지원
- **STA SoftAP 제한**: STA WiFi 설정·AP 스캔·연결 테스트는 SoftAP 포털(`http://192.168.4.1`) 접속 시에만 허용
  - STA IP로 접속 시 STA 탭 비활성 + 안내 메시지
  - 관련 API는 SoftAP 클라이언트만 허용 (`softap_required` / 403)
  - `/api/ota/status`에 `via_softap` 플래그 포함
- **Main AP 모드**: SoftAP LAN(최대 8), PC 브로커 MQTT, 포털에서 STA 비활성
  - SoftAP 클라 목록 API/UI (`/api/softap/clients`), SoftAP deauth 강화
  - 브로커가 PC일 때만 MQTT, URI 정규화·브로커 LAN 경고
- **About 정리**: 제품/제조사/MAC/Device ID 중심 표시
- **OTA 호스트 NRST 핸드오프**: UART1 `OTA_STATE(0xF2)` 브로드캐스트로 OTA 후 호스트 강제 리셋 유도 (v1.1.1부터, 본 릴리즈에서도 유지)

## 주의

- STA 홈 WiFi를 바꾸려면 SoftAP에 접속한 뒤 포털에서 STA 설정을 저장하세요.
- GitHub OTA는 공개 릴리즈 저장소 `WIFI_ESP_Module_Release`의 `vX.Y.Z/` 를 조회합니다.

Built from Visol_WIFI_Module_V_ESP @ 553d8b9.
## Archive note (2026-08-06)
- Renamed from **v1.2.0** → **v0.2.0** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.0`; binary image internal version strings remain the original `1.2.0` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
