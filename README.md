# WIFI ESP Module Release

VISOL ESP32 WiFi/MQTT 모듈 공개 펌웨어입니다.  
**POWRAY** 호스트와 UART·MQTT로 연동하며, SoftAP 웹 포털로 WiFi/MQTT/OTA를 설정합니다.

> 권장 POWRAY 펌웨어: **1.4.6 이상**

## 제품 역할

- ESP32가 홈 WiFi(STA) 또는 **Main AP SoftAP LAN**으로 네트워크에 붙고 MQTT 브로커와 통신
- J1 UART(IO25/IO26)로 호스트(POWRAY 등)와 프로토콜 브리지
- SoftAP 설정 포털(HTTP :80 UI, HTTPS :443→HTTP 리다이렉트)에서 장치·WiFi·MQTT·펌웨어 관리

## SoftAP 포털 주소 (v1.3.0+)

| 모드 | 주소 |
|------|------|
| **Main AP** | `http://192.168.100.1` (권장) |
| **일반 SoftAP** | `http://192.168.2.1` (권장) |
| APSTA 충돌 회피 | `http://192.168.3.1` (STA가 SoftAP와 같은 /24일 때) |
| HTTPS :443 | 자체 서명 → 동일 경로 HTTP 302 (UI는 HTTP만) |

`https://`로 열면 브라우저 경고가 한 번 뜰 수 있고, 계속하면 HTTP 포털로 이동합니다. SoftAP 접속 시 비밀번호 없이 설정 가능. STA IP로 열면 SoftAP 비밀번호 로그인(`Unlock Settings`) 필요.

Main AP 시 MQTT 브로커 예: `mqtt://192.168.100.100` (SoftAP에 붙은 PC).

## 설정 포털 탭 (요약)

| 탭 | 내용 |
|----|------|
| **Config** | Device/Group ID, UART1 보드레이트, Power Save · Edit → Save Config |
| **SoftAP** | Main AP ON/OFF, SoftAP SSID/비밀번호(+확인), 접속 스테이션 목록 |
| **STA** | 홈 WiFi SSID/비밀번호, AP 검색·접속 테스트 · SoftAP 접속 + Main AP OFF일 때만 |
| **MQTT** | 브로커 URI/포트/계정 · Test / Save / Reconnect |
| **POWRAY TEST** | MQTT로 디밍·상태·ALIVE/RSSI/IP/토픽 점검 (탭 이탈 시 자동 0%) |
| **FW** | Check/Install Latest(인터넷+STA) · 수동 `*-app.bin` 업로드(SoftAP만으로 가능) |
| **About** | 제품/FW/MAC 정보 · Restart Device |

## 최신 펌웨어 받기

이 저장소 **main**의 `vX.Y.Z/` 폴더가 버전입니다 (GitHub Release 태그 미사용).

1. 아래 버전 표에서 최신 `vX.Y.Z` 폴더로 이동  
2. 용도에 맞는 파일 다운로드:

| 파일 | 용도 |
|------|------|
| `ESP_WIFI_MQTT-v*-factory.bin` | 최초/공장 설치 (`esptool` offset `0x0`) |
| `ESP_WIFI_MQTT-v*-app.bin` | OTA / UART / 포털 수동 업로드 |
| `manifest.json` (+ `manifest.sig`) | 서명된 OTA 메타데이터 |
| `Tools/Visol_WIFI_Module_FW_Uploader.exe` | PC GUI 업로더 (최신 GUI 빌드) |

장치 포털 **FW → Check Latest / Install Latest** 도 같은 `vX.Y.Z/` 폴더에서 최고 semver를 고릅니다. STA + 인터넷 필요.

## 버전

| 버전 | 경로 | 요약 |
|------|------|------|
| v1.3.3 | [v1.3.3/](v1.3.3/) | SoftAP /sta 잠금 시에도 비밀번호 눈 아이콘 · 연결 테스트 안정화 · **4MB** |
| v1.3.2 | [v1.3.2/](v1.3.2/) | SoftAP `/sta` 폼 POST + Edit/잠금·포털 테마 · Config ID 동기화 · **4MB** |
| v1.3.1 | [v1.3.1/](v1.3.1/) | SoftAP 포털 STA pause 지연 + **4MB flash 헤더 수정**(factory 재플래시 필요) |
| v1.3.0 | [v1.3.0/](v1.3.0/) | SoftAP HTTPS→HTTP 리다이렉트 전용 (포털 UI는 HTTP) |
| v1.2.12 | [v1.2.12/](v1.2.12/) | SoftAP 포털 탭→페이지 분리, CFG BSS 축소 |
| v1.2.11 | [v1.2.11/](v1.2.11/) | POWRAY A9 GroupID 오인 수정, HTTPS 프로브 노이즈 억제 |
| v1.2.10 | [v1.2.10/](v1.2.10/) | POWRAY A9 ID/전류·진단 UI, MQTT 토픽 목록 |
| v1.2.9 | [v1.2.9/](v1.2.9/) | UART RX 스택 오버플로 수정 (POWRAY A9 + MQTT/HTTPS) |
| v1.2.8 | [v1.2.8/](v1.2.8/) | MainAP SoftAP `192.168.100.x`, 폴더 기반 GitHub OTA + 인터넷 게이트 |
| v1.2.7 | [v1.2.7/](v1.2.7/) | SoftAP MainAP `192.168.1.x` / portal `192.168.2.x`, OTA TLS 힙 확보 |
| v1.2.6 | [v1.2.6/](v1.2.6/) | POWRAY UI 정리, A9/MQTT drop 수정 |
| v1.2.5 | [v1.2.5/](v1.2.5/) | SoftAP HTTPS 안정화, POWRAY TEST UI |
| v1.2.4 | [v1.2.4/](v1.2.4/) | SoftAP POWRAY TEST 탭 |
| v1.2.3 | [v1.2.3/](v1.2.3/) | SoftAP HTTPS, APSTA IP 충돌 회피, MainAP L2 forward |
| v1.2.2 | [v1.2.2/](v1.2.2/) | SoftAP STA↔STA L2 forward |
| v1.2.1 | [v1.2.1/](v1.2.1/) | SoftAP 로고, About, web upload |
| v1.2.0 | [v1.2.0/](v1.2.0/) | 설정 UI, Main AP SoftAP LAN/MQTT |
| v1.1.1 | [v1.1.1/](v1.1.1/) | GitHub OTA 최신버전 탐색 수정 |
| v1.1.0 | [v1.1.0/](v1.1.0/) | WiFi AP 스캔/연결 테스트 |
| v1.0.0 | [v1.0.0/](v1.0.0/) | 초기 공개 릴리스 |

변경 이력: [RELEASE_NOTES.md](RELEASE_NOTES.md)

## 플래시

```bash
# 공장 설치 (병합 이미지)
esptool.py -p COMx -b 460800 write_flash 0x0 v1.3.1/ESP_WIFI_MQTT-v1.3.1-factory.bin

# UART OTA (이미 dual-OTA 파티션인 경우)
python visol_fw_updater.py --file v1.3.1/manifest.json --firmware v1.3.1/ESP_WIFI_MQTT-v1.3.1-app.bin --port COMx
```

또는 `Tools/Visol_WIFI_Module_FW_Uploader.exe` 사용 (GUI · 폴더 기반 GitHub OTA / 로컬 manifest).
