# ESP_WIFI_MQTT v0.2.1 (아카이브 · 과거 v1.2.1)

## 주요 변경

- SoftAP 포털 로고 인라인(captive-safe), About: Visol Inc / Since 2026 / License
- 설정 FW 탭에서 수동 FW 업로드(`app.bin`) 지원
- Check Latest 시 Tmr Svc 스택 오버플로 수정, manifest raw 우선 폴백
- SoftAP STA 세션 / OTA 인증 및 포털 UX 수정

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.1** → **v0.2.1**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.1` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.1`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
