## v0.2.10
- POWRAY A9 status: label ID/GroupID (frame Group[2]+ID[2]), current Current1..3 deci-amps (e.g. 418 → 41.8A)
- Show ALIVE / RSSI / IP results inline below diagnosis buttons (not only in details)
- Remove SUB_TOPICS (토픽) button from POWRAY TEST
- MQTT connected box lists board topics: SUB1 Broadcast, SUB2 CMD, SUB3 System, PUB1 System_R, PUB2 Data

## Archive note (2026-08-06)
- Renamed from **v1.2.10** → **v0.2.10** and moved under `dev/` as part of the production 1.0.0 rebaseline.
- Artifact filenames and text manifests were updated to `v0.2.10`; binary image internal version strings remain the original `1.2.10` (no rebuild).
- `manifest.json` version/URL fields were rewritten for archive layout; the embedded `signature` / `manifest.sig` may no longer verify against the rewritten JSON (archive only — not used for production OTA).
