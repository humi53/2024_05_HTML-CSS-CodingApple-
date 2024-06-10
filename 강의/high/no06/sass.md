# 쉽게 배우는 Sass 3편 : Mixin, use 등

### `@mixin` 문법

- 앞을 변수로

```scss
@mixin font-style($size, $구멍2) {
  font-size: $size;
  #{$구멍2}: -1px;
}
h2 {
  @include font-style(40px, letter-spacing);
}
h2 {
  @include font-style(40px, width);
}
```

- 저장 안하려면
  - `_파일명`
