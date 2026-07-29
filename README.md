# WIFI ESP Module Release

VISOL ESP32 WiFi/MQTT 모듈 펌웨어 배포 저장소입니다.

## 버전

| 버전 | 경로 | 비고 |
|------|------|------|
| v1.1.0 | [v1.1.0/](v1.1.0/) | WiFi AP 스캔/연결 테스트, UART1 전용 호스트 링크 |
| v1.0.0 | [v1.0.0/](v1.0.0/) | 초기 정식 릴리스 (dual OTA, USB-UART OTA, MQTT/WiFi 안정화) |

## 파일 설명

| 파일 | 용도 |
|------|------|
| `ESP_WIFI_MQTT-v*-app.bin` | 런타임 UART/GitHub OTA용 앱 이미지 |
| `ESP_WIFI_MQTT-v*-factory.bin` | 최초 설치·복구용 병합 이미지 (offset 0x0) |
| `bootloader.bin` / `partition-table.bin` / `ota_data_initial.bin` | 개별 플래시용 |
| `manifest.json` / `manifest.sig` | 서명된 OTA 메타데이터 |
| `ota_pubkey.pem` | 펌웨어에 내장된 검증 공개키(참고용) |
| `SHA256SUMS.txt` | 무결성 검사 |
| `Tools/Visol_WIFI_Module_FW_Uploader.exe` | PC용 factory/OTA GUI 업로더 |

## 최초 설치

```bash
esptool.py -p COMx -b 460800 write_flash 0x0 v1.1.0/ESP_WIFI_MQTT-v1.1.0-factory.bin
```

## 런타임 업데이트

```bash
python visol_fw_updater.py --file v1.1.0/manifest.json --firmware v1.1.0/ESP_WIFI_MQTT-v1.1.0-app.bin --port COMx
```
