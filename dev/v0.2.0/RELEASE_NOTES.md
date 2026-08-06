# ESP_WIFI_MQTT v0.2.0 (아카이브 · 과거 v1.2.0)

## 주요 변경 (이전 아카이브 v0.1.1 대비)

- **설정 페이지 탭 UI**: `Config | SoftAP | STA | MQTT | FW | About` 분리, 탭별 Edit/Save
- **STA SoftAP 제한**: STA WiFi 설정·스캔·연결 테스트는 SoftAP 포털 접속 시에만 허용
- **Main AP 모드**: SoftAP LAN(최대 8), PC 브로커 MQTT, 포털에서 STA 비활성
- SoftAP 클라 목록 API/UI (`/api/softap/clients`), SoftAP deauth 강화
- About: 제품/제조사/MAC/Device ID 중심 표시
- OTA 호스트 NRST 핸드오프(`OTA_STATE(0xF2)`) 유지

## 주의

- STA 홈 WiFi를 바꾸려면 SoftAP에 접속한 뒤 포털에서 STA 설정을 저장하세요.
- GitHub OTA는 공개 릴리스 저장소 루트 `vX.Y.Z/` 를 조회합니다.

빌드: Visol_WIFI_Module_V_ESP @ 553d8b9

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.0** → **v0.2.0**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.0` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.0`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
