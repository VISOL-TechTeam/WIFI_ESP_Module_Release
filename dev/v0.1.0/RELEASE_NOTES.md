# ESP_WIFI_MQTT v0.1.0 (아카이브 · 과거 v1.1.0)

## 주요 변경 (이전 아카이브 v0.0.0 대비)

- 설정 페이지: WiFi AP 스캔 → SSID 선택 → 비밀번호 입력 → 연결 테스트 API/UI (`/api/wifi/scan`, `/api/wifi/connect_test`)
- J1 UART TX/RX 핀맵 복구 (GPIO25=TX / GPIO26=RX) 및 UART1 init 순서 정상화
- UART2 경로 제거, 호스트 링크는 UART1 전용
- GUI 업로더: esptool 4/5 CLI 호환 수정, 도구명 `Visol_WIFI_Module_FW_Uploader`로 정리 (`Tools/`)

## 참고

- 설정 페이지 GitHub OTA, SoftAP HTTPS 기본 OFF / 포털 안정화는 이전 아카이브(v0.0.0)에 포함되어 있음

빌드: Visol_WIFI_Module_V_ESP @ af02b3b

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.1.0** → **v0.1.0**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.1.0` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.1.0`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
