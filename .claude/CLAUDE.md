# Project Harnesses

이 프로젝트에는 [revfactory/harness-100](https://github.com/revfactory/harness-100)(Apache-2.0, 라이선스는 `.claude/licenses/harness-100-LICENSE`)에서 가져온 두 하네스가 설치되어 있습니다.
스킬 파일명은 Claude Code가 인식하도록 업스트림의 `skill.md`를 `SKILL.md`로 바꿨습니다.

두 하네스 모두 산출물을 `_workspace/00_input.md`에 쓰므로, 한 작업이 끝나기 전에 다른 하네스를 실행하지 마세요.

## 36-design-system — UI 디자인 시스템

토큰 → 컴포넌트 → Storybook → 접근성 검증 → 문서화를 에이전트 팀이 수행합니다.
`/design-system` 스킬을 호출하거나 "디자인 시스템 만들어줘"처럼 요청하세요.

- 에이전트: `token-designer`, `component-developer`, `a11y-auditor`, `storybook-builder`, `doc-writer`
- 스킬: `design-system`(오케스트레이터), `wcag-checker`, `token-generator`
- 산출물(`_workspace/`): `01_design_tokens/`, `02_components/`, `03_storybook/`, `04_a11y_report.md`, `05_docs/`

## 16-fullstack-webapp — 풀스택 웹앱

요구사항 → 설계 → 프런트 → 백엔드 → 테스트 → 배포 파이프라인을 에이전트 팀이 수행합니다.
`/fullstack-webapp` 스킬을 호출하거나 "웹앱 만들어줘"처럼 요청하세요.

- 에이전트: `architect`, `frontend-dev`, `backend-dev`, `qa-engineer`, `devops-engineer`
- 스킬: `fullstack-webapp`(오케스트레이터), `component-patterns`, `api-security-checklist`
- 산출물: `_workspace/01_architecture.md` ~ `06_review_report.md`, 프로젝트 루트의 `src/`

## playwright-cli

`.claude/skills/playwright-cli`는 `playwright-cli install --skills`가 생성한 스킬입니다. 실제로 쓰려면 `npm i -g @playwright/cli@latest`가 필요합니다.
