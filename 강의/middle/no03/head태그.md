# head 태그에 들어갈 내용 정리

```html
<!DOCTYPE html>
<head>
  어쩌구
</head>
<body>
  저쩌구
</body>
```

1. 각종 CSS 파일들

```html
<head>
  <link href="css/main.css" rel="stylesheet" />
</head>
```

2. 스타일 태그

```html
<head>
  <style>
    .button {
      color: red;
    }
  </style>
</head>
```

3. 사이트 제목

```html
<head>
  <title>네이버입니다</title>
</head>
```

4. 여러가지 meta 태그

```html
<head>
  <meta charset="UTF-8" />
  <meta name="description" content="html 잘하는 코딩애플입니다." />
  <meta name="keywords" content="HTML,CSS,JavaScript,자바스크립트,코딩" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
```

- 인코딩, 구글검색시 제목과, 검색 키워드
- 사이트 초기 zoom 레벨이나 폭을 지정해주려면 name="viewport" 라는 속성을 부여하시면 됩니다.

width=device-width는 모바일 기기의 실제 폭으로 렌더링 해주세요 라는 뜻입니다.

요즘 스마트폰 가로 해상도가 1920px을 넘어가는 폰들이 많죠.

그럼 이것만 보고 1920px 에 해당하는 페이지를 띄워줄 수는 없겠죠?

그래서 실제 접속시 스마트폰 기기의 실제 가로폭을 보고 렌더링하라고 명령하는 부분이라고 보시면 됩니다.

initial-scale=1 이 부분은 접속시의 화면 줌레벨 설정입니다.

그래서 반응형 웹을 만들 때 저 meta 태그를 복붙하시고 시작하시면 되겠습니다.

5. open graph

```html
<head>
  <meta property="og:image" content="/이미지경로.jpg" />
  <meta property="og:description" content="사이트설명" />
  <meta property="og:title" content="사이트제목" />
</head>
```

6. Favicon

```html
<head>
  <link rel="icon" href="아이콘경로.ico" type="image/x-icon" />
</head>
```

- 32x32 사이즈로 제작하면됨.
- 웹사이트를 바탕화면에 바로가기 추가할 때 뜨는 아이콘 커스터 마이징. 가능
  `rel="apple-touch-icon-precomposed" `
- os마다 요구하는 rel 속성이 달라서 찾아써야됨. favicon generator 검색하면 알아서 해결해줌.
