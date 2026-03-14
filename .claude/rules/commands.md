---
description: 슬래시 커맨드 사용 시 참고 가이드
globs:
  - ".claude/commands/**"
---

# 슬래시 커맨드 가이드

## 사용 가능한 커맨드

- `/review [경로]`: 종합 코드 리뷰 (code-reviewer + security-auditor 연동)
- `/test [경로|패턴]`: 테스트 실행 및 분석
- `/commit`: 커밋 메시지 생성 (Conventional Commits 형식)
- `/document [경로]`: 문서 생성 (JSDoc/TSDoc + Markdown)

## 사용 예시

```
/review                  # 전체 변경사항 리뷰
/review src/api          # 특정 경로 리뷰
/test                    # 전체 테스트 실행
/test src/utils          # 특정 경로 테스트
/commit                  # 스테이지된 변경사항으로 커밋 메시지 생성
/document src/api        # API 문서 생성
```

## 커스터마이징

`.claude/commands/` 디렉토리에 새 `.md` 파일을 추가하여 커맨드를 확장할 수 있습니다.
