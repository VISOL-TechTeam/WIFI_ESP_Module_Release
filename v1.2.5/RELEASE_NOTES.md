## v1.2.5 (2026-07-31)

- SoftAP HTTPS(:443) 안정화: LWIP 소켓 확대, mbedTLS dynamic buffer, 실패 시 명확한 로그·지연 재시도, 포털에 실제 SoftAP IP/HTTPS 상태 표시
- POWRAY TEST: Activity 긴 문자열/HEX 줄바꿈, A9 Status 파싱 표시(밝기·온도·팬·전류·알람), System_R/Data 캡처 강화
- 디밍 UI 0–130: 0–100%=밝기, 101–130=Boost (값-100)초(최대 30s), +/-·숫자입력·프리셋, CONT_ALL/A7은 Test Tool과 동일 3자리 ASCII
- 온디바이스 CONT/A9는 MQTT publish + UART1 포워드(브로커 echo 없이도 동작)
