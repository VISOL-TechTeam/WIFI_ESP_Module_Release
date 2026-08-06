# ESP_WIFI_MQTT v0.3.2 (아카이브 · 과거 v1.3.2)

## 주요 변경

- SoftAP에서도 안전한 주변 STA AP 스캔, STA SSID가 비어 있으면 포털 전용(연결 루프 없음)
- SoftAP `/sta`: captive-safe HTML form POST로 스캔/테스트 (`<script>` / `/static` 추가 GET 없음)
- SoftAP `/sta` UI: 포털 테마, Edit→잠금 후 Save STA, 잠금 해제 시 비밀번호 표시/숨김
- Config Device ID: 부팅 시 `mqtt_cfg` ↔ `proto_cfg` 불일치면 동기화
- Flash **4MB**

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.3.2** → **v0.3.2**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.3.2` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.3.2`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
