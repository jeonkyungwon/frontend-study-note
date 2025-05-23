# TypeScript

마이크로소프트에서 개발한 JavaScript의 상위 집합 언어

- `.ts` 확장자를 사용
- JavaScript에 정적 타입 시스템과 객체 지향적 요소(인터페이스, 제네릭, 접근 제한자 등)를 추가한 언어
- 작성된 TypeScript 코드는 트랜스파일(transpile) 과정을 거쳐 JavaScript로 변환되어 브라우저에서 실행

## 특징 및 장점

### 1. 정적 타입 검사

- 변수, 함수, 매개변수, 반환 값 등에 타입을 명시함으로써 컴파일 타임에 오류를 미리 발견 가능

```tsx
function add(a: number, b: number): number {
  return a + b;
}
add(1, "2"); // ❌ 문자열 전달 시 컴파일 에러
```

### 2. IDE 자동 완성 및 코드 인텔리센스 향상

- 타입 정보 덕분에 코드 작성 시 자동 완성, 경고, 추론 등 개발자 경험이 향상

### 3. 객체지향 프로그래밍 지원

- 클래스, 인터페이스, 접근 제어자(public/private/protected) 등을 지원해, 대규모 프로젝트에 적합

### 4. 리펙토링 용이

- 코드 규모가 커져도, 타입 기반으로 정확한 리팩토링 가능(예 : 변수 이름 변경 시 타입 기반으로 연관된 부분 자동 수정)

### 5. JavaScript와 100% 호환

- 기존 JS 프로젝트에도 점진적으로 도입 가능(파일 하나씩 `.ts`로 변환해가며 사용 가능)

### 단점

- 타입 선언과 제네릭 등으로 초반 학습 진입장벽이 있음
- 코드량이 다소 많아짐(타입 선언 추가 등)
- 빌드/컴파일 과정이 필요(하지만 대부분 설정 자동화 가능)

## TypeScript vs JavaScript 비교

| 항목        | JavaScript                       | TypeScript                           |
| ----------- | -------------------------------- | ------------------------------------ |
| 타입 시스템 | 동적 타입 (런타임에서 오류 발생) | 정적 타입 (컴파일 타임에 오류 체크)  |
| 에러 탐지   | 실행 후 확인 가능                | 개발 중 확인 가능                    |
| 규모        | 소규모 스크립트에 적합           | 대규모 프로젝트에 적합               |
| 객체지향    | 기본적 지원 부족                 | 인터페이스, 제네릭 등 OOP 기능 지원  |
| 학습 곡선   | 낮음                             | 다소 있음 (초반 타입 개념 학습 필요) |
| 코드 보수성 | 낮음                             | 높음 (리팩토링에 강함)               |

<br/>

### 면접 답변

<aside>

### ✅ TypeScript란?

TypeScript는 JavaScript의 슈퍼셋으로, 정적 타입 시스템을 도입한 프로그래밍 언어입니다.

기존 JavaScript 문법 위에 타입을 지정할 수 있어서, 코드 작성 시점에 오류를 사전에 확인할 수 있고, 대규모 프로젝트에서도 안정적인 개발과 유지보수가 가능합니다.

또한 타입 정보 덕분에 IDE의 자동완성(IntelliSense)과 코드 탐색 기능이 강화되어 개발 생산성과 협업 효율이 높아지는 장점이 있습니다.

TypeScript는 작성 후 JavaScript로 트랜스파일되어 브라우저에서 실행되기 때문에, 기존 JS 생태계와도 호환됩니다.

</aside>
