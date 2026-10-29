# Security Policy

## 취약점 제보

보안 문제는 공개 이슈로 올리지 말고 GitHub의 **[비공개 취약점 제보](https://github.com/yoojin-aimaker/agent-hq/security/advisories/new)** 로 알려 주세요.
재현 방법과 영향 범위를 적어 주시면 확인 후 답변드립니다.

## 범위

| 대상 | 주의할 점 |
|---|---|
| `index.html` 뷰어 | 다른 사람의 `agent-hq.json`을 읽어 그립니다. 외부 문자열로 스크립트가 실행되면 취약점입니다 |
| `hq.mjs serve` | `127.0.0.1`에만 열립니다. 허용되지 않은 출처에서 보고(POST)가 들어가거나 작업 폴더 밖 파일이 읽히면 취약점입니다 |
| `hq.mjs push` | GitHub 토큰은 `gh auth token` 또는 `GITHUB_TOKEN`에서 읽기만 하고 저장하거나 출력하지 않습니다 |
| `registry/` Actions | PR 검증은 읽기 권한으로만 실행됩니다 |

## 사용자가 지켜야 할 것

- `push`로 올린 `agent-hq.json`은 **공개**됩니다. task 문구에 고객명, 내부 경로, 토큰을 넣지 마세요.
- `hq.mjs serve`를 `0.0.0.0`으로 열거나 외부에 포워딩하지 마세요. 필요하면 `--token`을 쓰세요.
