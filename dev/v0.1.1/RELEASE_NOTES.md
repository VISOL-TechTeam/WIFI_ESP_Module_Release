# ESP_WIFI_MQTT v0.1.1 (아카이브 · 과거 v1.1.1)

## 주요 변경 (이전 아카이브 v0.1.0 대비)

- **GitHub OTA 최신 버전 탐지 수정**: Check Latest가 공개 릴리스 저장소 `WIFI_ESP_Module_Release`를 사용
  - 원인: private 소스 저장소 `/releases/latest` 조회 → 404, 또는 Releases asset 부재
  - 수정: Contents API로 루트 `vX.Y.Z/` 최신 디렉터리 탐색 후 raw manifest 폴백
  - 설치 URL은 raw → Releases asset → manifest.app_url 순으로 프로브
- OTA 중 UART1 `OTA_STATE(0xF2)` 브로드캐스트 — 호스트 NRST 강제리셋 홀드
- PC 업데이터(`visol_fw_updater.py`) / manifest 기본 URL을 동일 공개 릴리스 저장소로 정렬

## 참고

- 옛 장치(잘못된 repo URL 하드코딩)는 한 번 USB-UART/factory로 이 버전을 올려야 이후 포털 OTA가 동작합니다.

빌드: Visol_WIFI_Module_V_ESP @ d891dc0

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.1.1** → **v0.1.1**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.1.1` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.1.1`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
