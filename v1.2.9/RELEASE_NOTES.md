## v1.2.9
- Fix critical `uart1_j1_rx` stack overflow on POWRAY TEST status (0xA9) when MQTT + SoftAP HTTPS are active
- Move UART RX large buffers / MQTT pub scratch / protocol parse+TX buffers off the RX task stack (BSS)
- Defer POWRAY status/hex parsing to `mqtt_pub_task`; increase `uart1_j1_rx` stack 6KB → 8KB
