|   date   |     title      |    skill     |
| :------: | :------------: | :----------: |
| 21.08.31 | CT / HTML 수업 | HTML, CSS,JS |

---

# TIL

1. CT -kakao2
2. HTML
3. CSS
4. JS
5. DESIGN

---

# 0831

## assignment

- 과제 깃헙 -3번

  [https://github.com/wuixwui/temp](https://github.com/wuixwui/temp)

- 링크

  [https://wuixwui.github.io/temp/](https://wuixwui.github.io/temp/)

---

### 질문

- BFC 의 display: flow-root

  float를 해제하기 위해서 clear-fix 방식이나 컨테이너를 BFC요소로 만드는 방식이 있는데, 주로 clearfix 방식을 사용한다고 합니다. 하지만 이 방법은 float 요소를 포함하기 위해 불필요한 요소를 삽입하기 때문에 가독성이 좋지 않다고 설명하는 글도 있었습니다.

  그러던 중 계속 눈에 보이던 display 속성이 flow-root 였는데 [https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Block_formatting_context](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Block_formatting_context)

  mdn 문서의 설명 중

  > The value name of flow-root makes sense when you understand you are creating something that acts like the root element (<html> element in browser) in terms of how it creates a new context for the flow layout inside it.

  이 부분이 잘 이해가 되지 않아서요.. 루트 요소를 html 내부에서 만든다는 의미인 건가요?

  → 이부분에 대해서 계속 찾아봤는데 혹시

  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bdb79b3a-3db0-4e64-af29-f83bbc4aaa5f/Untitled.png)

  이러한 부분에 대한 설명일 까요? p태그가 float된 이미지 뒤로 단순히 밀리는 것이 아니라 완전히 분리된다는 의미에서 `how it creates a new context for the flow layout inside it.` 인걸까요?😥

  - flow layout 기본적인 블록과 인라인 요소가 보여지는 방식

- 가운데 라인에 대한 질문

  다시 읽는 네이버 캐스트 부분에서 왼쪽과 오른쪽을 나눠주는 라인에 대해서 질문이 있습니다!

  처음에는 한쪽에 `border-right` 나 `border-left` 를 이용해서 주려고 했는데 그러다 보니 가운데 라인의 height에 맞추면 레이아웃이 애매해지게 되었습니다.

  결국 HTML에 직접 ul사이에 새로운 div를 만들고 스타일링을 하게 되었는데 이러한 방법 말고 가운데 선을 긋기 위한 좋은 방법이 있을까요..?

  처음에는 ::after 방법을 사용해 보려고 했었는데 ul에 적용하게 된다면 li안으로 들어가 버리고 cont에 적용하자니 가운데에 위치하게 할 수가 없어서요!

  ![recast.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8a8d35b3-7fba-46f9-b623-317435e5a27b/recast.jpg)

---

## Progammers - today

1. 신규 아이디 추천

   [[프로그래머스] 오늘의 문제.15](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.15)

2. 숫자 문자열과 영단어

   [코딩테스트 연습 - 숫자 문자열과 영단어](https://programmers.co.kr/learn/courses/30/lessons/81301)

   정리(0901)

3. 체육복

   [[프로그래머스] 오늘의 문제.16](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.16)

---

## HTML

### a

HTML은 inline 요소 안에 block 요소가 들어 오는 것을 지양하지만 a태그는 기능으로 인해 사용한다.

### 웹 접근성

HTML 마크업을 할때 논리 구조(리더기로 읽혔을 때의 순서)를 생각하면서 마크업 하는 버릇을 들이자.

디자인만을 만드는 것에 집중하지 말것..! 😥

## CSS

### Typo

- css component를 만들 때 typography를 먼저 잡고 들어간다.

  → 이럴 경우 global setting을 미리 잡아주면 좋다.

- line-height는 전체적으로 잡아주는 기준이 존재하기 때문에 이후 추가 수정을 생각해서 단순히 레이아웃을 위해 임의적으로 변경하기 전에 생각을 꼭 해봐야한다.

### Design sync

디자인 이미지와 맞춰볼때 position과 opacity를 이용해서 겹쳐보면 완벽하게 싱크를 맞출 수 있다.

- class 이름을 위치 기반으로 (left나 right) 사용하게 되면 반응형 디자인일때 이해가 되지 않는 이름이 될 수도 있다.

### CSS 순서

보더 →넓이 높이 패딩, 마진, 간격 → 디테일 타이포 색 → 플롯, 포지션 → 정리

- 특정 요소마다 값이 다를 경우 inline속성으로 관리해도 좋다.

### BFC Block Formatting Context

[[CSS 바로 알기] Block Formatting Context](https://blueshw.github.io/2020/05/17/know-css-block-formatting-context/)

**BFC는 margin 병합을 막는다.**

[CSS 마진 상쇄(Margin-collapsing) 원리 완벽 이해](https://velog.io/@raram2/CSS-%EB%A7%88%EC%A7%84-%EC%83%81%EC%87%84Margin-collapsing-%EC%9B%90%EB%A6%AC-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4)

- margin collapse

  1. 인접 형제 박스 간 상하 마진이 겹칠 때 (제일 많이 만나는 현상)
  2. 빈 요소\*의 상하 마진이 겹칠 때 (뭐야 왜이래 하면 대체로 이 현상)

     - 빈요소란?

       height / min-height / padding / border 등 상하로 늘어나는 프로퍼티 값을 명시적으로 주지 않았거나

       내부에 Inline 콘텐츠가 존재하지 않는 요소

     상단 마진과 하단 마진 중 더 큰 값으로 상쇄

     상쇄가 **연속적으로** 발생할 수도 있다.

     ![https://media.vlpt.us/post-images/raram2/ffac75c0-121f-11ea-aaba-65695302c179/02-margin-collapsing-emptybox-case.png](https://media.vlpt.us/post-images/raram2/ffac75c0-121f-11ea-aaba-65695302c179/02-margin-collapsing-emptybox-case.png)

  3. 부모 박스와 첫번째 (마지막) 자식 박스의 상단, 하단 마진이 겹칠 때

     브라우저는 부모 박스와 첫 번째(마지막) 자식 박스 간의 경계를 그 사이에 있는 border / padding / inline 콘텐츠 유무로 판단합니다.

     앞에 설명했던 빈 박스의 마진 상쇄 현상과는 조금 다르게, 이미 명시적으로 height / min-height 값을 줬더라도 이번 경우에선 신경 쓰지 않습니다.

     **부모와 자식 간의 마진 병합을 막기 위해서는 꼭 border /padding / inline 중 하나의 값이 존재해야 합니다.**

     만약 border,padding,inline 중 어느 것도 포함되지 않는다면 이때, 자식 요소의 마진이 더 크든 작든 상관없이 상쇄된 마진은 **부모 박스의 바깥으로만 렌더링이 됩니다. (크기는 더 큰 마진을 기준으로)**

  ### 마진 상쇄 규칙 적용

  - 마진 상쇄는 인접한 두 박스가 온전한 **block-level** (width가 자동으로 늘어나는 요소)요소일 경우에만 적용됩니다.
    (inline, inline-block, table-cell, table-caption 등의 요소는 block-level이 아닙니다.)
  - 마진 값이 0이더라도 상쇄 규칙은 적용됩니다.
  - 좌우 마진은 겹치더라도 상쇄되지 않습니다.

  ### 마진 상쇄 규칙 예외

  다음과 같은 상황에서는 인접 요소 간 마진 상쇄가 일어나지 않습니다.

  - 박스가 `position: absolute` 된 상태
  - 박스가 `float: left/right` 된 상태 (단, clear 되지 않은 상태)
  - 박스가 `display: flex` 일 때 내부 flexbox item
  - 박스가 `display: grid` 일 때 내부 grid item

이번 수업 중 margin이 내 마음대로 사용되어지지 않은 이유가 바로 이것이다.

> 부모 박스와 첫번째 (마지막) 자식 박스의 상단, 하단 마진이 겹칠 때

브라우저는 부모 박스와 첫 번째(마지막) 자식 박스 간의 경계를 그 사이에 있는 **border / padding / inline** 콘텐츠 유무로 판단합니다.

앞에 설명했던 빈 박스의 마진 상쇄 현상과는 조금 다르게, 이미 명시적으로 height / min-height 값을 줬더라도 이번 경우에선 신경 쓰지 않습니다.

**부모와 자식 간의 마진 병합을 막기 위해서는 꼭 border /padding / inline 중 하나의 값이 존재해야 합니다.**

만약 border,padding,inline 중 어느 것도 포함되지 않는다면 이때, 자식 요소의 마진이 더 크든 작든 상관없이 상쇄된 마진은 **부모 박스의 바깥으로만 렌더링이 됩니다. (크기는 더 큰 마진을 기준으로)**

부모 박스의 바깥으로 margin이 적용되다 보니 float으로 띄워진 이미지와의 높이를 맞추기 위해 text(block요소)에 넣어준 margin으로 오히려 원하지 않던 여백이 생겨버리게 된 것이다.

### flex tip

- `flex basis` : item의 기본 비율을 정할 수 있다. (grid의 column처럼 사용할 수 있다.)
- `@media`로 화면이 작아졌을 때 `flex-grow` 를 함께 사용하면 `width:100%` 느낌을 줄 수 있다.
- `flex order` 의 기본값은 0으로 +1이 될수록 먼저 올 수 있다.

### pointer-event

클릭 값을 정할 수 있다.

- none : 클릭할 수 없다.
- auto : 기본값으로 클릭할 수 있다.

## Design

### margin with design

- 디자인에서 사용하는 그리드의 column 개수는 대체로 12개를 베이스로 한다.
  - 기본적으로 사용되는 1,2,3,4,6등 같은 사이즈의 section을 만들기에 쉽다.
- 여백은 계층(hierarchy)을 나눈다.

  가까운 오브젝트일수록 같은 계층으로 인식 될 수 있다.

  → 여백의 크기 차이로 그룹핑을 시킨다.

  → 그렇기 때문에 HTML 구조를 나누고 스타일링을 해줄 때 이러한 구조를 생각하면서 margin과 padding을 나눠주는 편이 이후 추가 수정에 도움이 된다.

- 모바일 화면에서 3개의column이 max이다.
- 보통 사용하는 여백은 8,10의 배수

  [https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/1Gdv/image/cy25j35DVoTzV-0xYauYBYO1Es0.png](https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/1Gdv/image/cy25j35DVoTzV-0xYauYBYO1Es0.png)

  - component 8~24 / layout 24 ~ 64
  - component 10~30 / layout 30 ~ 60

- 사이드와의 여백은 가독성에 도움이 된다.

### 토스 디자인 컨퍼런스2

1. 당연하다는 불편함을 이해하고 해결하는 방법을 생각
2. 필요한 부분을 쪼개고 나누는 귀찮은 부분을 해결하는 것이 사용자 편의를 올릴 수 있는 방법
