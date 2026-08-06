# ESP_WIFI_MQTT v0.2.11 (아카이브 · 과거 v1.2.11)

## 주요 변경

- POWRAY A9 상태 수정: frame[2:3]은 모델(GroupID 아님), Device ID는 [4:5], GroupID는 MQTT 설정에서 가져옴
- SoftAP HTTPS: TLS 세션 단일화·핸드셰이크 타임아웃 단축, captive-portal CONN_EOF/timeout ERROR 로그 억제 (HTTP :80 동일)

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.11** → **v0.2.11**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.11` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.11`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
