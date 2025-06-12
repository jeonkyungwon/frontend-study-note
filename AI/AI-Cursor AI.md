# Cursor AI

**Cursor AI**는 개발자들이 더 효율적으로 코드를 작성하고 디버깅할 수 있도록 도와주는 **AI 기반 코드 편집기(IDE)**이다. 현재 가장 유명한 것은 VSCode 기반의 커스텀 IDE인 Cursor이다.

# Cursor AI란?

> **Cursor**는 “AI-first code editor”라는 슬로건을 내세우며, 코드 작성을 중심으로 다양한 AI 기능이 통합된 AI 코드 에디터이다.
> 기존의 VSCode 환경을 기반으로 하며, ChatGPT 또는 GPT-4 기반의 AI가 깊게 통합되어 있다.

# 주요 기능

### 코드 이해 및 요약

선택한 코드 블록에 대해 AI가 설명

> ex. “이 함수는 뭐하는 함수야?”

### 코드 수정 요청

자연어로 수정 요청을 하면 코드가 자동으로 수정

> ex. “이 함수 시간복잡도 줄여줘”

### 자동 리팩토링

`Ctrl+K` → “Make this more readable”, “Use TypeScript” 같은 프롬프트로 코드 개선

### 전체 코드 컨텍스트 학습

프로젝트 전체 구조와 파일을 파악하고 AI가 그 문맥을 기반으로 답변

### 자동 문서 생성

주석 추가, 문서화 자동화 등도 자연어로 가능

### 명령어 팔레트 통합

명령 팔레트에 “Add logging”, “Make this async” 등 커맨드 기반 AI 툴이 있음

### GPT 선택 가능

GPT-3.5, GPT-4, GPT-4o 등 선택 가능. API Key 직접 연동도 가능

# 언제 사용하면 좋을까?

- 복잡한 코드 블록을 이해하거나 요약하고 싶을 때
- 빠르게 버그를 찾거나 리팩토링할 때
- 빠른 프로토타이핑 및 실험적 구현을 할 때
- GPT 기반의 작업을 매끄럽게 IDE에 통합하고 싶을 때

# 자주 사용하는 프롬프트

### 1. 자연어로 컴포넌트 생성

```
"Create a responsive card component using Tailwind and TypeScript"
```

### 2. 코드 리팩토링

```
"Make this component more readable and split into smaller components"
```

### 3. 버그 추적 및 수정

```
"Fix the hydration error in this Next.js component"
"Why is this event not firing?"
```
