# WIFI ESP Module Release

VISOL ESP32 WiFi/MQTT 모듈 공개 펌웨어 저장소입니다.
**POWRAY** 호스트와 UART·MQTT로 연동하며, SoftAP 웹 포털로 WiFi/MQTT/OTA를 설정합니다.

> 권장 POWRAY 펌웨어: **1.4.6 이상**

## 저장소 구조

| 경로 | 역할 |
|------|------|
| [`v1.0.0/`](v1.0.0/) | **프로덕션 메인라인** (현재 최신). 장치 GitHub OTA가 탐색하는 대상 |
| [`dev/`](dev/) | 과거 개발선 아카이브 (구 공개 `1.x.x` → `0.x.x`). OTA 「최신」 탐색 **대상 아님** |
| [`Tools/`](Tools/) | PC GUI 실행 파일 zip + 사용설명서 PDF (`WIFI_Module_V_ESP-executables.zip`, 모듈/업로더/프로토콜 매뉴얼) |
| [`RELEASE_NOTES.md`](RELEASE_NOTES.md) | 버전 인덱스(요약). 상세는 각 버전 폴더·`dev/` 참고 |

GitHub Release 태그/`/releases/latest`는 사용하지 않습니다. **`main` 브랜치의 루트 `vX.Y.Z/` 폴더**가 버전입니다.

## 제품 역할

- ESP32가 홈 WiFi(STA) 또는 **Main AP SoftAP LAN**으로 네트워크에 붙고 MQTT 브로커와 통신
- J1 UART(IO25/IO26)로 호스트(POWRAY 등)와 프로토콜 브리지
- SoftAP 설정 포털(HTTP :80 UI, HTTPS :443→HTTP 리다이렉트)에서 장치·WiFi·MQTT·펌웨어 관리

## SoftAP 포털 주소 (현재 프로덕션 기준)

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

1. [`v1.0.0/`](v1.0.0/) 로 이동 (현재 프로덕션)
2. 용도에 맞는 파일 다운로드:

| 파일 | 용도 |
|------|------|
| `ESP_WIFI_MQTT-v*-factory.bin` | 최초/공장 설치 (`esptool` offset `0x0`) |
| `ESP_WIFI_MQTT-v*-app.bin` | OTA / USB-UART / 포털 수동 업로드 |
| `manifest.json` (+ `manifest.sig`) | 서명된 OTA 메타데이터 |
| [`Tools/WIFI_Module_V_ESP-executables.zip`](Tools/WIFI_Module_V_ESP-executables.zip) | PC GUI 실행 파일 묶음 (업로더 + MQTT 테스트 도구) |
| [`Tools/VISOL_WIFI_모듈_사용설명서_260806.pdf`](Tools/VISOL_WIFI_모듈_사용설명서_260806.pdf) | WIFI 모듈 사용설명서 (260806) |
| [`Tools/VISOL_WIFI_펌웨어_업로더_사용설명서_260806.pdf`](Tools/VISOL_WIFI_펌웨어_업로더_사용설명서_260806.pdf) | 펌웨어 업로더 사용설명서 (260806) |
| [`Tools/WiFi_Module_Protocol_260806.pdf`](Tools/WiFi_Module_Protocol_260806.pdf) | WiFi Module Protocol (260806) |

장치 포털 **FW → Check Latest / Install Latest** 는 릴리스 repo **`main` 루트**의 `vX.Y.Z/` 폴더만 스캔해 최고 semver를 고릅니다. **`dev/` 아래는 탐색하지 않습니다.** STA + 인터넷이 필요합니다.

## manifest.json (OTA 검증 메타데이터)

각 `vX.Y.Z/`(및 `dev/vX.Y.Z/`)에 있는 `manifest.json`은 **앱 바이너리(`*-app.bin`)를 설치하기 전에 검증·다운로드에 쓰는 서명된 메타데이터**입니다.  
PC UART 업데이터와 장치 GitHub/웹 OTA가 동일한 스키마를 공유합니다. GitHub Release 태그 API는 쓰지 않고, 이 파일 + raw `app.bin` URL로 동작합니다.

### 역할

