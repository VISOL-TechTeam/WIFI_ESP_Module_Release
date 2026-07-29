# ESP_WIFI_MQTT v1.1.0

## 주요 변경 (since v1.0.0)

- 설정 페이지: WiFi AP 스캔 → SSID 선택 → 비밀번호 입력 → 연결 테스트 API/UI 추가 (`/api/wifi/scan`, `/api/wifi/connect_test`)
- J1 UART TX/RX 핀맵 복구 (GPIO25=TX / GPIO26=RX) 및 UART1 init 순서 정상화
- UART2 경로 제거, 호스트 링크는 UART1 전용
- GUI 업로더: esptool 4/5 CLI 호환 수정, 도구명 `Visol_WIFI_Module_FW_Uploader`로 정리 (Tools 폴더)

## 참고

- 설정 페이지 GitHub OTA, SoftAP HTTPS 기본 OFF / 포털 안정화는 v1.0.0에 포함되어 있음

Built from Visol_WIFI_Module_V_ESP @ af02b3b.
