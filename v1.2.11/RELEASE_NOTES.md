## v1.2.11
- Fix POWRAY A9 status: frame[2:3] is model (not GroupID); Device ID at [4:5]; GroupID from MQTT config (was showing model e.g. 24 as GroupID)
- SoftAP HTTPS: single TLS session, shorter handshake timeout; quiet captive-portal CONN_EOF/timeout ERROR spam (HTTP :80 unchanged)
