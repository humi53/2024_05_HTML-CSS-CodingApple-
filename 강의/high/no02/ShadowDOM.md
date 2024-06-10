# 딥다크한 어둠의 공간 Shadow DOM

- Show user agent shadow DOM

- `-webkit-` : 크롬 , 사파리, edge
- `-ms-` : Explorer
- `-moz-` : Firefox

- label을 만들고 input을 숨기기는 방식으로 많이 씀.

```css
input[type="range"] {
  appearance: none;
}
input[type="range"]::-webkit-slider-thumb {
  appearance: none;
  background-color: red;
  width: 50px;
  height: 50px;
}
```

- 그냥 구글 검색으로 스타일 넣는게 쉬움.

- `<hello></hello>` 라는 태그에 shadowDOM을 심어서 사용할 수 있으나 귀찬게 이렇게 쓸일은 없음.
