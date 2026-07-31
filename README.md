# WIFI ESP Module Release

VISOL ESP32 WiFi/MQTT 紐⑤뱢 怨듦컻 由대━利???μ냼?낅땲??

## 踰꾩쟾

| 踰꾩쟾 | 寃쎈줈 | ?붿빟 |
|------|------|------|
| v1.2.3 | [v1.2.3/](v1.2.3/) | APSTA SoftAP/STA IP 異⑸룎 ?섏젙, MainAP ARP L2 forward, ?곗냽 ?ъ젒??retry UI ?쒓굅) |
| v1.2.2 | [v1.2.2/](v1.2.2/) | SoftAP STA?봖TA L2 forward (MainAP LAN PC 釉뚮줈而? |
| v1.2.1 | [v1.2.1/](v1.2.1/) | SoftAP ?ы꽭 濡쒓퀬 PNG/利됱떆?몄쭛, Main AP MQTT Test ???곸＜ ?곌껐 |
| v1.2.0 | [v1.2.0/](v1.2.0/) | ???ㅼ젙 UI, Main AP SoftAP LAN/MQTT, STA SoftAP ?쒗븳, About ?뺣━, OTA_STATE ?몄뒪???몃뱶?ㅽ봽 |
| v1.1.1 | [v1.1.1/](v1.1.1/) | GitHub OTA 理쒖떊踰꾩쟾 ?먯? ?섏젙, OTA_STATE ?몄뒪???몃뱶?ㅽ봽 |
| v1.1.0 | [v1.1.0/](v1.1.0/) | WiFi AP ?ㅼ틪/?곌껐 ?뚯뒪?? UART1 ?꾩슜 ?몄뒪??留곹겕 |
| v1.0.0 | [v1.0.0/](v1.0.0/) | 珥덇린 怨듦컻 由대━利?(dual OTA, USB-UART OTA, MQTT/WiFi ?덉젙?? |

## ?뚯씪 醫낅쪟

| ?뚯씪 | ?⑸룄 |
|------|------|
| `ESP_WIFI_MQTT-v*-app.bin` | ?고???UART/GitHub OTA?????대?吏 |
| `ESP_WIFI_MQTT-v*-factory.bin` | 怨듭옣 ?ㅼ튂??寃고빀 ?뚮옒???대?吏 (offset 0x0) |
| `bootloader.bin` / `partition-table.bin` / `ota_data_initial.bin` | 媛쒕퀎 ?뚮옒?쒖슜 |
| `manifest.json` / `manifest.sig` | ?쒕챸??OTA 硫뷀??곗씠??|
| `ota_pubkey.pem` | ?뚯썾?댁뿉 ?댁옣??寃利?怨듦컻??李멸퀬?? |
| `SHA256SUMS.txt` | 臾닿껐??寃??|
| `Tools/Visol_WIFI_Module_FW_Uploader.exe` | PC??factory/OTA GUI ?낅줈??|

## 怨듭옣 ?ㅼ튂

```bash
esptool.py -p COMx -b 460800 write_flash 0x0 v1.2.3/ESP_WIFI_MQTT-v1.2.3-factory.bin
```

## ?고????낅뜲?댄듃

```bash
python visol_fw_updater.py --file v1.2.3/manifest.json --firmware v1.2.3/ESP_WIFI_MQTT-v1.2.3-app.bin --port COMx
```

?μ튂 ?ㅼ젙 ?ы꽭??GitHub OTA??????μ냼??`vX.Y.Z/` 寃쎈줈(?먮뒗 GitHub Releases asset)?먯꽌 理쒖떊 manifest瑜?議고쉶?⑸땲??