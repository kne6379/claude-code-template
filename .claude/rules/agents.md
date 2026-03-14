---
description: 서브에이전트 사용 시 참고 가이드
globs:
  - ".claude/agents/**"
---

# 서브에이전트 가이드

## 사용 가능한 에이전트

- `@code-reviewer`: 코드 리뷰 수행 (품질, 보안, 에러 처리, 성능)
- `@test-runner`: 테스트 실행 및 분석 (프레임워크 자동 감지)
- `@security-auditor`: 보안 취약점 검사 (OWASP Top 10 기반)

## 사용 예시

```
@code-reviewer 변경된 파일들을 리뷰해줘
@test-runner 전체 테스트 실행하고 분석해줘
@security-auditor 인증 모듈 보안 검사해줘
```

## 커스터마이징

`.claude/agents/` 디렉토리의 각 에이전트 파일을 수정하여:
- 검토 기준 조정
- 출력 포맷 변경
- 사용 가능한 도구 제한/확장
