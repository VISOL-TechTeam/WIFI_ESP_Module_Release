# ESP_WIFI_MQTT v1.0.0

## 요약

- 첫 **프로덕션** 메인라인 릴리스 **1.0.0**입니다.
- 기능적으로는 구 개발선 **v1.3.3**(현재 아카이브 `dev/v0.3.3/`)을 이어받습니다.
- 과거 공개 **1.x.x** 폴더는 **0.x.x**로 이름을 바꿔 [`dev/`](../dev/)에 보관했습니다.

## 빌드 갱신 (2026-09-04)

- **ID 동기화 개선**: POWRAY ↔ WIFI Device ID 동기화 경로 보강
- Device ID 변경 시 MQTT 토픽 재구성(`mqtt_refresh_topics_after_device_id_change`)
- 동일 버전(`1.0.0`) 바이너리·manifest 교체 — 이미 1.0.0인 장치는 GitHub OTA 「최신」으로 잡히지 않으므로 **수동 업로드 / UART OTA / factory 재플래시**로 적용

## 주요 변경 (구 1.3.3 계열 기준)

- SoftAP `/sta`: 폼이 잠긴 상태에서도 비밀번호 표시/숨김(눈 아이콘) 사용 가능
- 연결 테스트 안정화: MQTT pause / SoftAP disconnect 처리 강화 (예상치 못한 `POWERON_RESET` 감소)
- Flash **4MB**

구 개발선에서 이어받은 제품 기능(요약): SoftAP 멀티페이지 포털, Main AP LAN, STA 설정·스캔, MQTT, POWRAY TEST, GitHub 폴더 OTA(루트 `vX.Y.Z/`만), USB-UART OTA(VOTA), 수동 `app.bin` 업로드 등.

## 버전·OTA 안내

- 장치 GitHub OTA는 릴리스 repo **`main` 루트**의 `vX.Y.Z/` 폴더만 스캔합니다. `dev/` 아카이브는 「최신」에 포함되지 않습니다.
- `dev/` 바이너리 내부 앱 버전 문자열은 원래 빌드값을 유지합니다(폴더/파일명만 0.x로 정리).

## 산출물

- `ESP_WIFI_MQTT-v1.0.0-app.bin` — OTA / 앱 파티션 이미지
- `ESP_WIFI_MQTT-v1.0.0-factory.bin` — 전체 플래시 이미지
- `manifest.json` / `manifest.sig` — 서명된 OTA manifest
- `bootloader.bin`, `partition-table.bin`, `ota_data_initial.bin`
- `SHA256SUMS.txt`

## 플래시

- 이전 1.3.x(또는 동등 아카이브 0.3.x)에서 앱만 OTA해도 본 변경에는 충분합니다
- 공장/전체 재기록: `ESP_WIFI_MQTT-v1.0.0-factory.bin` (4MB 플래시)
