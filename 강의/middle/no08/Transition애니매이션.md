# Transition 속성으로 CSS 애니메이션 구현하기

1. 시작스타일 정하기

2. 최종스타일 정하기

3. 언제 최종스타일로 변할지 트리거 주기 (대부분 마우스 올렸을 때임)

4. transition 으로 서서히 동작하게 만들기

```css
.box {
  transition-delay: 1s; /* 시작 전 딜레이 */
  transition-duration: 0.5s; /* transition 작동 속도 */
  transition-property: opacity; /* 어떤 속성에 transition 입힐건지 */
  transition-timing-function: ease-in; /* 동작 속도 그래프조정 */
}
```

- 개발자 도구 : ... Animations 탭 누르고 동작. 분석.

- 숙제는 더큰 투명한 div 안에 동작할 div를 넣어서 접근하는 방식으로 처리