1. **버전 비교** — `version`으로 현재 펌웨어보다 새지 확인 (웹 OTA는 다운그레이드·동일 버전 재설치 거부)
2. **무결성** — 다운로드한 `app.bin`의 크기(`app_size`)·SHA-256(`sha256`)이 manifest와 일치해야 설치
3. **출처 검증** — ECDSA P-256 `signature`를 장치 내장 공개키로 검증 (위·변조 차단)
4. **다운로드 경로** — `app_url`(또는 동일 폴더 raw URL)로 `*-app.bin` 위치 지정

서명·SHA·크기·target 불일치 시 설치를 거부하고 **기존 OTA 슬롯을 유지**합니다.

### 필드 (`schema`: 1)

| 필드 | 의미 |
|------|------|
| `schema` | manifest 스키마 버전 (현재 `1`) |
| `project` | 프로젝트 ID (`ESP_WIFI_MQTT`) |
| `target` | 칩 대상 (`esp32`) |
| `version` | SemVer 문자열 (예: `1.0.0`) |
| `build_id` | 빌드 식별자 |
| `channel` | 채널 (예: `stable`) |
| `app_size` | `*-app.bin` 바이트 크기 (OTA 슬롯 `0x1E0000` 이하) |
| `sha256` | `*-app.bin`의 SHA-256 hex |
| `app_url` | 앱 바이너리 HTTPS(raw) URL |
| `min_updater` | 최소 업데이터 버전 |
| `created_at` | UTC 생성 시각 (`YYYY-MM-DDTHH:MM:SSZ`) |
| `signature` | 정규 페이로드에 대한 ECDSA P-256 서명 hex |

서명 대상(정규 문자열):  
`schema|project|target|version|build_id|app_size|sha256|app_url|channel`

### manifest.sig

같은 폴더의 `manifest.sig`는 `signature`와 **동일한 서명 hex를 담은 사이드카 파일**입니다(릴리스 빌드 시 `--sig-out`으로 생성).  
장치 OTA 검증은 **`manifest.json` 안의 `signature` 필드**를 기준으로 합니다. `manifest.sig`는 배포·도구 쪽에서 서명을 따로 참조할 때 쓰는 보조 파일입니다.

예: [`v1.0.0/manifest.json`](v1.0.0/manifest.json), [`v1.0.0/manifest.sig`](v1.0.0/manifest.sig)

## 버전

| 버전 | 경로 | 요약 |
|------|------|------|
| **v1.0.0** | [v1.0.0/](v1.0.0/) | **프로덕션 메인라인** (구 개발선 1.3.3 기능 리베이스) · SoftAP `/sta` 잠금 시 비밀번호 눈 아이콘 · 연결 테스트 안정화 · **4MB** |
| 아카이브 | [dev/](dev/) | 과거 공개 `1.x.x` → `0.x.x` (`v1.a.b` → `dev/v0.a.b/`). 프로덕션 OTA 최신 아님 |

예시 매핑: `v1.3.3`→`dev/v0.3.3/`, `v1.3.2`→`dev/v0.3.2/`, `v1.2.12`→`dev/v0.2.12/`, 초기 공개 `v1.0.0`→`dev/v0.0.0/` (루트 `v1.0.0/`은 새 프로덕션).

- 프로덕션 노트: [v1.0.0/RELEASE_NOTES.md](v1.0.0/RELEASE_NOTES.md)
- 인덱스: [RELEASE_NOTES.md](RELEASE_NOTES.md)
- 아카이브 설명·이력: [dev/README.md](dev/README.md), [dev/CHANGELOG.md](dev/CHANGELOG.md)

## 플래시

```bash
# 공장 설치 (병합 이미지)
esptool.py -p COMx -b 460800 write_flash 0x0 v1.0.0/ESP_WIFI_MQTT-v1.0.0-factory.bin

# USB-UART OTA (이미 dual-OTA 파티션인 경우)
python visol_fw_updater.py --file v1.0.0/manifest.json --firmware v1.0.0/ESP_WIFI_MQTT-v1.0.0-app.bin --port COMx
```

또는 [`Tools/WIFI_Module_V_ESP-executables.zip`](Tools/WIFI_Module_V_ESP-executables.zip) 다운로드 후 압축 해제하여 GUI 업로더 사용 (폴더 기반 GitHub OTA / 로컬 manifest).
