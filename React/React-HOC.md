# HOC (고차 컴포넌트)

컴포넌트 로직을 재사용하기 위한 React 기술 중 하나

React API의 일부가 아니며, React의 구성적 특성에서 나오는 패턴

컴포넌트를 가져와 새 컴포넌트를 반환하는 함수

```jsx
const EnhancedComponent = higherOrderComponent(WrappedComponent);
```

> 컴포넌트는 props를 UI로 변환하는 반면, 고차 컴포넌트는 컴포넌트를 새로운 컴포넌트로 변환한다.

### 예시

```jsx
import React, { useEffect, useState } from "react";

export default function withLoading(Component) {
  const WithLoadingComponent = (props) => {
    const [loading, setLoading] = useState(true);

    useEffect(() => {
      const timer = setTimeout(() => setLoading(false), 1000);

      return () => clearTimeout(timer);
    }, []);
  };

  return loading ? <p>로딩 중...</p> : <Component {...props} />;
}
```

```jsx
import React from "react";
import withLoading from "./withLoading";

function Button() {
  return <button>버튼</button>;
}

export default withLoading(Button);
```

### 면접 답변

<aside>

### ✅ 고차 컴포넌트란?

고차 컴포넌트는 하나의 컴포넌트를 입력으로 받아, 새로운 컴포넌트를 반환하는 함수입니다. 즉, 컴포넌트를 인자로 받아 로직을 확정하거나 재사용 가능한 기능을 추가한 컴포넌트를 만들어내는 React의 디자인 패턴입니다. 예를 들어, 공통된 로딩 처리나 권한 검사 로직을 여러 컴포넌트에 반복하지 않고 HOC로 분리해 적용할 수 있습니다.

</aside>
