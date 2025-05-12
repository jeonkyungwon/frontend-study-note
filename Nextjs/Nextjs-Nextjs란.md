# Next.js

React의 기능을 확정한 프레임워크로 페이지 기반 라우팅, API 라우트, SSR 등의 기능을 내장하고 있어 별도 설정 없이도 복잡한 웹 애플리케이션을 쉽게 구축 가능

Vercel에서 개발 및 유지보수를 하고 있으며, 기본적으로 React를 더 프로덕션 친화적으로 만들어주는 역할을 함

## 주요 특징

### 1. 파일 기반 라우팅 (File-based Routing)

- `pages/` 폴더 내부에 있는 파일 이름이 곧 URL 경로

```bash
pages/about.js → /about
pages/blog/[id].js → /blog/:id  (동적 라우팅 지원)
```

### 2. SSR (서버 사이드 렌더링)

- `getServerSideProps` 를 통해 매 요청 시 서버에서 HTML을 생성
- 최신 데이터 반영이 필요할 때 적합
- SEO에 유리하며, 데이터 의존도가 높은 페이지에서 유용
- 사용 예 : 로그인 사용자 전용 대시보드, 실시간 정보 페이지 등

### 3. CSR (클라이언트 사이드 렌더링)

- React의 기본 방식으로, `useEffect` 를 통해 클라이언트에서 데이터 요청
- 서버는 최소한의 HTML만 전달하고, 나머지는 브라우저에서 렌더링
- 초기 로딩은 느릴 수 있지만, 사용자와의 상호작용이 많은 페이지에서 유리
- 사용 예 : 검색 결과 필터링, 무한 스크롤 페이지, 대시보드 등

### 4. SSG (정적 사이트 생성)

- `getStaticProps` 를 통해 빌드 시 HTML을 미리 생성
- 요청마다 렌더링하지 않고, 정적 HTML을 즉시 응답
- 최고의 속도와 트래픽 처리 능력 제공
- 사용 예 : 블로그, 문서 페이지, 마케팅 랜딩 페이지

### 5. ISR (증분 정적 재생성)

- `getStaticProps` + `revalidate` 옵션 사용
- 빌드 후에도 정적 페이지를 주기적으로 재생성
- SSG의 성능 + 최신성 확보
- 사용 예 : 제품 상세 페이지, 뉴스 기사 목록 등

### 6. API Routes

- 백엔드 없이도 `pages/api/` 디렉토리 내에서 API를 만들 수 있음
- 예 : `pages/api/hello.js` → `api/hello` 에서 실행

### 7. 이미지 최적화 (next/image)

- 브라우저 크기에 따라 자동 리사이징 및 Lazy Loading
- WebP 등의 포맷 지원으로 성능 향상

### 8. Built-in CSS 지원

- CSS, Sass, CSS-in JS 등 다양한 스타일 방식 지원
- APP Router를 사용할 경우 Tailwind CSS, shadcn/ui와 잘 통합

### 9. 최신 기능 (App Router)

Next.js 13+ 버전부터는 App Router라는 새로운 구조 도입

- `app/` 디렉토리 중심의 구조
- 서버 컴포넌트(Server Components) 지원
- Layouts, templates, loading, error 파일 기반 관리
- `use client` 디렉티브를 통해 클라이언트 컴포넌트 명시

<br/>

### 면접 답변

<aside>

### ✅ Next.js란?

Next.js는 React 기반의 프레임워크로, SSR(서버 사이드 렌더링), SSG(정적 사이트 생성), CSR(클라이언트 사이드 렌더링) 등 다양한 렌더링 방식을 유연하게 지원하는 것이 가장 큰 특징입니다.

페이지 기반의 라우팅 시스템을 제공하고, 폴더 구조만으로도 라우팅이 가능해서 개발 생산성이 높습니다. 또한 API 라우트 기능을 통해 간단한 백엔드 기능까지 구현할 수 있습니다.

그리고 이미지 최적화, 코드 분할, 자동 정적 최적화 같은 퍼포먼스 관련 기능도 기본 제공되어, 성능에 민감한 웹 애플리케이션을 만들 때 유리합니다.

</aside>
