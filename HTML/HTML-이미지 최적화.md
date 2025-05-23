# 이미지 최적화

**이미지 최적화**란 웹 페이지 성능 개선을 위해 이미지 파일의 크기와 품질을 최적화 하는 과정이다.

- 웹 페이지 로딩 속도 개선
- 사용자 경험(UX) 향상
- SEO 성능 향상

**모바일 최적화를 하지 않았을 때**

- 페이지 속도 저하로 인한 이탈률 증가
- 검색 엔진 노출 감소
- 불필요한 트래픽 낭비

### 이미지 최적화 주요 기법

1. 이미지 포맷 선택

- 기존 포맷 : JPG, PNG, GIF
- 차세대 포맷 : WebP(더 작은 크기와 우수한 품질), AVIF(WebP 보다 더 높은 압축 효율)

```jsx
if ('avif'를 지원하면) {
  // 'avif' 이미지 포맷 파일 출력
} else if ('webp'를 지원하면) {
  // 'webp' 이미지 포맷 파일 출력
} else {
  // 'jpg' 이미지 포맷 파일 출력
}
```

2. 이미지 크기 조정(Resizing) / 이미지 압축(Compression)
   이미지 크기 조정 : 사용자 화면에 맞는 적절한 크기의 이미지 제공

- 데스크톱, 테블릿, 모바일 해상도에 맞춘 반응형 이미지 사용
- CSS Media Query아 `srcset` 속성 활용

```jsx
<img
  src="example-small.jpg"
  srcset="example-small.jpg 480w, example-large.jpg 1024w"
  sizes="(max-width: 600px) 480px, 1024px"
  alt="Sample Image">
```

이미지 압축 : 이미지의 품질은 유지하면서 파일 크기를 줄이는 기술

- 손실 압축 : 불필요한 데이터 일부를 제거하여 파일 크기를 크게 줄이는 방식
  - 장점 : 파일 크기 감속 폭이 큼
  - 단점 : 압축률이 높을 수록 이미지 품질이 저하될 수 있음
  - JPG, WebP에 적합
- 무손실 압축 : 이미지 데이터를 모두 유지하면서 효율적으로 압축하는 방식
  - 장점 : 이미지 품질 100% 유지
  - 단점 : 압축률이 낮아 파일 크기 감소 폭이 적음
  - PNG, GIF, WebP에 적합

3. Lazy loading(지연 로딩)
   이미지를 사용자 스크롤 위치에 따라 지연 로딩하여 초기 페이지 로딩 속도 개선

```jsx
<img
  loading="lazy" // 로딩 지연
  decoding="async" // 디코딩 지연
  alt="sample"
/>
```

- decoding : 이미지 외의 다른 콘텐츠가 웹 페이지에 빠르게 표시되는 것을 도와줌

4. 캐싱 및 CDN 사용

- 브라우저 캐싱 : 사용자가 이미 방문한 사이트의 이미지를 캐싱하여 재방문 시 로딩 속도 개선
- CDN 사용 : 전 세계에 분산된 서버에서 이미지를 빠르게 제공

### 요약

- 이미지 최적화는 속도 UX, SEO 개선에 필수적
- 작은 노력으로 큰 성능 향상 가능

<br/>
<br/>

### 면접 답변

<aside>

## ✅ 이미지 최적화에 대해서 설명하세요.

이미지 최적화는 웹 페이지의 성능과 사용자 경험에 직접적인 영향을 주는 중요한 작업입니다. 대표적인 방법으로 포맷 선택, 용량 압축, 사이즈 조정, 지연 로딩 등이 있습니다.

</aside>
