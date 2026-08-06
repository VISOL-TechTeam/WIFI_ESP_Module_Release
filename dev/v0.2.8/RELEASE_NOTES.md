# ESP_WIFI_MQTT v0.2.8 (아카이브 · 과거 v1.2.8)

## 주요 변경

- SoftAP LAN: MainAP `192.168.100.1/24`, 설정 포털 SoftAP `192.168.2.1/24`
- MQTT MainAP 브로커 예: `mqtt://192.168.100.100`
- APSTA 충돌 시 포털 `192.168.3.1` (100.x 아님)
- 비밀번호 확인: SoftAP 설정에만 유지 (STA/MQTT에서는 제거, 눈 아이콘은 유지)
- GitHub OTA: 릴리스 repo `main` 루트에서 최고 semver `vX.Y.Z/` 폴더 탐색 (Release 태그/`/releases/latest` 미사용)
- OTA 확인/설치 중 MQTT + SoftAP HTTPS pause 유지(TLS 힙)
- HTTPS SAN: `192.168.100.1` / `.2.1` / `.3.1`

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.8** → **v0.2.8**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.8` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.8`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
