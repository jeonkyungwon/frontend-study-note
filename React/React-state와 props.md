# state & props

`state` 와 `props` 는 모두 컴포넌트의 데이터를 다루는 방식이지만, **누가 관리하고 변경하는지**에 따라 역할이 다르다.

# State (상태)

- 컴포넌트 내부에서 선언하고 관리하는 동적인 데이터
- 컴포넌트의 UI와 동기화되는 데이터이며, `setState` 등을 통해 변경 가능
- 사용자의 입력, API 응답 등 시간에 따라 바뀌는 값을 담음

```jsx
import { useState } from "react";

function Counter() {
  //여기서 count는 컴포넌트 내부의 state
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>Click: {count}</button>;
}
```

# Props (속성)

- 부모 컴포넌트가 자식 컴포넌트에게 전달하는 읽기 전용 데이터
- 자식은 props를 수정할 수 없고, 읽기만 가능
- 컴포넌트 재사용성과 구성을 높이는 데 사용

```jsx
//여기서 name은 부모가 넘긴 props
function Greeting({ name }) {
  return <h1>Hello, {name}</h1>;
}

// 사용 예
<Greeting name="Kyungwon" />;
```

# state vs props 차이

| 구분      | state                              | props                       |
| --------- | ---------------------------------- | --------------------------- |
| 정의      | 컴포넌트 내부에서 관리하는 데이터  | 부모가 자식에게 주는 데이터 |
| 수정 가능 | setState 또는 set 함수로 수정 가능 | 수정 X, 읽기 전용           |
|           |
| 사용 목적 | 동적 UI 상태 관리                  | 컴포넌트 간 데이터 전달     |
| 소유자    | 해당 컴포넌트 자체                 | 부모 컴포넌트               |

<br/>

### 면접 답변

<aside>

### ✅ state와 props의 차이점에 대해 설명하시오.

state와 props는 모두 React에서 컴포넌트의 데이터를 다루는 방식이지만, 관리 주체와 수정 가능 여부에 따라 차이가 있습니다.

state는 컴포넌트 내부에서 선언하고 관리하는 데이터로, setState 또는 set 함수를 통해 값을 변경할 수 있습니다.

props는 부모 컴포넌트가 자식 컴포넌트에 전달하는 읽기 전용 데이터입니다. 자식 컴포넌트에서는 props를 직접 수정할 수 없고, 전달받아 사용하는 용도로만 사용됩니다.

요약하면, state는 해당 컴포넌트의 내부 상태를 위한 데이터이고, props는 부모에서 전달받는 값이라는 차이가 있습니다.

</aside>
