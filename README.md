# WIFI ESP Module Release

VISOL ESP32 WiFi/MQTT 모듈 공개 릴리즈 저장소입니다.

## 버전

| 버전 | 경로 | 요약 |
|------|------|------|
| v1.2.1 | [v1.2.1/](v1.2.1/) | SoftAP 포털 로고 PNG/즉시편집, Main AP MQTT Test 후 상주 연결 |
| v1.2.0 | [v1.2.0/](v1.2.0/) | 탭 설정 UI, Main AP SoftAP LAN/MQTT, STA SoftAP 제한, About 정리, OTA_STATE 호스트 핸드오프 |
| v1.1.1 | [v1.1.1/](v1.1.1/) | GitHub OTA 최신버전 탐지 수정, OTA_STATE 호스트 핸드오프 |
| v1.1.0 | [v1.1.0/](v1.1.0/) | WiFi AP 스캔/연결 테스트, UART1 전용 호스트 링크 |
| v1.0.0 | [v1.0.0/](v1.0.0/) | 초기 공개 릴리즈 (dual OTA, USB-UART OTA, MQTT/WiFi 안정화) |

## 파일 종류

| 파일 | 용도 |
|------|------|
| `ESP_WIFI_MQTT-v*-app.bin` | 런타임 UART/GitHub OTA용 앱 이미지 |
| `ESP_WIFI_MQTT-v*-factory.bin` | 공장 설치용 결합 플래시 이미지 (offset 0x0) |
| `bootloader.bin` / `partition-table.bin` / `ota_data_initial.bin` | 개별 플래시용 |
| `manifest.json` / `manifest.sig` | 서명된 OTA 메타데이터 |
| `ota_pubkey.pem` | 펌웨어에 내장된 검증 공개키(참고용) |
| `SHA256SUMS.txt` | 무결성 검사 |
| `Tools/Visol_WIFI_Module_FW_Uploader.exe` | PC용 factory/OTA GUI 업로더 |

## 공장 설치

```bash
esptool.py -p COMx -b 460800 write_flash 0x0 v1.2.1/ESP_WIFI_MQTT-v1.2.1-factory.bin
```

## 런타임 업데이트

```bash
python visol_fw_updater.py --file v1.2.1/manifest.json --firmware v1.2.1/ESP_WIFI_MQTT-v1.2.1-app.bin --port COMx
```

장치 설정 포털의 GitHub OTA는 이 저장소의 `vX.Y.Z/` 경로(또는 GitHub Releases asset)에서 최신 manifest를 조회합니다.