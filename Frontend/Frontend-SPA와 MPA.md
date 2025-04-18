# SPA (Single Page Application)

페이지 전체를 새로고침하지 않고, 하나의 HTML 페이지 내에서 동적으로 콘텐츠를 변경하는 방식의 웹 애플리케이션으로 클라이언트 측 라우팅(Client-Side Routing)을 통해 화면 전환

### 동작 방식

1. 초기 로딩 시 : HTML, CSS, JS 파일을 모두 받아옴
2. 이후 사용자의 요청(페이지 전환)은 JavaScript가 처리해서 필요한 데이터만 요청하고 DOM을 동적으로 갱신 (디핑(Diffing) 알고리즘을 사용해서 바뀐 부분만 찾아서 동적으로 갱신)
3. 주소(URL)는 바뀌지만, 실제로는 페이지 리로드 X (페이지 전체를 다시 렌더링하지 않고, 현재 페이지 구조를 유지한 채 필요한 내용만 변경)

### 장점

- 빠른 화면 전환 : 페이지 전체를 새로 불러오지 않아서 빠름
- 모바일 앱과 유사한 UX : 앱처럼 부드러운 전환이 가능
- API 중심 개발에 적합 : 백엔드와 REST API 또는 GraphQL로 분리 가능
- 캐싱 효율 증가 : 한 번 받은 자원은 재사용 가능

### 단점

- 초기 로딩 느림 : 한 번에 리소스를 많이 불러옴
- SEO 취약 : 크롤러가 JS 실행을 못하면 내용 파악 어려움 → SSR 도입으로 개선 가능
- 브라우저 히스토리/스크롤 복원 등 관리 필요

### 대표 사례

- Gmail, Facebook 등
- 대부분의 React, Vue, Angular 기반 웹앱

<br/>

# MPA (Multi Page Application)

페이지마다 개별 HTML 파일을 요청해서 페이지를 전환하는 구조로, 브라우저가 새로운 페이지로 이동할 때마다 서버에서 HTML을 새로 받아옴

### 동작 방식

1. 사용자가 링크를 클릭하면 서버에 요청을 보내고, 서버는 새로운 HTML 문서를 반환
2. 전체 페이지가 다시 로드되며 렌더링
3. 서버 중심 라우팅(Server-Side Routing)이 기본

### 장점

- SEO 최적화 용이 : HTML 컨텐츠가 서버에서 렌더링되어 검색 엔진이 쉽게 읽음
- 초기 진입 속도 빠름 : 필요한 리소스만 로드
- 보안성, 접근성 증가 : 전통적인 방식이기 때문에 안정적

### 단점

- 페이지 이동 시 깜빡임(Flicker) 발생
- 공통 리소스 반복 로딩(헤더, 푸터 등)
- 사용자 경험(UX)이 SPA보다 다소 끊긴 느낌

### 대표 사례

- 대부분 전통적인 웹사이트
- 네이버, 다음 쇼핑몰, 은행 웹 사이트 등
- 서버에서 템플릿 기반으로 렌더링하는 JSP, PHP, Django 같은 프로젝트

<br/>

### 면접 질문

<aside>

### ✅ SPA와 MPA에 대해 설명해보세요.

SPA는 Single Page Application으로 하나의 HTML 페이지에서 동작하는 웨비 앱입니다. 사용자가 페이지를 이동해도 실제로는 페이지 전체가 리로딩되지 않고, 자바스크립트가 필요한 데이터만 받아와서 화면을 동적으로 바꿔주는 방식입니다. 이런 구조 덕분에 화면 전환이 빠르고 UX가 부드럽다는 장점이 있지만, 초기 로딩이 느리고 SEO 대응이 별도로 필요합니다. 주로 React나 Vue 같은 프론트엔드 프레임워크를 사용할 때 사용됩니다.

MPA는 Multi Page Application으로 페이지를 이동할 때마다 서버로부터 새로운 HTML 파일을 받아오는 구조입니다. 그래서 매 페이지 이동 시 전체 페이지가 리로딩됩니다. SEO에 유리하고 초기 진입 속도는 빠르지만, 매 페이지마다 새로 요청이 가기 때문에 UX는 조금 떨어질 수 있습니다. 대표적으로 네이버나 다음 같은 일반적인 웹 사이트에서 많이 사용됩니다.

</aside>

### ⭐ 실제 면접 질문

<aside>

### ✅ SPA를 실행하려면 어떻게 해야 하나요?

SPA는 하나의 HTML 파일에서 시작해 JavaScript로 화면을 전환하는 방식이라서, 기본적으로는 페이지를 이동해도 실제로는 새로고침 없이 동작합니다. 하지만 이 구조만으로는 문제 사항이 발생할 수 있습니다.

예를 들어, 사용자가 특정 URL을 직접 입력해서 원하는 화면으로 접근할 수 없고, 브라우저의 앞/뒤로 가기 버튼도 제대로 작동하지 않는다는 점입니다.

이러 문제를 해결하기 위해 클라이언트 사이드 라우팅이 필요합니다. 라우팅 기법을 통해 URL 경로에 따라 어떤 컴포넌트를 보여줄지 매핑하고, 실제 페이지 이동 없이도 화면을 바꿔줄 수 있습니다.

</aside>
