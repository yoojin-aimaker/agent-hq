# Changelog

이 프로젝트의 주요 변경 사항을 기록합니다. 형식은 [Keep a Changelog](https://keepachangelog.com/ko/1.1.0/)를 따릅니다.

## [Unreleased]

## [3.0.0] - 2026-10-29

누구나 자기 멀티에이전트를 연결할 수 있게 되었습니다.

### Added
- `hq.mjs` 커넥터: `init` `scan` `report` `serve` `push` `validate` (단일 파일, 의존성 0)
- 데이터 형식 v1 `agent-hq.json` + JSON Schema. 층은 team 기준으로 자동 배정
- 뷰어 소스 전환: `?gh=owner/repo`, `?src=local`, `?src=https://…`, CONNECT 패널
- 로비: `registry/<login>.json` PR → GitHub Actions 자동 검증 → 공개 목록
- Python SDK `sdk/python/agent_hq.py`
- 보고가 끊기면 5분 뒤 검토 중, 30분 뒤 대기로 자동 감쇠
- 하단 저작권 표기, 연결 가이드 `docs/CONNECT.md`

### Fixed
- 좁은 화면(980px 미만)에서 화면이 티커 길이만큼 거대하게 늘어나던 문제
- https 페이지에서 로컬 서버 접속이 막히는 브라우저(Safari 등) — `http://127.0.0.1:4173`에서 뷰어를 직접 제공
- Claude 로그 자동 감지가 에이전트 이름이 언급만 돼도 '작업 중'으로 켜던 오탐

### Security
- 외부 데이터를 화면에 넣기 전 HTML 이스케이프, 인라인 이벤트 핸들러 제거
- 로컬 서버는 127.0.0.1에만 열리고 허용된 출처의 요청만 받음

## [2.0.0] - 2026-07-04

### Added
- 야간 빌딩 단면도 픽셀 씬 (캔버스 저해상도 → 3배 확대)
- 타이핑, 모니터 플리커, 엘리베이터, 네온, 유성, 서버랙 LED, 고양이 애니메이션
- 책상 클릭 상세 패널, 필터, 층 로그, 티커, CRT 토글
- `scan.mjs`로 Claude/Codex 에이전트 스캔, `serve.mjs`로 실시간 상태

[Unreleased]: https://github.com/yoojin-aimaker/agent-hq/compare/v3.0.0...HEAD
[3.0.0]: https://github.com/yoojin-aimaker/agent-hq/releases/tag/v3.0.0
[2.0.0]: https://github.com/yoojin-aimaker/agent-hq/commit/065d17f
