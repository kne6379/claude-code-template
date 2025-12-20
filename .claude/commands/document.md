---
description: 문서화 생성
---

# 문서화 생성

코드에 대한 문서를 자동으로 생성합니다.

## 수행 단계

1. **코드 분석**
   - 지정된 파일 또는 모듈 구조 분석
   - 함수, 클래스, 인터페이스 식별

2. **문서 생성**
   - API 문서 생성
   - 사용 예시 작성
   - 타입 정의 문서화

3. **README 업데이트**
   - 필요 시 README.md 업데이트 제안

## 인자

- `$ARGUMENTS`: 문서화할 파일 또는 디렉토리

## 예시

```bash
/document src/api         # API 디렉토리 문서화
/document src/utils/date.ts  # 특정 파일 문서화
/document --readme        # README.md 업데이트
```

## 출력 형식

- JSDoc/TSDoc 형식의 인라인 문서
- Markdown 형식의 외부 문서 (필요 시)
