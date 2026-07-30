# ESP_WIFI_MQTT v1.1.1

## 주요 변경 (since v1.1.0)

- **GitHub OTA 최신 버전 탐지 수정**: 설정 페이지 Check Latest가 공개 릴리스 저장소 `WIFI_ESP_Module_Release`를 사용하도록 변경
  - 원인: 펌웨어가 private 소스 저장소 `WIFI_Module_V_ESP`의 `/releases/latest`만 조회 → 404/미탐지
  - 또한 아티팩트가 git 폴더로만 올라가고 GitHub Releases asset이 없으면 `/releases/latest`가 실패
  - 수정: Releases/latest 우선 + Contents API로 `vX.Y.Z/` 최신 디렉터리 탐색 후 raw manifest 폴백
  - 설치 URL도 raw → Releases asset → manifest.app_url 순으로 프로브 (private app_url 의존 제거)
- OTA 중 UART1 `OTA_STATE(0xF2)` 브로드캐스트 — 호스트 NRST 강제리셋 홀드
- PC 업데이터(`visol_fw_updater.py`) / manifest 기본 URL도 동일 공개 릴리스 저장소로 정렬

## 참고

- 장치(1.0.0/1.1.0)가 이 수정을 받으려면 한 번은 UART/factory로 v1.1.1을 올려야 합니다 (구 펌웨어는 잘못된 repo URL을 하드코딩).
- 이후부터는 설정 페이지 GitHub OTA로 최신 버전을 찾을 수 있습니다.

Built from Visol_WIFI_Module_V_ESP @ d891dc0.
