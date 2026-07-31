# WIFI ESP Module Release

VISOL ESP32 WiFi/MQTT 모듈 공개 릴리스 저장소입니다.

## 버전

| 버전 | 경로 | 요약 |
|------|------|------|
| v1.2.7 | [v1.2.7/](v1.2.7/) | SoftAP MainAP `192.168.1.x` / portal `192.168.2.x`, GitHub OTA TLS 힙 확보 |
| v1.2.6 | [v1.2.6/](v1.2.6/) | POWRAY UI 정리, A9/MQTT drop 수정, 비밀번호 UX |
| v1.2.5 | [v1.2.5/](v1.2.5/) | SoftAP HTTPS 안정화, POWRAY TEST UI |
| v1.2.4 | [v1.2.4/](v1.2.4/) | SoftAP POWRAY TEST 탭 |
| v1.2.3 | [v1.2.3/](v1.2.3/) | SoftAP HTTPS, APSTA IP 충돌 회피, MainAP L2 forward |
| v1.2.2 | [v1.2.2/](v1.2.2/) | SoftAP STA↔STA L2 forward |
| v1.2.1 | [v1.2.1/](v1.2.1/) | SoftAP 로고, About, web upload, Check Latest 수정 |
| v1.2.0 | [v1.2.0/](v1.2.0/) | 설정 UI, Main AP SoftAP LAN/MQTT |
| v1.1.1 | [v1.1.1/](v1.1.1/) | GitHub OTA 최신버전 탐색 수정 |
| v1.1.0 | [v1.1.0/](v1.1.0/) | WiFi AP 스캔/연결 테스트 |
| v1.0.0 | [v1.0.0/](v1.0.0/) | 초기 공개 릴리스 |

## 파일 종류

| 파일 | 용도 |
|------|------|
| `ESP_WIFI_MQTT-v*-app.bin` | OTA/UART/GitHub OTA용 앱 이미지 |
| `ESP_WIFI_MQTT-v*-factory.bin` | 공장 설치용 병합 플래시 이미지 (offset 0x0) |
| `bootloader.bin` / `partition-table.bin` / `ota_data_initial.bin` | 개별 플래시용 |
| `manifest.json` / `manifest.sig` | 서명된 OTA 메타데이터 |
| `ota_pubkey.pem` | 펌웨어에 내장된 검증 공개키 참고용 |
| `SHA256SUMS.txt` | 무결성 검증 |
| `Tools/Visol_WIFI_Module_FW_Uploader.exe` | PC용 factory/OTA GUI 업로더 |

## SoftAP IP (v1.2.7+)

| 모드 | SoftAP IP |
|------|-----------|
| Main AP | `http://192.168.1.1` |
| 일반 SoftAP / 설정 포털 | `http://192.168.2.1` |
| APSTA 충돌 회피 | `http://192.168.3.1` (STA가 SoftAP와 같은 /24일 때) |

## 공장 설치

```bash
esptool.py -p COMx -b 460800 write_flash 0x0 v1.2.7/ESP_WIFI_MQTT-v1.2.7-factory.bin
```

## 시리얼 업데이트

```bash
python visol_fw_updater.py --file v1.2.7/manifest.json --firmware v1.2.7/ESP_WIFI_MQTT-v1.2.7-app.bin --port COMx
```

장치 설정 포털의 GitHub OTA는 이 저장소의 `vX.Y.Z/` 경로(또는 GitHub Releases asset)에서 최신 manifest를 조회합니다.
