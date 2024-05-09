# seudo-class로 인터랙티브 버튼 만들기

- 순서중요함

```css
.btn {
  background-color: #133761;
  color: white;
  float: right;
  padding: 20px;
  border: none;
  border-radius: 5px;

  cursor: pointer;
}

.btn:hover {
  background-color: chocolate;
}
.btn:focus {
  background-color: grey;
  border: 2px solid white;
}
.btn:active {
  background-color: brown;
}
.input-test {
  font-size: 20px;
}
.input-test:focus {
  border: 10px solid red;
}
.custom-link {
  text-decoration: none;
}
.custom-link:link {
  color: aqua;
}
.custom-link:visited {
  color: black;
}
```
