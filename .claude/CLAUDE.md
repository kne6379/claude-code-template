# Claude Code 프로젝트 컨텍스트

이 프로젝트는 Claude Code의 다양한 기능을 활용한 템플릿입니다.

## 프로젝트 구조

```
.claude/
├── agents/           # 서브에이전트 정의
├── commands/         # 슬래시 커맨드
├── skills/           # 자동 적용 스킬
├── settings.json     # 훅 설정
└── CLAUDE.md         # 이 파일
```

## 사용 가능한 기능

### 서브에이전트 (@멘션으로 호출)
- `@code-reviewer`: 코드 리뷰 수행
- `@test-runner`: 테스트 실행 및 분석
- `@security-auditor`: 보안 취약점 검사

### 슬래시 커맨드
- `/review`: 종합 코드 리뷰
- `/test`: 테스트 실행
- `/document`: 문서 생성

### 스킬 (자동 적용)
- `architecture-guide`: 코드 작성 시 아키텍처 가이드
- `test-conventions`: 테스트 작성 시 컨벤션

### 훅 (자동 실행)
- 위험한 명령어 차단
- 파일 변경 알림

## 커스터마이징

각 파일을 프로젝트에 맞게 수정하여 사용하세요:
- 에이전트의 검토 기준 조정
- 스킬의 컨벤션 변경
- 훅의 자동화 규칙 추가
