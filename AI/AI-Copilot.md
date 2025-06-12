# GitHub Coplit

GitHub와 OpenAI가 함께 만든 AI 코드 자동 완성 도구로 VS Code 같은 다양한 코드 편집기에서 사용 가능하고, GPT-4 또는 GPT-3.5 기반으로 동작

# 주요 특징

### 코드 자동 완성

함수 이름만 타이핑해도 전체 함수 몸체를 자동 제안

### 여러 줄 생성

주석 기반으로 여러 줄 코드 생성

> `fetch data from API` 등

### 문맥 인식

파일 전체, 현재 프로젝트 문맥을 일부 파악하여 제안

### 다양한 언어 지원

JavaScript, TypeScript, HTML, CSS, Python 등 다중 언어 지원

### 지속 업데이트

이제 GPT-4 기반의 Copilot X도 일부 제공 중 (챗봇 기능 등 포함)

# 언제 사용하면 좋을까?

- 빠르게 코드 작성하고 싶을 때
- 로그인, fetch, map 등 반복 로직 자동화

# 자주 사용하는 파트

### 1. 컴포넌트 빠른 초안

```tsx
// A button component with hover animation
```

- 주석만 달아도 Copilot이 적절한 JSX + CSS-in-JS를 자동 생성

### 2. API 호출/에러 처리 자동완성

```tsx
// Fetch posts from /api/posts and show in a list
```

- fetch → error handling → JSX 렌더링까지 한번에 생성

### 3. Form, 상태 관리 패턴 추론

```tsx
// useReducer for form input management
```

- 상태 로직과 dispatch 구조까지 자동 완성됨

### 4. 유틸 함수 자동 완성

```tsx
function validateEmail(email: string) {
```

- 함수 이름만 입력하면 내부 로직을 추측해 자동 작성
