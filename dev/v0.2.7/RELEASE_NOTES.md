# ESP_WIFI_MQTT v0.2.7 (아카이브 · 과거 v1.2.7)

## 주요 변경

- SoftAP LAN: MainAP `192.168.1.1/24`, 설정 포털 SoftAP `192.168.2.1/24`
- APSTA 충돌: STA가 SoftAP /24를 쓰면 포털을 `192.168.3.1`로 이동
- HTTPS SAN·MQTT MainAP 브로커 예시를 새 SoftAP IP에 맞춤
- GitHub OTA 확인/설치 전 MQTT + SoftAP HTTPS를 잠시 중지해 TLS 힙 확보
- mbedTLS `SSL_IN_CONTENT_LEN=8192`, dynamic free, `tls_oom` 오류 메시지 개선

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.7** → **v0.2.7**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.7` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.7`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
