# 레이아웃 만들기 4 : CSS Grid 레이아웃

### 간단한 Grid 레이아웃 만들기

```html
<div class="grid-container">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: 100px 100px 100px;
  grid-gap: 10px;
}
```

### Grid로 레이아웃 만드는 법 1. 자식 div 높이와 폭을 조정하기

```html
<div class="grid-container">
  <div class="grid-nav">헤더</div>
  <div class="grid-sidebar">사이드바</div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
.grid-nav {
  grid-column: 1 / 4;
  grid-row: 2 / 4;
}
```

### Grid로 레이아웃 만드는 법 2. 자식에게 이름쓰고 부모가 배치하기

```html
<div class="grid-container">
  <div class="grid-nav">헤더</div>
  <div class="grid-sidebar">사이드바</div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
.grid-nav {
  grid-area: 헤더;
}

.grid-sidebar {
  grid-area: 사이드;
}

.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: 100px 100px 100px;
  grid-gap: 10px;
  grid-template-areas:
    "헤더 헤더 헤더 헤더"
    "사이드 사이드 . ."
    "사이드 사이드 . .";
}
```
