# 동기 (Synchronous)

- 한 번에 하나의 작업만 실행
- 이전 작업이 완료되어야 다음 작업이 실행
- 코드가 위에서 아래로 순차적으로 실행

### 예시 코드

```jsx
console.log("안녕");
console.log("하세요");
console.log("전경원입니다.");

//1. 안녕
//2. 하세요
//3. 전경원입니다.
```

> 시간이 오래 걸리는 작업이 있을 경우, 전체 프로그램이 멈춰서 기다려야 하는 문제점이 있음

# 비동기

- 여러 개의 작업을 동시에 처리 가능
- 작업이 끝날 때까지 기다리지 않고, 다음 코드 실행
- 대표적인 비동기 작업
  1. 네트워크 요청(fetch, API, XMLHttpRequest)
  2. 타이머(setTimeout)
  3. 이벤트 리스터

### 예시 코드

```jsx
console.log("순서");

setTimeout(() => {
  console.log("시간이 걸려용");
});

console.log("먼저 갑니다~");

//1. 순서
//2. 먼저 갑니다~
//(2초 후) 3. 시간이 걸려용
```

> 시간이 오래 걸리는 작업이 있어도 다른 작업을 동시에 실행 가능
> UI 반응성 개선(사용자가 기다리지 않아도 된다)

# 비동기 처리 방법

## 1. Callback(콜백 함수)

특정 작업이 완료된 후 실행되는 함수

즉, 함수 실행이 끝난 후 해야 할 작업을 미리 정의해놓고 실행하는 방식

### 예시 코드

```jsx
function fetchData(callback) {
  setTimeout(() => {
    console.log("콜백아 고마워");
    callback();
  }, 2000);
}

function processData() {
  console.log("아 늦었네 ㅋㅋㅋㅋ");
}

fetchData(processData);

//콜백아 고마워
//아 늦었네 ㅋㅋㅋㅋ
```

### 콜백 함수는 언제 사용해야 할까?

주로 비동기 작업을 제어할 때 사용

- 비동기 네트워크 요청(API 호출)
- 이벤트 헨들러
- 타이머

> 즉각적인 반응이 필요한 경우 적합

### 콜백 지옥

콜백을 과도하게 중첩해서 사용하면 코드가 읽기 어려워지는 문제가 발생하는데, 이를 콜백 지옥이라고 함

### 예시 코드

```jsx
function step1(callback) {
  setTimeout(() => {
    console.log("Step 1 완료");
    callback();
  }, 1000);
}

function step2(callback) {
  setTimeout(() => {
    console.log("Step 2 완료");
    callback();
  }, 1000);
}

function step3(callback) {
  setTimeout(() => {
    console.log("Step 3 완료");
    callback();
  }, 1000);
}

// 콜백 중첩 발생! (콜백 지옥)
step1(() => {
  step2(() => {
    step3(() => {
      console.log("🚀 모든 작업 완료!");
    });
  });
});
```

- 코드가 계단식으로 깊어져 가독성이 떨어짐
- 디버깅이 어려움
- 유지보수가 복잡해짐

### 해결 방법

- Promise 사용
- async/await 사용

## 2. Promise

특정한 작업의 완료 또는 실패를 나타내는 객체

`then()` `catch()` `finally()` 를 사용하여 결과를 처리

프로미스 객체를 직접적으로 만들어서 사용하는 경우는 드물다

### Promise 상태

- `pending` (대기 중) : 비동기 작업이 아직 완료되지 않음
- `fullfilled` (성공) : 비동기 작업이 성공적으로 완료됨(`resolved()`)
- `reject` (실패) : 작업이 실패함(`reject()`)

```jsx
const borrow = 20;

const payWith10Perc = new Promise((resolve, reject) => {
  setTimeout(() => {
    if (Math.random() < 0.5) {
      reject("사업 망함");
    }

    resolve(borrow * 1.1);
  }, 1000);
});

payWith10Perc
  .then((result) => console.log(result + "만원"))
  // then()에서 거부 콜백 함수를 생략하면 catch()에서 처리 가능
  .catch((error) => console.log(error))
  .finally(() => console.log("기한 종료"));
```

