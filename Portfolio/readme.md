# 잘안되는...

- BootStrap을 쓰면서 미세하게 설정하기 힘듬.
- 차라리 BootStrap을 안쓴 버전과 BootStrap위주로 쓰는 버전을 따로 만드는게 좋지 않을까?

- 모르겠고 아무튼 해결해서 완성함.

### 특이사항

- row는 `-margin`이 들어있다.
- col은 자체 `padding`이 들어있다.
- chatgpt대화로 내린 결론은 구조상 이게 좋지 않을까
  - container > 사용자contanier > row > col > 보여줄box
- 위 구조가 아닐땐
  - margin과 padding을 잘 조절하자.
- 핵심은 : 일관성 있는 재활용성 있는 한부분만 파악하면 다른부분도 똑같이 적용되는 모델을 적용해야 된다 생각함.

### 6. 기타 Bootstrap 레이아웃 구축 팁

- 많은 부트스트랩 요소들은 사이즈가 em 으로 선언되어있습니다.

그래서 부모 div박스에 font-size : 00px 이렇게 주면 한번에 많은 사이즈들을 축소나 확대하실 수 있습니다.

media object 부모 div박스에 font-size 아무렇게나 한번 줘보십시오.

안에있는 글자들이 각각 알맞은 비율로 줄어듭니다.

- <hr> 이라는 태그는 가로 선을 생성해줍니다.

<div class="vr"></div> 이렇게 쓰면 세로선을 생성해줍니다. height 설정 가능합니다.

- Bootstrap 홈페이지에 있는 Icons 메뉴를 활용하면

<svg> 이런 식으로 정의된 아이콘을 복사 붙여넣기할 수 있는데

Font Awesome 이런 것 전부 첨부하는 것 보다 용량을 훨씬 줄일 수 있습니다.
