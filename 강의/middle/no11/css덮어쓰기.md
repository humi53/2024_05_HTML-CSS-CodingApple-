# CSS 덮어쓰기 잘하는 법 & 어떤 코드가 좋은 코드인가요

### 클래스명 중복

- 밑에있는것을 최종적으로 적용함
- @media 문법도 하단에 작성해야 하는 이유도 이것임.

### 안되는 경우.

- class, id, style직접. 우선순위를 높여도 됨.
- `!important` 10000점짜리 우선순위
- 점수를 높이는 방식은 근본적인 해결책이 아님.
- 10000점이 끝임.

### specificity 점수 높이기

- 20점 짜리

```css
.main-background .custom {
  color: green;
}
```

- 21점 짜리

```css
div.main-background .custom {
  color: green;
}

.custom {
  color: red;
}
```

- 하지만 셀렉터가 길게 적으면 미래에 덮어쓰기 힘들어짐.
- 스타일링은 1개의 키워드로 하는게 좋은 습관이 되겠음.

### 좋은코드

- 나중에 수정/관리가 쉬우면 항상 좋은 코드임.
- 확장성이 좋으면 좋은 코드임. (재활용, 확장해서 다른 class를 만들기 쉬운지.)

### 부트스트랩 덮어쓰기는?

- class 추가하는게 흔하고 덮어쓰기는 잘 안함.