> Promise를 사용하면 콜백 지옥을 해결할 수 있고, 가독성이 좋아짐

### `then()` - 성공한 경우 실행

- 비동기 작업이 성공(`resolved()` 상태)하면 `then()` 실행
- 여러 개의 `then()` 을 체이닝(Chaining, 메서드 연속 실행) 가능

```jsx
new Promise((resolve) => {
  setTimeout(() => resolve(1), 1000);
})
  .then((result) => {
    console.log(result); // 1
    return result * 2;
  })
  .then((result) => {
    console.log(result); // 2
    return result * 3;
  })
  .then((result) => {
    console.log(result); // 6
  });
```

> 체이닝을 사용하면 가독성이 좋아지고, 비동기 작업을 순차적으로 실행 가능

### `catch()` - 실패한 경우 실행

- 비동기 작업이 실패(`reject()` 상태)하면 `catch()` 실행
- 오류가 발생했을 때 에러를 잡아 처리하는 역할

```jsx
new Promise((resolve) => {
  setTimeout(() => resolve(1), 1000);
})
  .then((result) => {
    console.log(result); // 1
    throw new Error("🚨 에러 발생!");
  })
  .then((result) => {
    console.log(result * 2); // 실행되지 않음
  })
  .catch((error) => {
    console.error(error.message); // "🚨 에러 발생!"
  });
```

### `finally` - 성공/실패와 관계 없이 항상 실행

- `finally()` 는 Promise가 끝난 후 무조건 실행
- 리소스 정리, 로딩 UI 숨기기 등에 활용

```jsx
new Promise((_, reject) => {
  setTimeout(() => reject("❌ 데이터 로드 실패!"), 2000);
})
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.error(error); // "❌ 데이터 로드 실패!"
  })
  .finally(() => {
    console.log("🧹 모든 작업 완료, 정리 중...");
  });
```

## 3. async/await (비동기 코드 간소화)

- `async` 키워드를 함수 앞에 붙이면 자동으로 Promise를 반환
- `await` 키워드를 사용하면 비동기 작업이 완료될 때까지 기다림
- 동기 코드처럼 읽기 쉬움
- Promise의 문제점을 보완하기 위해 사용

```jsx
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("📡 데이터 가져오기 완료!");
      resolve("✅ 성공적으로 데이터 받음");
    }, 2000);
  });
}

async function getData() {
  console.log("1. 데이터 요청");
  const result = await fetchData(); // 비동기 작업이 끝날 때까지 기다림
  console.log(result);
  console.log("3. 작업 완료");
}

getData();

//1. 데이터 요청
//(2초 후) 📡 데이터 가져오기 완료!
//✅ 성공적으로 데이터 받음
//3. 작업 완료
```

# 이벤트 루프 (Event Loop)

JavaScript의 비동기 처리를 가능하게 하는 핵심 개념

- JavaScript는 싱글 스레드 언어이므로, 한 번에 하나의 작업만 실행 가능
- 하지만 이벤트 루프를 통해 비동기 작업을 처리하여 여러 작업을 동시에 실행하는 것처럼 동작할 수 있음
- 콜 스택(Call Stack)과 태스크 큐(Task Queue)를 관리하여 비동기 작업을 처리하는 역할
- node.js 실행 환경에서도 지원

## 동작 과정

### 1. 콜 스택

- 실행할 함수가 쌓이는 공간
- 동기적 코드 실행
- 비동기 코드를 만나면 태스크 큐로 들어감

### 2. 태스크 큐(`setInterval`, `setTimeout`) / 마이크로 태스크 큐(API 호출)

- 비동기 작업이 완료되면 실행 대기

### 3. 이벤트 루프

- 콜 스택이 비어 있으면 태스크 큐에서 작업을 가져와 실행

### 이벤트 루프 실행 과정 정리

```bash
[동기 코드 실행 (콜 스택)]
   ↓
[비동기 함수 호출 → Web API로 이동]
   ↓
[작업 완료 → 태스크 큐 등록]
   ↓
[콜 스택 비면 → 이벤트 루프가 태스크 큐의 콜백을 실행]
```
