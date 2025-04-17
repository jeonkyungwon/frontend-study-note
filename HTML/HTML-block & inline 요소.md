# Block 요소

한 줄 전체를 차지하는 요소로, 새로운 줄에서 시작하고 다음 요소 역시 새 줄에서 시작하게 만드는 성질을 가짐(수직으로 쌓임)

### 특징

- 항상 새로운 줄에서 시작
- 한 줄 전체의 너비를 차지(width: 100%)
- 내부에 다른 block 요소나 inline 요소 모두 포함 가능
- 크기(width, height) 지정이 자유로움
- 브라우저가 자동으로 줄바꿈을 해줌

### 예시

```html
<!-- Block 요소 예시 -->
<div>첫 번째 블록</div>
<div>두 번째 블록</div>
```

-> 결과:

| 첫 번째 블록 |
| ------------ |
| 두 번째 블록 |

### 대표적인 Block 요소

`<div>, <p>, <h1>~<h6>, <ul>, <ol>, <li>, <section>, <article>, <header>, <footer>, <nav>, <form>, <table>` 등

<br/>

# inline 요소

내용만틈의 너비만 차지하는 요소로, 줄바꿈이 되지 않고 같은 줄에 나란히 배치(수평으로 나란히 배치)

### 특징

- 줄바꿈 X(같은 줄에 계속 배치)
- 요소의 내용만큼만 너비 차지
- width, height 속성을 지정해도 적용 X(CSS에서 `display: block`등으로 바꿔야 가능)
- block 요소를 포함할 수 없고 오직 다른 inline 요소나 텍스트만 포함 가능

### 예시

```html
<!-- Inline 요소 예시 -->
<span>첫 번째 인라인</span>
<span>두 번째 인라인</span>
```

-> 결과

| 첫 번째 인라인 | 두 번째 인라인 |
| -------------- | -------------- |

<br/>

# inline-block 요소

inline처럼 나란히 배치되면서도, block처럼 width, height 지정이 가능한 요소로 버튼을 만들 때 자주 사용

```css
button {
  display: inline-block;
  width: 100px;
  height: 40px;
}
```

<br/>
<br/>

### 면접 답변

<aside>

### ✅ block과 inline 요소의 차이에 대해서 설명하시오.

block 요소는 한 줄 전체를 차지하고 줄바꿈이 일어나는 반면, inline 요소는 나란히 배치되며 줄바꿈이 되지 않고 내용만큼만 공간을 차지합니다.

block 요소는 다른 block 요소나 inline 요소를 자식으로 포함할 수 있지만, inline 요소는 텍스트나 다른 inline 요소만 포함할 수 있습니다.

또한 block 요소는 높이나 너비 값을 지정할 수 있지만, inline 요소는 크기 지정이 어렵고 텍스트 흐름에 맞춰 자동으로 크기가 정해집니다.

</aside>

<aside>

### ✅ inline-block에 대해 설명하시오.

inline-block은 HTML 요소의 display 속성 중 하나로, inline 요소처럼 나란히 배치되면서 block 요소처럼 너비와 높이를 지정할 수 있는 속성입니다.

주로 버튼이나 네비게이션 메뉴처럼 여러 요소를 가로로 나열하면서 각 요소에 크기를 설정하거나 간격을 주고 싶을 때 사용합니다.

</aside>
