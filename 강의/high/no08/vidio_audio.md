# HTML video, audio 다루기

### 속성

```html
<video autoplay muted loop poster="썸네일경로" preload="metadata">
  <source src="비디오파일경로" />
</video>
```

- muted는 음소거상태

- autoplay는 자동재생 (muted와 함께 넣어야 동작함)

- poster는 썸네일이미지

- preload는 영상을 먼저 다운을 받을지 말지를 선택가능합니다 (auto, metadata, none 사용가능)

### 비디오를 '배경'으로 쓰고싶다면

- 유행은 지났지만 어떻게 하는지 알아봅시다.

- 일반적인 Youtube 비디오 넣는 방법처럼 `<iframe>` 코드 복붙 이런게 아니라

- 비디오 파일을 직접 다운받아서 같은 폴더에 준비하고

- 다음처럼 레이아웃 짜면 됩니다.

```html
<div class="video-box">
  <video class="video-container" autoplay muted loop>
    <source src="img/bridge.mp4" type="video/mp4" />
  </video>
  <h3 class="video-title">Buy Our Shoes!</h3>
</div>
```

```css
.video-box {
  height: 500px;
  width: 100%;
  overflow: hidden;
  position: relative;
}

.video-container {
  position: absolute;
  width: 100%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: -1;
}
```

- 어떤 요소를 궁극의 가운데정렬을 하고 싶을 때

저렇게 position absolute를 주고 top, left, transform 속성을 차례로 줍니다.

그럼 position relative를 가진 부모에 대해 정가운데 위치시킬 수 있습니다.

max-width, width 등으로 크기 조정을 넣는 것도 좋습니다.

여기까지만 하면 비디오가 배경처럼 크게 보이며

그리고 원하는 html을 <video> 하단에 적는 식으로 비디오 위에 글쓰고 그럴 수 있습니다.
