# ESP_WIFI_MQTT v1.2.1

## Summary (KO)
- STA IP 웹 설정 접속 시 `Specified method is invalid for this resource` 오류 수정
- 로그인 후 303 리다이렉트 + GET `/login`·`/settings` 허용으로 새로고침/북마크 안정화
- WiFi SoftAP/STA(APSTA) 안정성 개선
- OTA 전송 신뢰성 개선 (UART/GitHub OTA)

## Summary (EN)
- Fix STA IP web portal HTTP method mismatch (`Specified method is invalid for this resource`)
- After SoftAP-password login, 303 redirect to `/`; allow GET on `/login` and `/settings`
- WiFi SoftAP/STA stability improvements
- OTA transfer reliability improvements

## Flash
- **Factory (first install / recovery):** `ESP_WIFI_MQTT-v1.2.1-factory.bin` @ `0x0`
- **Runtime OTA:** `ESP_WIFI_MQTT-v1.2.1-app.bin` + `manifest.json`

## Notes
- SoftAP (`http://192.168.4.1`): settings without password
- STA IP: SoftAP password login required (default `visol1234` if unset)
