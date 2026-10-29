# Contributing

Agent HQ에 관심 가져 주셔서 고맙습니다. 작은 오타 수정부터 새 프레임워크 연결 예제까지 모두 환영합니다.

## 무엇을 도울 수 있나

- **내 빌딩 등록** — `registry/<내 GitHub 아이디>.json` 하나를 PR로 추가 ([방법](docs/CONNECT.md#4-로비에-등록하기-선택))
- **연결 예제** — LangGraph, CrewAI, AutoGen, n8n 등에서 `hq.report(...)`를 넣는 짧은 예제
- **버그 제보** — [Issues](https://github.com/yoojin-aimaker/agent-hq/issues)에 재현 방법과 브라우저/OS를 적어 주세요
- **아이디어** — [Discussions](https://github.com/yoojin-aimaker/agent-hq/discussions)에서 먼저 이야기해요

## 지켜 주세요 (프로젝트 원칙)

1. **빌드 도구·프레임워크·npm 의존성 없음.** 뷰어는 `index.html` 하나, 커넥터는 `hq.mjs` 하나로 유지합니다.
2. **픽셀 감성 유지.** 저해상도 캔버스 384×288, 3배 확대, 90ms 틱은 바꾸지 않습니다. 스프라이트는 low 캔버스에, 글자는 hi 레이어에.
3. **외부 데이터는 믿지 않습니다.** 화면에 넣는 모든 문자열은 `esc()`를 거칩니다. `innerHTML`에 날것을 넣는 PR은 받지 않습니다.
4. **아무것도 없어도 깨지지 않게.** 서버, 네트워크, 폰트가 없어도 데모는 떠야 합니다.

설계 배경은 [docs/HANDOFF.md](docs/HANDOFF.md), 진행 상황은 [docs/ROADMAP.md](docs/ROADMAP.md)에 있습니다.

## 로컬에서 확인하기

```bash
node --check hq.mjs
node hq.mjs init && node hq.mjs report test --status active --task "확인"
node hq.mjs serve            # http://127.0.0.1:4173
node tools/registry.mjs check
```

화면을 바꿨다면 PR에 변경 전후 스크린샷을 붙여 주세요. 브라우저 콘솔에 에러가 없어야 합니다.

## PR 규칙

- 한 PR에는 한 가지 변경만
- 커밋 메시지 앞에 `feat:` `fix:` `docs:` `chore:` 중 하나
- 사용자에게 보이는 변경이면 [CHANGELOG.md](CHANGELOG.md)의 `Unreleased`에 한 줄 추가

이 프로젝트에 참여하는 모든 분은 [행동 강령](CODE_OF_CONDUCT.md)을 따릅니다.
