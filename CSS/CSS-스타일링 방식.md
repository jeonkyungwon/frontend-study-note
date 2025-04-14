# CSS 스타일링 방식

### 1. Global CSS

- 스타일링 방식의 기본
- 전역 스타일 파일에서 class 정의 -> HTML/JS에서 불러다 씀
- 유지보수가 힘들다는 단점이 있음 (클래스 이름 충돌, 전역 오염)
- 동적 스타일 어려움 (조건에 따라 색상, 크기 등 바꾸기 어려움)
- 순수 CSS, Sass, SCSS 등이 있음

### 🔎CSS 전처리기

- 기존 CSS 문법에 변수, 조건문, 반복문, 함수 등의 기능을 추가해주는 도구
- `.scss` `.sass` 파일을 `.css`로 변환해서 브라우저가 인식할 수 있게 함

<br/>

### 면접 답변

<aside>
💡

### ✅ CSS 전처리기란?

기존 CSS 문법에 변수, 조건문, 반복문, 함수 등의 기능을 추가해주는 도구로 scss, sass 파일을 css로 변환해서 브라우저가 인식할 수 있게 합니다.

</aside>

<br/>

### Sass / CSS

| 구분        | Sass                                | SCSS                               |
| ----------- | ----------------------------------- | ---------------------------------- |
| 파일 확장자 | `.sass`                             | `.scss`                            |
| 문법 스타일 | 들여쓰기 기반 (중괄호 X)            | CSS와 유사 (중괄호 O, 세미콜론 O)  |
| 사용 난이도 | 더 간결하지만 익숙하지 않을 수 있음 | CSS랑 거의 똑같아서 진입 장벽 낮음 |
| 현재 추세   | 거의 SCSS 위주로 사용               | 가장 많이 쓰임                     |

> Sass의 업그레이드형이 SCSS

### 2. Scoped / Module CSS

- 클래스명을 자동으로 로컬 스코프로 변환해서 충돌 방지
- Vue, React에서 자주 사용

```css
/* Button.module.css */
.button {
  background: blue;
}
/* 실제 렌더링 시: Button_button__abc123 */
```

### 3. Utilty-First CSS

미리 정의된 클래스 조합으로 UI 완성

대표적으로 Tailwind CSS

**특징**

- 라이브러리 타입으로 빠른 스타일 구축
- 다른 방법론과 함께 사용 가능
- 스타일 관점의 작명을 하여 의미론 사용 X
- HTML 코드에 스타일이 강하게 연결
- HTML/CSS 병렬 개발이 불가능, 그렇기에 소규모 팀 또는 단일 엔지니어 개발에 적합

**장점**

- 편안함과 빠른 개발
- 일관된 디자인
- 쉽고 자유로운 커스텀
- 로우 레벨의 스타일 제공
- JS 코드와의 분리

**단점**

- 클린하지 못한 코드
- 클래스명 학습의 러닝 커브
- JS 코드 사용 불가
- HTML/CSS 코드 혼재

### 4. CSS-in-JS

JS 코드 안에서 CSS를 정의하고 적용하는 스타일링 방식

즉, 스타일을 `.css`파일에 따로 작성하는 대신 JS 파일 안에서 컴포넌트와 함께 스타일을 선언

**작동 방식**

```css
import styled from 'styled-components';

const Button = styled.button`
  background-color: ${(props) => (props.primary ? 'blue' : 'gray')};
  color: white;
  padding: 10px 16px;
  border-radius: 4px;
`;

<Button primary>확인</Button>
```

- 스타일이 JS 안에 들어감
- props나 상태(state)에 따라 동적으로 스타일 변경 가능
- 클래스 이름이 자동으로 생성 -> 충돌 걱정 X

**장점**

1. 컴포넌트 기반 개발과 완벽한 궁합

- 스타일과 로직을 한 파일에서 관리 가능
- 코드 응집도가 높고 유지보수가 쉬움

2. 동적 스타일링 가능

- props, state, context 등 JS의 데이터를 바탕으로 스타일 변경 가능

3. 클래스 이름 자동 관리

- 무작위 해시 된 고유 클래스 이름이 생성되어 충돌 방지

4. 조건부 스타일, 테마 관리에 유리

- `ThemeProvider` 같은 기능으로 다크모드, 디자인 시스템 연동에 최적화

**단점**

1. 런타임 성능 이슈

- 스타일이 JS 안에서 동적으로 생성되므로, 렌더링 성능에 영향을 줄 수 있음 -> SSR 환경에선 초기 로딩 늦어질 수 있음

2. 도구 설정 복잡

- styled-components, emotion마다 바벨 플러그인, SSR 설정 등이 필요할 수 있음

**대표 라이브러리**
| 라이브러리 | 특징 |
| --- | --- |
| **styled-components** | React 기반 대표 라이브러리, 문법 직관적 |
| **emotion** | 빠르고 유연한 CSS-in-JS, styled-components와 유사 |
| **Stitches** | 타입스크립트와 궁합 좋고, 정적 스타일 생성 |
| **Vanilla Extract** | 빌드 타임에 CSS 생성 → 런타임 성능 우수 |
| **JSS** | Vue나 기타 JS 프레임워크에도 사용 가능 |

<br/>
<br/>

<aside>

## ✅ Utility-First CSS(Tailwind CSS)란?

Utility-First CSS는 미리 정의된 유틸리티 클래스를 조합해 UI를 구성하는 스타일링 방식입니다.

하나의 클래스가 작은 스타일 속성 하나만 담당하고, 이들을 조합해서 레이아웃이나 디자인을 만들어 나가는 구조입니다.

대표적인 프레임워크로 Tailwind CSS가 있습니다.

Tailwind는 수많은 유틸리티 클래스들을 제공하고, 이를 HTML에 직접 작성함으로써 빠른 개발 속도, 일관된 디자인, 자유로운 커스터마이징이 가능하다는 장점이 있습니다.

다만 HTML 안에 클래스가 많아지고, JS처럼 동적 스타일을 직접 다룰 수는 없다는 점에서 가독성과 코드 분리 측면에서는 단점도 존재합니다.

</aside>

<br/>

<aside>

## ✅ CSS-in-JS란?

CSS-in-JS는 JavaScript 파일 안에서 스타일을 정의하고, 컴포넌트 단위로 관리할 수 있게 해주는 방식입니다.

주로 React 기반 프로젝트에서 사용되며, 동적 스타일링, 클래스 충돌 방지, 테마 설정 등에 강점을 가지고 있습니다.

대표적으로 styled-components, emotion 등이 있습니다.

</aside>
