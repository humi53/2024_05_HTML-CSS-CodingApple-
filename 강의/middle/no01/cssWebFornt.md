# HTML CSS 웹폰트 넣는 법과 안티앨리어싱

- woff : 웹용 폰트 용량이 막 작아짐.

#### 옛 IE 호환

```css
@font-face {
  font-family: "NanumSquare";
  font-weight: 400;
  src: url(NanumSquareR.eot);
  src: url(NanumSquareR.eot?#iefix) format("embedded-opentype"), url(NanumSquareR.woff)
      format("woff"), url(NanumSquareR.ttf) format("truetype");
}
```

## 웹폰트

웹폰트용 woff파일

웹폰트용으로 나온 woff 파일이 있습니다. ttf에 비해 용량이 3분의1 수준입니다.

한글폰트 ttf 파일은 용량이 매우 크기 때문에 (한글폰트는 특히 몇천자가 들어있기 때문에)

구할 수 있다면 woff 파일을 사용하시는걸 추천드립니다. ttf와 호환성은 거의 비슷한 수준입니다.

어짜피 ttf나 woff 둘다 IE8 이하에선 적용되지 않습니다. 자유롭게 woff를 사용하도록 합니다.

나눔스퀘어 woff 버전 : `https://github.com/moonspam/NanumSquare`

## 구글폰트

폰트를 빠르게 사용하기 위한 Google Fonts

구글폰트라는 사이트를 이용하면 굳이 폰트파일을 구하지 않아도 됩니다.

Google Fonts 사이트에서 바로 폰트파일과 CSS 정의부분을 링크할 수 있으니까요.

fonts.google.com

저 사이트에서 원하는 폰트를 고르신 다음

HTML에 첨부하고 싶다면 <link>로 시작되는 부분을 복붙하시면 되고,

## 폰트 Anti-aliasing 에 대해

조금 더 부드럽게 하려면
웹상의 글자를 살짝 돌려보십시오.

```css
transform: rotate(0.04deg);
```
