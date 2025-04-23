# 반응형 웹

화면 크기나 디바이스 종류에 따라 레이아웃이나 콘텐츠의 스타일이 자동으로 조정되는 웹 디자인 방식

> 즉 하나의 HTML 문서로 다양한 해상도와 디바이스에 최적화된 화면을 제공하는 것을 목표로 함

### 주요 방법

1. 미디어 쿼리 (Media Query) : 가장 대표적인 방법으로 디바이스의 화면 너비, 높이, 해상도 등에 따라 스타일을 다르게 적용

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

1. 유동적인 단위 사용 : 고정 px 대신 `%, vw, vh, rem, em` 등의 단위를 사용하며 부모 요소나 뷰포트에 따라 유연하게 크기 조절 가능

```css
width: 100%; /* 부모 기준 */
font-size: 1.2rem; /* 루트 요소 기준 */
```

**※ em과 rem의 차이**

- CSS에서 상대 단위를 나타내는 단위로, 둘 다 기준 값에 비례해서 크기를 설정하는 단위 (기준이 어디냐에 따라 차이가 있음)

**차이 요약**

| 구분      | `em`                             | `rem`                                    |
| --------- | -------------------------------- | ---------------------------------------- |
| 의미      | **부모 요소의 폰트 크기**를 기준 | **최상위 요소(html)의 폰트 크기**를 기준 |
| 계산 기준 | **상위 요소에 따라 바뀜 (상속)** | **항상 html 요소 기준**                  |
| 사용 용도 | 버튼 안 폰트 크기, 패딩 등       | 전체적인 폰트 크기 조정 시               |
| 중첩 영향 | 중첩되면 곱해짐 → 예측 어려움    | 예측 쉬움 (일관성 유지됨)                |

**예제 비교**

```css
<style>
  html {
    font-size: 16px; /* 기준 rem 크기 */
  }
  .parent {
    font-size: 20px;
  }
  .child-em {
    font-size: 2em; /* 20px * 2 = 40px */
  }
  .child-rem {
    font-size: 2rem; /* 16px * 2 = 32px */
  }
</style>

<div class="parent">
  <div class="child-em">em 기준</div>
  <div class="child-rem">rem 기준</div>
</div>
```

- `child-em` 은 부모 폰트 20px x 2 = 40px
- `child-rem` 은 html 폰트 16px x 2 = 32px

> em은 중첩 시 곱셈

1. Flexible Layout (Flexbox, Grid) : Flexbox와 CSS Grid를 사용하면 레이아웃 자체가 유연하게 움직이도록 설계 가능

```css
display: flex;
flex-wrap: wrap;
```

1. 모바일 우선 접근 : 기본 스타일을 모바일 기준으로 작성하고, 더 큰 화면에 대해 미디어 쿼리로 스타일을 확장
2. CSS Framework 사용 : Tailwind CSS, Bootstrap 등에서 반응형 유틸리티 클래스 제공

```css
<div class="text-base md:text-lg lg:text-xl">텍스트</div>
```

<aside>

### ✅ 반응형 웹에 대해 설명해주세요.

반응형 웹이란 하나의 웹 페이지가 다양한 화면 크기와 디바이스 환경에 따라 자동으로 스타일을 조절하는 웹 디자인 방식입니다.

미디어 쿼리, 상대 단위, 유연한 레이아웃 등을 활용해 사용자 경험을 일관되게 제공합니다.

</aside>
