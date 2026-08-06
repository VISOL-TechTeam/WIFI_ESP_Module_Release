# ESP_WIFI_MQTT v0.2.5 (아카이브 · 과거 v1.2.5)

## 주요 변경 (2026-07-31)

- SoftAP HTTPS(:443) 안정화: LWIP 소켓 확대, mbedTLS dynamic buffer, 실패 시 명확한 로그·지연 재시도, 포털에 실제 SoftAP IP/HTTPS 상태 표시
- POWRAY TEST: Activity 긴 문자열/HEX 줄바꿈, A9 Status 파싱 표시(밝기·온도·팬·전류·알람), System_R/Data 캡처 강화
- 디밍 UI 0–130: 0–100%=밝기, 101–130=Boost, +/-·숫자입력·프리셋
- 온디바이스 CONT/A9는 MQTT publish + UART1 포워드(브로커 echo 없이도 동작)

## 아카이브 안내 (2026-08-06)
- 과거 공개 버전 **v1.2.5** → **v0.2.5**로 폴더명을 바꾸고 `dev/`로 이동했습니다 (프로덕션 1.0.0 리베이스).
- 파일명·텍스트 manifest는 `v0.2.5` 기준으로 정리됐을 수 있으나, 바이너리 내부 버전 문자열은 원래 빌드값(예: `1.2.5`)을 유지합니다(재빌드 없음).
- 아카이브용으로 고친 `manifest.json`의 서명/`manifest.sig`는 검증이 실패할 수 있습니다. 프로덕션 OTA 최신 탐색 대상이 아닙니다.
