# 약간 쓸데없는 Pseudo-element

- `pseudo-class` (다른상태일 때)
- `::pseudo-element` (내부의 일부분만 스타일줄 때) : 콜론 하나도 적용하지만 구분하기위해 두개 쓴다.
- `after`, `before`

```css
.text::after {
  content: "안녕";
  color: red;
}
```

- `<div style="float: none; clear: both"></div>`

```css
.box::after {
  content: "";
  display: block;
  clear: both;
}
```
