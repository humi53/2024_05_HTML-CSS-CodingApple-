# 쉽게 배우는 Sass 2편 : 핵심문법

- sass : 들여쓰기

### nesting 문법

- 관련있는 class 들을 묶을때 좋음

```scss
.main-bg {
  h4 {
    font-size: 16px;
  }
  button {
    color: red;
  }
}
```

### extend 문법

- 임시클래스
- % 임시클래스는 단독으로 컴파일이 안됨

```scss
%btn {
  width: 100px;
  height: 100px;
  padding: 20px;
}

.btn-green {
  @extend %btn;
  color: green;
}
```
