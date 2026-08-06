# ESP_WIFI_MQTT v0.3.3 (아카이브 · 과거 v1.3.3)

## 주요 변경

- SoftAP `/sta`: 폼이 잠긴 상태에서도 비밀번호 표시/숨김(눈 아이콘) 유지
- 연결 테스트 안정화: MQTT pause / SoftAP disconnect 처리 강화 (`POWERON_RESET` 감소)

## 산출물

- `ESP_WIFI_MQTT-v0.3.3-app.bin` — OTA / 앱 파티션 이미지
- `ESP_WIFI_MQTT-v0.3.3-factory.bin` — 전체 플래시 이미지
- `manifest.json` / `manifest.sig` — 서명된 OTA manifest
- `bootloader.bin`, `partition-table.bin`, `ota_data_initial.bin`
- `SHA256SUMS.txt`

## 플래시

- 이전 1.3.x 계열에서 앱만 OTA해도 본 변경에는 충분합니다
- 공장/전체 재기록: `ESP_WIFI_MQTT-v0.3.3-factory.bin` (4MB)

> 프로덕션 후속: 동일 계열 기능은 루트 [`v1.0.0`](../../v1.0.0/RELEASE_NOTES.md) 으로 이어집니다.

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.3.3** → **v0.3.3**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.3.3` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.3.3`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
