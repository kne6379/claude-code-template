---
name: architecture-guide
description: 코드 작성 시 프로젝트 아키텍처 가이드 자동 적용
globs:
  - "src/**/*"
  - "app/**/*"
  - "lib/**/*"
---

# 프로젝트 아키텍처 가이드

이 가이드는 프로젝트의 코드 품질과 일관성을 유지하기 위한 범용 원칙입니다.

## 코드 구조 원칙

### 1. 단일 책임 원칙 (SRP)
- 파일/모듈당 하나의 주요 책임
- 함수는 하나의 작업만 수행
- 클래스는 하나의 변경 이유만 가짐

### 2. 계층 분리
```
[Presentation Layer] → [Business Logic] → [Data Access] → [External Services]
```
- 각 계층은 자신보다 하위 계층만 의존
- 순환 의존성 금지

### 3. 의존성 주입
- 하드코딩된 의존성 대신 주입 사용
- 테스트 용이성 확보

## 네이밍 컨벤션

### 일반 규칙
- 변수/함수: `camelCase`
- 클래스/타입: `PascalCase`
- 상수: `SCREAMING_SNAKE_CASE`
- 파일명: 언어/프레임워크 컨벤션 준수

### 의미 있는 이름
- 동사로 시작하는 함수명 (예: `getUserById`, `calculateTotal`)
- 명사로 된 변수명 (예: `userList`, `totalAmount`)
- Boolean은 is/has/can 접두사 (예: `isActive`, `hasPermission`)

## 에러 처리

### 원칙
- 에러는 적절한 계층에서 처리
- 복구 가능한 에러와 치명적 에러 구분
- 의미 있는 에러 메시지 제공

### 패턴
- 비즈니스 로직에서 예외 정의
- 프레젠테이션 계층에서 사용자 친화적 메시지 변환
- 로깅은 적절한 레벨로 수행

## 코드 품질

### DRY (Don't Repeat Yourself)
- 중복 코드는 함수/모듈로 추출
- 단, 과도한 추상화 지양

### KISS (Keep It Simple, Stupid)
- 불필요한 복잡성 제거
- 명확하고 읽기 쉬운 코드 우선

### YAGNI (You Aren't Gonna Need It)
- 현재 필요한 기능만 구현
- 미래의 가상 요구사항 배제
