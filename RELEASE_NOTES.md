## v1.2.4
- SoftAP POWRAY TEST tab (MQTT CONT_ALL/CMD/A9/diagnostics)
## v1.2.3
- SoftAP HTTPS :443, APSTA IP conflict fix, MainAP ARP L2 forward, continuous reconnect

## v1.2.2
- SoftAP STA↔STA L2 forward so ESP clients on MainAP SoftAP can reach PC MQTT broker

## v1.2.1
- SoftAP logo inline, About Visol Inc, web app.bin upload, Check Latest crash fix

# Release Notes

## v1.2.3 (2026-07-31)

- SoftAP 포털 HTTPS(:443) 재활성 — 자체 서명 ECDSA(SAN: 192.168.4.1 / 192.168.5.1). 브라우저 경고에서 계속 진행
- 클라이언트 APSTA에서 SoftAP 192.168.4.1과 STA 게이트웨이 충돌 시 SoftAP 포털을 192.168.5.1로 이동
- MainAP SoftAP L2 forward에 ARP/브로드캐스트 flood 추가 (STA↔STA MQTT)
- 클라이언트 MQTT를 STA netif에 바인딩
- Config의 WiFi/MQTT retry 횟수 UI·로직 제거 → 연속 자동 재접속
- MainAP와 클라이언트 ESP 모두 1.2.3 플래시 권장

## v1.2.2 (2026-07-31)

- SoftAP STA↔STA L2 forwarding: MainAP SoftAP에 붙은 ESP B 등이 PC 브로커(STA)에 MQTT 접속 가능
- MainAP.md에 STA↔STA 원인/수정/대안 토폴로지 문서화

## v1.2.1 (2026-07-30)

- SoftAP 포털 로고 PNG 표시 수정 및 SoftAP 설정 즉시편집
- Main AP MQTT Test 성공 후 상주 연결 유지

