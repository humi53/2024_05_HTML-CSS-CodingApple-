# transform & animation 으로 매끄러운 애니메이션 만들기

### 브라우저가 그림그리는 순서

1. Rnder Tree
2. Layout

- 박스만들기
- width, height, margin, padding 등

3. Paint

- 색칠하기
- color 등

4. Composite

- transform, opacity 처리

- transform 같은건 다른 쓰레드에서 처리해줌
- 웹브라우저는 쓰레드1개
- 애니매이션 처리 속성은 다른 쓰레드에서 처리.

### transform 관련 CSS 속성들

```css
.box {
  transform: rotate(10deg);
  transform: translate(10px, 20px);
  transform: scale(2);
  transform: skew(30deg);

  /*transform 두개 이상을 한꺼번에 쓰려면*/
  transform: rotate(10deg) translateX(30px);
}
```

- transform 은 어떤 요소를 독립적으로 움직이게 만들고 싶을 때 사용합니다.

본인 원래 위치에서 자유롭게 (다른 요소에 영향 없이) 이동하게 됩니다.

rotate는 회전, translate는 좌표이동, scale은 확대축소, skew는 비틀기 입니다.

특히 애니메이션을 동작시킬 때 transform 속성을 쓰면 효과적인데 이유는 강의에서 설명합니다.

### 복잡한 애니메이션 구현법

- 예전 간단한 a -> b 애니메이션들은

시작스타일, 최종스타일, 트리거, transition 주면 된다고 했습니다.

근데 a -> b -> a, a -> 1초정지 -> b 같은 복잡한건 못합니다.

@keyframes를 쓰면 가능합니다.

1. 가장 먼저 @keyframes 를 정의합니다.

```css
@keyframes 움찔움찔 {
  0% {
    transform: translateX(0px); /* 애니메이션이 0%만큼 동작시 */
  }
  50% {
    transform: translateX(-20px); /* 애니메이션이 50%만큼 동작시 */
  }
  100% {
    transform: translateX(20px); /* 애니메이션이 100%만큼 동작시 */
  }
}
```

@keyframes는 커스텀 애니메이션을 정의하기 위한 공간이라고 생각하시면 됩니다.

'움찔움찔'이라는 애니메이션을

0% 진행했을 때의 CSS,

50% 진행했을 때의 CSS,

100% 진행했을 때의 CSS를 각각 작성합니다.

(% 수치는 맘대로 변경, 추가 가능합니다)

2. keyframes를 원하는 곳에 첨부합니다.

```css
.box:hover {
  animation-name: 움찔움찔;
  animation-duration: 1s;
}
```

animation 속성을 이용하시면 애니메이션을 동작시킬 수 있습니다 .

꼭 필요한 속성은 name과 duration이고

애니메이션 이름을 name에

애니메이션 동작시간을 duration에 넣으면 됩니다.

그럼 진짜 마우스 올렸을 때 움찔움찔 애니메이션이 동작합니다.

3. 애니메이션 세부조정하기

```css
.box:hover {
  animation-name: 움찔움찔;
  animation-duration: 1s;
  animation-timing-function: linear; /*베지어 주기*/
  animation-delay: 1s; /*시작 전 딜레이*/
  animation-iteration-count: 3; /*몇회 반복할것인가*/
  animation-play-state: paused; /*애니메이션을 멈추고 싶은 경우 자바스크립트로 이거 조정*/
  animation-fill-mode: forwards; /*애니메이션 끝난 후에 원상복구 하지말고 정지*/
}
```

위의 속성을 쓰시면 애니메이션 동작시 세부사항을 더 자세하게 조정하실 수 있습니다.

이제 위에 있는 숙제를 하러가도록 합시다.

### 성능 잡을 수 있는 여러 방법1. will-change 쓰면 됩니다.

```css
.box {
  will-change: transform;
}
```

애니메이션을 주는 .box가 약간 느리게 동작한다면

will-change : 애니메이션줄속성;

이걸 써놓으면 성능개선이 가능합니다. 바뀔 내용을 미리 렌더링해주는 속성이라 그렇습니다.

뭔가 이상하게 버벅일 때만 쓰시고 애니메이션이 스무스하게 잘 된다면 쓸 이유는 없습니다.

이상하게 많이 쓰면 브라우저 자체가 더 느려질 수 있습니다.

https://dev.opera.com/articles/ko/css-will-change-property/

### 성능 잡을 수 있는 여러 방법2. 하드웨어 가속

애니메이션이 너무 많아 CPU만으로 전부 연산이 불가능하다면

GPU의 도움을 받을 수도 있습니다.

```css
.box {
  transform: translate3d(0, 0, 0);
}
```

transform : translate3d를 쓰면 3D 이동도 가능한데

이 속성의 경우 GPU를 사용해서 연산하게 됩니다.

그래서 translate3d(0, 0, 0) 이런 식으로 아무데도 움직이지 않는 3D 이동명령을 주고

뒤에 필요한 transform을 더 적용한다면

GPU를 이용해서 .box가 가진 transform 속성들을 연산할 수 있습니다.

꼭 써야하는건 아니고 뭔가 느리게 동작한다면 써볼 수 있는 것들입니다.
