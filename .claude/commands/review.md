---
description: 코드 리뷰 실행
---

# 코드 리뷰

변경된 코드에 대해 종합적인 리뷰를 수행합니다.

## 수행 단계

1. **변경 사항 확인**
   - `git diff` 또는 `git diff --staged`로 변경된 파일 확인

2. **코드 리뷰 수행**
   - **code-reviewer** 서브에이전트를 사용하여 코드 품질 검토
   - 코딩 컨벤션, 가독성, 유지보수성 평가

3. **보안 검사**
   - **security-auditor** 서브에이전트를 사용하여 보안 취약점 검사

4. **결과 종합**
   - 발견된 이슈를 우선순위별로 정리
   - 개선 제안 제공

## 인자

- `$ARGUMENTS`: 리뷰할 특정 파일 또는 디렉토리 (선택사항)

## 예시

```bash
/review                    # 모든 변경 사항 리뷰
/review src/auth          # auth 디렉토리만 리뷰
/review --staged          # staged 파일만 리뷰
```
