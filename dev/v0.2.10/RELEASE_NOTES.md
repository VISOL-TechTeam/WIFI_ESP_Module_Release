# ESP_WIFI_MQTT v0.2.10 (아카이브 · 과거 v1.2.10)

## 주요 변경

- POWRAY A9 상태: ID/GroupID(프레임 Group[2]+ID[2]), Current1..3를 deci-amp로 표시(예: 418 → 41.8A)
- ALIVE / RSSI / IP 결과를 진단 버튼 아래에 인라인 표시
- POWRAY TEST에서 SUB_TOPICS 버튼 제거
- MQTT 연결 박스에 SUB1 Broadcast, SUB2 CMD, SUB3 System, PUB1 System_R, PUB2 Data 표시

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.10** → **v0.2.10**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.10` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.10`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
