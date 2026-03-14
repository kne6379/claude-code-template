# Claude Code Template

Claude Code의 Subagents, Commands, Skills, Hooks를 활용한 프로젝트 템플릿입니다.
이 문서에서는 각 기능의 사용법과 커스터마이징 방법을 안내합니다.

## 빠른 시작

```bash
# 이 템플릿을 복제하여 사용
git clone https://github.com/your-username/claude-code-template.git
cd claude-code-template

# .claude 폴더를 프로젝트에 복사
cp -r .claude /your-project/
```

## 구성 요소

```
.claude/
├── agents/                    # Subagents (서브에이전트)
│   ├── code-reviewer.md       # 코드 리뷰 에이전트
│   ├── test-runner.md         # 테스트 실행 에이전트
│   └── security-auditor.md    # 보안 감사 에이전트
│
├── commands/                  # Slash Commands (슬래시 커맨드)
│   ├── review.md              # /review - 코드 리뷰
│   ├── test.md                # /test - 테스트 실행
│   ├── commit.md              # /commit - 커밋 메시지 생성
│   └── document.md            # /document - 문서 생성
│
├── rules/                     # Rules (경로별 세부 규칙)
│   ├── feature-guide.md       # 기능별 사용 가이드
│   ├── agents.md              # 에이전트 가이드
│   ├── commands.md            # 커맨드 가이드
│   ├── hooks.md               # 훅 가이드
│   └── customizing.md         # 커스터마이징 가이드
│
├── skills/                    # Skills (스킬 - 자동 적용)
│   ├── architecture/
│   │   └── SKILL.md           # 아키텍처 가이드
│   └── test-conventions/
│       └── SKILL.md           # 테스트 컨벤션
│
├── settings.json              # Hooks 정의
└── CLAUDE.md                  # 공통 컨텍스트 (간결하게 유지)
```

## 기능별 차이점

| 구분      | Subagents        | Commands      | Skills               | Hooks         |
| --------- | ---------------- | ------------- | -------------------- | ------------- |
| 호출 방식 | 자연어, @멘션    | /명령어       | 자동 (컨텍스트 매칭) | 이벤트 트리거 |
| 컨텍스트  | 별도 (격리)      | 메인 공유     | 메인에 주입          | 외부 실행     |
| LLM 판단  | O                | O             | O                    | X (규칙 기반) |
| 용도      | 복잡한 작업 위임 | 반복 프롬프트 | 자동 가이드          | 강제 규칙     |

## 사용 예시

### Subagents

```
@code-reviewer 변경된 파일들을 리뷰해줘
@test-runner 전체 테스트 실행하고 분석해줘
@security-auditor 인증 모듈 보안 검사해줘
```

### Commands

```
/review              # 코드 리뷰 실행
/test                # 테스트 실행
/commit              # 커밋 메시지 생성
/document src/api    # API 문서 생성
```

### Skills

코드 작성 시 자동으로 적용됩니다:

- `src/**/*.ts` 파일 작성 시 → architecture-guide 적용
- `**/*.test.ts` 파일 작성 시 → test-conventions 적용

### Hooks

자동으로 실행됩니다:

- 위험한 `rm -rf` 명령어를 차단합니다
- TypeScript 파일 변경 시 알림을 표시합니다

## 언제 무엇을 사용할까?

| 상황                     | 추천 기능 | 이유                           |
| ------------------------ | --------- | ------------------------------ |
| 테스트 실행 후 결과 분석 | Subagent  | 로그가 많아 컨텍스트 오염 방지 |
| 코드 리뷰 요청           | Subagent  | 별도 컨텍스트에서 분석         |
| 커밋 메시지 생성         | Command   | 단순 반복 작업                 |
| 코딩 스타일 가이드       | Skill     | 항상 적용되어야 함             |
| 파일 저장 후 포맷팅      | Hook      | 무조건 실행 필요               |
| 위험 명령어 차단         | Hook      | 예외 없이 무조건 차단          |

## 커스터마이징

각 파일을 프로젝트에 맞게 수정할 수 있습니다:

1. **에이전트 수정**: `.claude/agents/` 파일의 검토 기준을 조정합니다
2. **스킬 수정**: `.claude/skills/*/SKILL.md`의 컨벤션을 변경합니다
3. **훅 추가**: `.claude/settings.json`에 자동화 규칙을 추가합니다
4. **커맨드 추가**: `.claude/commands/`에 새 커맨드 파일을 생성합니다

## 참고 문서

- [Claude Code 공식 문서](https://docs.anthropic.com/en/docs/claude-code)
- [Subagents 가이드](https://docs.anthropic.com/en/docs/claude-code/sub-agents)
- [Hooks 가이드](https://docs.anthropic.com/en/docs/claude-code/hooks)

## 라이선스

MIT
