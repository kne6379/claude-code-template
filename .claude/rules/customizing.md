# 커스터마이징 가이드

이 템플릿을 프로젝트에 맞게 수정하는 방법을 안내합니다.

## 수정 대상

1. **CLAUDE.md** (`.claude/CLAUDE.md`)
   - 프로젝트별 핵심 원칙 및 컨벤션 추가
   - 빌드/테스트 명령어 기재
   - 200줄 이하로 유지 권장

2. **에이전트** (`.claude/agents/*.md`)
   - 검토 기준 조정
   - 사용 가능 도구 변경

3. **스킬** (`.claude/skills/*/SKILL.md`)
   - 아키텍처/테스트 컨벤션 변경
   - `globs` 패턴으로 적용 경로 조정

4. **훅** (`.claude/settings.json`)
   - 자동화 규칙 추가/수정
   - 차단할 명령어 패턴 추가

5. **커맨드** (`.claude/commands/*.md`)
   - 새 슬래시 커맨드 추가

6. **규칙** (`.claude/rules/*.md`)
   - 경로별 세부 규칙 추가
   - `globs` frontmatter로 적용 범위 지정

## 규칙 파일 작성법

```markdown
---
description: 규칙 설명
globs:
  - "src/api/**/*.ts"
---

# 규칙 제목

구체적이고 검증 가능한 규칙을 작성해야 합니다:
- Good: "2칸 들여쓰기를 사용한다"
- Bad: "코드를 깔끔하게 작성한다"
```
