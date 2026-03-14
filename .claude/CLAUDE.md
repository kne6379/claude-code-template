# Claude Code 프로젝트 템플릿

이 프로젝트는 Claude Code의 다양한 기능(Subagents, Commands, Skills, Hooks)을 활용한 템플릿입니다.

## 프로젝트 구조

```
.claude/
├── agents/           # 서브에이전트 정의 (@멘션으로 호출)
├── commands/         # 슬래시 커맨드 (/명령어로 호출)
├── skills/           # 자동 적용 스킬 (컨텍스트 매칭)
├── rules/            # 경로별 세부 규칙
├── settings.json     # 훅 설정 (이벤트 트리거)
└── CLAUDE.md         # 이 파일 (공통 컨텍스트)
```

## 핵심 원칙

- 코드 변경 시 기존 컨벤션과 스타일을 유지한다
- 에러 메시지는 사용자 친화적으로 작성한다
- 보안 취약점(OWASP Top 10)을 항상 고려한다

## 주요 참고 문서

- 프로젝트 개요 및 사용법: @README.md
- 기능별 사용 가이드: `.claude/rules/` 하위 파일 참조
- 아키텍처 가이드: `.claude/skills/architecture/SKILL.md` (src/app/lib 경로에서 자동 적용)
- 테스트 컨벤션: `.claude/skills/test-conventions/SKILL.md` (테스트 파일에서 자동 적용)
