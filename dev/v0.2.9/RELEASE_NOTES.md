# ESP_WIFI_MQTT v0.2.9 (아카이브 · 과거 v1.2.9)

## 주요 변경

- MQTT + SoftAP HTTPS 활성 시 POWRAY TEST status(0xA9)에서 `uart1_j1_rx` 스택 오버플로 수정
- UART RX 대용량 버퍼 / MQTT pub scratch / 프로토콜 파싱·TX 버퍼를 RX 태스크 스택에서 BSS로 이동
- POWRAY status/hex 파싱을 `mqtt_pub_task`로 이관, `uart1_j1_rx` 스택 6KB → 8KB

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.9** → **v0.2.9**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.9` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.9`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
