# 릴리스 노트 인덱스

제품은 POWRAY와 연동합니다. 권장 POWRAY FW: **≥ 1.4.6**. SoftAP 포털·플래시 안내는 [README.md](README.md).

## 버전 정책 (2026-09-04)

- **프로덕션 메인라인:** 루트 [`v1.0.1/`](v1.0.1/) (최신). [`v1.0.0/`](v1.0.0/) 유지.
- **아카이브 개발선:** 과거 루트 `v1.x.x` → [`dev/v0.x.x/`](dev/) (메이저 1→0). OTA 「최신」은 `dev/`를 무시합니다.

상세 변경 내용은 각 폴더의 `RELEASE_NOTES.md`에만 두고, 이 파일은 인덱스만 유지합니다.

## 도구

- [`Tools/WIFI_Module_V_ESP-executables.zip`](Tools/WIFI_Module_V_ESP-executables.zip) — PC GUI 실행 파일 묶음 (업로더 + MQTT 테스트 도구)

## 프로덕션

| 버전 | 노트 |
|------|------|
| **v1.0.1** | [v1.0.1/RELEASE_NOTES.md](v1.0.1/RELEASE_NOTES.md) — ID 동기화 개선 |
| v1.0.0 | [v1.0.0/RELEASE_NOTES.md](v1.0.0/RELEASE_NOTES.md) |

요약: **v1.0.1** = Device ID 동기화 보강. v1.0.0 장치는 GitHub/UART OTA로 업그레이드 가능.

## 아카이브 (`dev/`)

과거 공개 1.x.x 이력은 [`dev/CHANGELOG.md`](dev/CHANGELOG.md)와 각 [`dev/v0.*/RELEASE_NOTES.md`](dev/)에 있습니다.
프로덕션 배포·OTA 최신에는 사용하지 마세요.
