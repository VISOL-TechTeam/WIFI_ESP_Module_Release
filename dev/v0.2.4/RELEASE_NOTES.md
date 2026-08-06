# ESP_WIFI_MQTT v0.2.4 (아카이브 · 과거 v1.2.4)

## 주요 변경

- SoftAP 포털 **POWRAY TEST** 탭 추가 (WIFI_MQTT_Test_Tool과 동일 MQTT 토픽/페이로드)
- 제어: Broadcast CONT_ALL, Single CONT_CMD, Status Request (A9)
- 진단: ALIVE / RSSI / IP / SUB_TOPICS
- MQTT 연결 상태 표시, 미연결 시 전송 비활성

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.4** → **v0.2.4**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.4` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.4`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
