# ESP_WIFI_MQTT v1.2.0

## 주요 변경 (since v1.1.1)

- **설정 페이지 탭 UI**: `Config | SoftAP | STA | MQTT | FW | About` 로 분리
  - 탭별 Edit/Save로 독립 설정·저장
  - MQTT Test/Reconnect, FW Check/Install, About Restart 유지
- **STA SoftAP 전용**: STA WiFi 설정·AP 스캔·접속 테스트는 SoftAP 포털(`http://192.168.4.1`) 접속 시에만 허용
  - STA IP로 접속 시 STA 탭 비활성 + 안내 메시지
  - 서버 API도 SoftAP 클라이언트만 허용 (`softap_required` / 403)
  - `/api/ota/status`에 `via_softap` 플래그 포함
- **OTA 호스트 NRST 홀드**: UART1 `OTA_STATE(0xF2)` 브로드캐스트로 OTA 중 호스트 강제 리셋 방지 (v1.1.1부터 포함, 본 릴리스에도 유지)

## 참고

- STA 홈 WiFi를 바꾸려면 SoftAP에 연결한 뒤 포털에서 STA 탭을 사용하세요.
- GitHub OTA는 공개 릴리스 저장소 `WIFI_ESP_Module_Release`의 `vX.Y.Z/` 를 조회합니다.

Built from Visol_WIFI_Module_V_ESP @ b349b01.
