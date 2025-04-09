# HTML 기본 구조

1. HTML 문서는 기본적으로 Doctype 선언으로 시작하며, 이는 해당 문서가 HTML5 문서임을 브라우저에 알려주는 역할

```html
<!DOCTYPE html>
```

2. 다음으로 `<html>` 태그로 전체 문서를 감싸고, `<head>`와 `<body>` 두 부분으로 나뉨

   - `<head>` : HTML 문서의 메타 데이터, 제목, 스타일이나 외부 리소스에 대한 정보를 포함
     > 메타 데이타 : 데이터를 설명하는 데이터

   ```html
   <head>
     <meta charset="UTF-8" />
     <meta name="viewport" content="width=device-width, initial-scale=1.0" />
     <meta name="description" content="문서에 대한 간단한 설명" />
     <meta name="keywords" content="키워드1, 키워드2, 키워드3" />
     <meta name="author" content="작성자 이름" />

     <title>문서 제목</title>

     <style>
       h1 {
         background-color: #f0f0f0;
       }
       p {
         color: green;
       }
     </style>
     <link rel="stylesheet" href="styles.css" />
     <script src="script.js"></script>
   </head>
   ```

   <br/>

   - `<body>` : HTML 문서의 실제 내용을 담고 있는 부분으로 텍스트, 이미지, 버튼 등 실제 웹 브라우저에 보여질 콘텐츠가 포함

   ```html
   <body>
     <h1>본문 제목</h1>
     <p>본문의 첫 번째 단락입니다.</p>
     <p>본문의 두 번째 단락입니다.</p>

     <img src="/_assets/images/example.jpg" alt="예시 이미지" />
   </body>
   ```

<br/>

> 이런 기본 구조를 바탕으로 HTML 페이지가 구성되고, 이를 통해 웹 브라우저가 콘텐츠를 올바르게 렌더링할 수 있게 된다.

<br/>
<br/>

### 면접 답변

<aside>

### ✅ HTML의 기본 구조는 어떻게 되나요?

HTML 문서는 기본적으로 Doctype 선언으로 시작하며, 이는 해당 문서가 HTML5 문서임을 브라우저에 알려주는 역할을 합니다.

다음으로는 `<html>` 태그로 전체 문서를 감싸고, 문서 구조는 크게 `<head>` 와 `<body>` 두 부분으로 나뉘게 됩니다.

`<head>` 영역에는 문서의 메타데이터, 제목, 스타일 시트, 외부 리소스 링크, 그리고 스크립트 등 브라우저가 콘텐츠를 렌더링하기 전에 참고해야 할 정보들이 포함됩니다.

`<body>` 영역에는 실제 사용자에게 보여지는 콘텐츠들이 포함되는 부분으로, 텍스트, 이미지, 버튼 등 다양한 시각적 요소들이 포함됩니다.

</aside>

<br/>

### 꼬리 질문 답변

<aside>

### Doctpye이란?

Doctype은 HTML 문서가 어떤 표준을 따르는지 브라우저에 알려주는 선언문으로, 정확한 렌더링과 웹 표준 준수를 위해 꼭 필요합니다.

</aside>
