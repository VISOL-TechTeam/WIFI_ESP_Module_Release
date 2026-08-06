# 릴리스 노트 인덱스

제품은 POWRAY와 연동합니다. 권장 POWRAY FW: **≥ 1.4.6**. SoftAP 포털·플래시 안내는 [README.md](README.md).

## 버전 정책 (2026-08-06)

- **프로덕션 메인라인:** 루트 [`v1.0.0/`](v1.0.0/) (구 개발선 **1.3.3** 기능을 1.0.0으로 리베이스)
- **아카이브 개발선:** 과거 루트 `v1.x.x` → [`dev/v0.x.x/`](dev/) (메이저 1→0). OTA 「최신」은 `dev/`를 무시합니다.

상세 변경 내용은 각 폴더의 `RELEASE_NOTES.md`에만 두고, 이 파일은 인덱스만 유지합니다.

## 도구

- `Tools/Visol_WIFI_Module_FW_Uploader.exe` — PC GUI 업로더

## 프로덕션

| 버전 | 노트 |
|------|------|
| **v1.0.0** | [v1.0.0/RELEASE_NOTES.md](v1.0.0/RELEASE_NOTES.md) |

요약: SoftAP `/sta` 잠금 상태에서도 비밀번호 표시(눈 아이콘), 연결 테스트 안정화(MQTT pause / SoftAP disconnect), Flash **4MB**. 구 개발선 1.3.3과 기능적으로 동일 계열입니다.

## 아카이브 (`dev/`)

과거 공개 1.x.x 이력은 [`dev/CHANGELOG.md`](dev/CHANGELOG.md)와 각 [`dev/v0.*/RELEASE_NOTES.md`](dev/)에 있습니다.
프로덕션 배포·OTA 최신에는 사용하지 마세요.
