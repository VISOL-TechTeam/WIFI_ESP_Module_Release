# ESP_WIFI_MQTT v1.3.3

## 변경 사항
- SoftAP /sta: 잠금(locked) 상태에서도 WiFi/STA 비밀번호 표시(눈 아이콘) 사용 가능
- 연결 테스트 안정화: MQTT pause / SoftAP disconnect 처리를 강화해 STA 연결 테스트 중 예기치 않은 POWERON_RESET 감소
- Flash 크기 **4MB** (기존 1.3.x와 동일)

## 산출물
- ESP_WIFI_MQTT-v1.3.3-app.bin — OTA / 앱 파티션 이미지
- ESP_WIFI_MQTT-v1.3.3-factory.bin — 전체 플래시 이미지
- manifest.json / manifest.sig — 서명된 OTA 매니페스트
- ootloader.bin, partition-table.bin, ota_data_initial.bin
- SHA256SUMS.txt

## Flash
- 이전 1.3.x에서 앱 전용 OTA로 충분
- Factory / 전체 재플래시: ESP_WIFI_MQTT-v1.3.3-factory.bin (4MB flash)
