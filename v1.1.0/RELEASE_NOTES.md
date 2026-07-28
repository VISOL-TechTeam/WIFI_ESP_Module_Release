# ESP_WIFI_MQTT v1.1.0

## Summary
- 4MB dual OTA 파티션 (`ota_0` / `ota_1`)
- USB-UART0 런타임 OTA (BOOT 스위치 불필요)
- ECDSA P-256 manifest 서명 + SHA256 검증
- GitHub Release HTTPS OTA 명령 지원

## Flash
- **Factory (최초/복구):** `ESP_WIFI_MQTT-v1.1.0-factory.bin` @ `0x0`
- **Runtime OTA:** `ESP_WIFI_MQTT-v1.1.0-app.bin` + `manifest.json`

## Notes
- V1.0 단일 factory 장치에서 OTA를 쓰려면 이 factory 이미지를 **1회** 플래시해야 합니다.
- 공개키는 펌웨어에 내장되어 있으며, `ota_pubkey.pem` 과 일치해야 합니다.
