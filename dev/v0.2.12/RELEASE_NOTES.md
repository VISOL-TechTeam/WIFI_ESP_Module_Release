# ESP_WIFI_MQTT v0.2.12 (아카이브 · 과거 v1.2.12)

## 주요 변경

- SoftAP 설정 포털 탭 UI를 페이지로 분리 (`/`, `/config`, `/softap`, `/sta`, `/mqtt`, `/powray`, `/fw`, `/about`)
- 공유 CSS/JS(`/static/…`), POWRAY JS는 `/powray`만, OTA JS는 `/fw`만
- `s_cfg_page_buf` BSS 64KB → 20KB (약 44KB 절감), Edit/lock·API·auth·`/logo.png` 유지
- Captive portal 착지는 계속 `/` (Config)

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.12** → **v0.2.12**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.12` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.12`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
