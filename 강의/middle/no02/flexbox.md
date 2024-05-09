# 레이아웃 만들기 3 : 편리한 Flexbox

### Flexbox 세부속성

```css
.flex-container {
  display: flex;
  justify-content: center; /* 좌우정렬 */
  align-items: center; /* 상하정렬 */
  flex-direction: column; /* 세로정렬 */
  flex-wrap: wrap; /* 폭이 넘치는 요소 wrap 처리 */
}
.box {
  flex-grow: 2; /* 폭이 상대적으로 몇배인지 결정 */
}
```
