|   date   |   title   |    skill     |
| :------: | :-------: | :----------: |
| 21.09.02 | HTML 수업 | HTML, CSS,JS |

---

# TIL

1. HTML-markup
2. CSS
3. JS
4. DESIGN

---

# 0902

## assignment

- opencast 과제 개선 -3번

개선점

1. opencast의 padding을 top과 border로 넣어줍니다.

   → 기본 구성에 대한 흐름에 더 잘 맞추기 위해서 / opencast는 여기에선 그저 container 역할을 한다.

2. line 제거 하고 after 속성으로 line 추가해줍니다.

   → 의미가 없는 꾸며주기 요소는 가능하면 markup 부분에서 추가적으로 만들지 않는 편이 좋다.

3. after로 추가된 가상요소들은 position absolute를 이용해서 position층을 이용해서 배치해주면 다루기 쉽다.
4. category after 요소 정리 float제거 및 position 사용

---

- naver header 과제 - 4번

  [https://github.com/wuixwui/temp](https://github.com/wuixwui/temp)

  [https://wuixwui.github.io/temp/](https://wuixwui.github.io/temp/)

- 작업하면서 어려웠던 부분

  aside css가 너무길어지게 된 부분..😥

  ![resp.gif](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bf1fed7b-ff73-4b9f-9358-f37b5d64df13/resp.gif)

  aside toggle 버튼 구현에서 자연스럽게 올라가고 내려가게 하려면 overflow: hidden을 주어야 했습니다.

  → aside에 주게 되면 버튼까지 보이지 않게됨.

  → 그렇게 되면 공지사항과 more 버튼이 보이지 않게 됨.

  - 이를 해결하기 위해서 content-defalt(inner)에만 relative를 주어 공지사항과 more를 side와 다른 선상에 놓이게 처리함.
  - 높이 조절을 내용과 전체 높이 두가지를 조절하게 스크립트를 구성

    (내용이 스르르 올라가면서 메인도 따라 붙을 수 있도록)

  → 공지 사항과 more을 content-defalt(inner)에 걸리게 하기 위해서 중간 위치상 부모에 걸리지 않게 하기 위해서 포지션 속성을 content-defalt(inner)를 제외하고 그 하위요소들에는 position 속성을 제한함.

  - float로 모든 것을 처리해야되다보니 코드가 지저분해지는 느낌...

  → script에서 display : none으로 사용하면 뚝뚝 사라지고 없어지다보니 부자연스러워짐

  - transition과 opacity, pointEvent를 사용

  ### 질문

  위쪽으로 올라가는 부분(공지사항과 more)을 어떤 식으로 처리하는 게 깔끔한 코드를 사용할 수 있을까요?

  처음 생각했던건 단순히 overflow-hidden을 이용해서 높이를 조절하는 것이었는데 inner 밖으로 배치된 요소들로 인해서 불필요한 요소가 많아지게 된 것 같아요..😥

  - 정리할 수 있는데 까지 정리해보기..(자고나서..)

---

### 질문

- flex와 float의 혼용

- 초보자(?)의 단계와 단계

---

## HTML

[https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FQzdiOfp8QbWQhaUVQiRe2e%2Fnaver-page](https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FQzdiOfp8QbWQhaUVQiRe2e%2Fnaver-page)

페이지 마다 다른 부분이 있다면 화면 고유 이름을 지어준다.

- 페이지에서도 공통 속성 부분과 그렇지 않고 특수한 부분들을 나눠서 정리해두면 수정에 용이하다.

### 메뉴 구조도

### UL, OL

순서가 있는 내용에는 단순하게 span p div를 사용하는 것이 아니라 의미를 파악하고 ul혹은 ol등의 list태그를 사용한다.

## CSS

### 로고 이미지의 사용

의미가 적은 로고의 디자인일 경우 img태그보다 background를 사용하는 편이 좋다.

(디자인으로 사용되면 굳이 alt와 같은 설명이 필요없기 때문에..?)

### 브라우저 호환성

CSS는 브라우저 호환성이 브라우저마다 다르기 때문에 브라우저 호환성을 생각하면서 작업을 해줘야한다.

### flex, float, inline

상황에 맞는 속성을 사용할 수 있어야 한다.

- inline으로 사용할 수 있는 속성은 inline으로

### line-height

단위에 %를 사용하면 계산이 되어서 온다.

### border로 삼각형 만들기

border-top: 10px solid red;

border-left: 10px solid blue;

border-bottom: 10px solid lime;

border-right: 10px solid yellow;

[StarWars.com | The Official Star Wars Website](https://www.starwars.com/)

### outline / border

[](https://aboooks.tistory.com/228)

### font

[CSS에 대한 깊은 이해: 폰트 매트릭스, line-height와 vertical-align | WIT블로그](https://wit.nts-corp.com/2017/09/25/4903)

### :hover

CSS의 :hover는 JS에서 "mouseenter"로 같은 효과를 줄 수 있다. ↔ "mouseleave"

## JS

### Babel

## Design

### 디자이너와의 소통

- 맞춰주어야 하는 1px과 그렇지 않은 1px을 맞춰주어야한다.
