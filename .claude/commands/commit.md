---
description: 커밋 메시지 생성
---

# 커밋 메시지 생성

변경 사항을 분석하여 커밋 메시지를 작성합니다.

## 수행 단계

1. **변경 사항 확인**

   - `git diff --staged` 또는 `git diff`로 변경 내용 확인

2. **커밋 메시지 작성**
   - Conventional Commits 형식 사용
   - 변경 유형과 범위 파악
   - 간결하고 명확한 메시지 작성

## 커밋 메시지 형식

```
<type>(<scope>): <subject>

<body>
```

### Type

- `feat`: 새 기능
- `fix`: 버그 수정
- `refactor`: 리팩토링
- `docs`: 문서 변경
- `test`: 테스트 추가/수정
- `chore`: 빌드, 설정 변경

### 예시

```
feat(auth): 로그인 API 추가

- JWT 토큰 발급 구현
- 리프레시 토큰 로직 추가
```

## 인자

- `$ARGUMENTS`: 추가 컨텍스트 (선택사항)

## 예시

```bash
/commit                    # staged 변경사항으로 메시지 생성
/commit 로그인 기능 완료    # 컨텍스트 추가
```
