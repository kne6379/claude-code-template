---
description: 훅 설정 변경 시 참고 가이드
globs:
  - ".claude/settings.json"
---

# 훅 가이드

## 현재 설정된 훅

### PreToolUse - 도구 실행 전
- **위험 명령어 차단**: `rm -rf /`, `rm -rf ~`, `rm -rf *` 실행 차단

### PostToolUse - 도구 실행 후
- **TypeScript 파일 알림**: `.ts`, `.tsx` 파일 생성/수정 시 알림

### Notification - 알림
- **일반 알림**: Claude Code 알림 메시지 출력

## 훅 추가 방법

`.claude/settings.json`의 `hooks` 객체에 새 훅을 추가합니다.

사용 가능한 이벤트:
- `PreToolUse`: 도구 실행 전 (차단 가능)
- `PostToolUse`: 도구 실행 후
- `Notification`: 알림 발생 시

## 주의사항

- 훅은 LLM 판단 없이 규칙 기반으로 무조건 실행됩니다
- `exit 1`로 종료하면 해당 도구 실행이 차단됩니다
- 환경변수 `$TOOL_INPUT`으로 도구 입력값에 접근할 수 있습니다
