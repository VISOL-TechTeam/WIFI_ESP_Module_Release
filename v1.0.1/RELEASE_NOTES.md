# ESP_WIFI_MQTT v1.0.1

## 요약

- **ID 동기화 개선** 릴리스입니다 (v1.0.0 + POWRAY ↔ WIFI Device ID 동기화 보강).
- GitHub OTA 「최신」으로 1.0.0 장치가 이 버전을 받을 수 있습니다.

## 주요 변경

- POWRAY ↔ WIFI Device ID 동기화 경로 보강
- Device ID 변경 시 MQTT 토픽 재구성 (`mqtt_refresh_topics_after_device_id_change`)
- 그 외 기능은 v1.0.0과 동일 계열 (SoftAP 포털, MQTT, dual-OTA 등)

## 산출물

- `ESP_WIFI_MQTT-v1.0.1-app.bin` — OTA / 앱 파티션 이미지
- `ESP_WIFI_MQTT-v1.0.1-factory.bin` — 전체 플래시 이미지
- `manifest.json` / `manifest.sig` — 서명된 OTA manifest
- `bootloader.bin`, `partition-table.bin`, `ota_data_initial.bin`
- `SHA256SUMS.txt`

## 플래시 / OTA

- **권장:** 설정 페이지 GitHub OTA 또는 UART `INSTALL_LATEST` (1.0.0 → 1.0.1)
- 공장/전체 재기록: `ESP_WIFI_MQTT-v1.0.1-factory.bin` (4MB 플래시)
