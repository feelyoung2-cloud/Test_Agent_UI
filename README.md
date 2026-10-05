# Test_Agent_UI

이 저장소는 `.claude/settings.json`으로 Claude Code 스킬/플러그인을 등록해 둔 상태입니다.
등록된 마켓플레이스는 `/plugin` 명령으로 바로 설치할 수 있고, 업스트림 업데이트를 그대로 따라갑니다.

## 활성화된 플러그인

| 플러그인 | 저장소 | 용도 |
|---|---|---|
| `superpowers` | [obra/superpowers-marketplace](https://github.com/obra/superpowers-marketplace) | 브레인스토밍·TDD·디버깅·코드리뷰 등 개발 워크플로 스킬 |
| `ui-ux-pro-max` | [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | UI/UX 디자인 인텔리전스 (스타일·색상·타이포·차트·UX 가이드라인 검색 DB) |
| `taste-skill` | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | 프런트엔드 디자인 취향 스킬 (brutalist, minimalist, soft, redesign 등) |
| `andrej-karpathy-skills` | [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) | LLM 코딩 실수를 줄이는 행동 지침 (Think Before Coding, Simplicity First 등) |
| `harness` | [revfactory/harness](https://github.com/revfactory/harness) | 에이전트 팀(하네스) 설계 메타 스킬 |
| `kordoc` | [chrisryugj/kordoc](https://github.com/chrisryugj/kordoc) | HWP/HWPX/PDF/DOCX 등 한국 공문서 파싱·생성 |
| `watch` | [bradautomates/claude-video](https://github.com/bradautomates/claude-video) | 영상(URL/로컬) 시청·분석: yt-dlp + ffmpeg + 자막/Whisper (Python 3.10+ 필요) |
| `impeccable` | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | UI 디자인 품질 스킬. 훅이 세션 시작·도구 호출·종료마다 실행되며 엔진 바이너리를 GitHub 릴리스에서 받아 실행하므로, 원치 않으면 `enabledPlugins`에서 `false`로 되돌릴 것 |

## 등록만 하고 꺼 둔 플러그인

켜려면 `.claude/settings.json`의 `enabledPlugins`에서 해당 항목을 `true`로 바꾸거나 `/plugin install <이름>@<마켓플레이스>`를 실행합니다.

| 플러그인 | 꺼 둔 이유 |
|---|---|
| `claude-mem@thedotmack` | 기본값이 로그인이 필요한 호스팅 메모리(세션 내용이 외부로 전송)이며 모든 이벤트에 훅이 걸림 |
| `ecc@ecc` | SKILL.md 1,000개 이상 + 훅 24개로 컨텍스트 부담이 큼 |
| `codex@openai-codex` | Codex CLI(`npm i -g @openai/codex`)와 로그인이 필요함 |
| `caveman@caveman` | 모든 응답 스타일을 압축체로 바꿈 |

설치만 해 두고 필요할 때 고르는 대형 마켓플레이스:

- `claude-code-workflows` ([wshobson/agents](https://github.com/wshobson/agents)) — 플러그인 94개
- `google-plugins` ([google/skills](https://github.com/google/skills)) — Google Cloud 관련 플러그인 17개
- `superpowers-marketplace`에는 `superpowers` 외에 `superpowers-chrome`, `episodic-memory` 등 9개가 더 있음

## 마켓플레이스가 없어 수동 설치가 필요한 항목

- **playwright** ([microsoft/playwright](https://github.com/microsoft/playwright)): `npm i -g @playwright/cli@latest` 후 `playwright-cli install --skills`
- **Agent-Reach** ([Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach)): `pip install agent-reach` 후 `agent-reach install --env=auto`. 기본은 점검만 하며, `--system`을 붙여야 시스템 변경과 스킬 등록이 일어남. 이 스킬은 웹 검색·URL 요청 전반에 우선 적용되도록 작성되어 있으니 필요할 때만 설치할 것
- **harness-100** ([revfactory/harness-100](https://github.com/revfactory/harness-100)): 하네스 폴더를 골라 `cp -r en/<NN-name>/.claude/ <프로젝트>/.claude/`로 복사. 전부 복사하면 스킬이 수백 개가 되므로 UI 프로젝트라면 `36-design-system`, `16-fullstack-webapp` 정도를 후보로 볼 것

## 참고

- [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)는 스킬이 아니라 큐레이션 목록이라 설치 대상이 아닙니다.
