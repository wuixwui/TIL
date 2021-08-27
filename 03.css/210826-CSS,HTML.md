|   date   | title |   skill   |
| :------: | :---: | :-------: |
| 21.08.26 | float | HTML, CSS |

---

# TIL

1. HTML
2. CSS

---

# 0826

## assignment

- 23일 과제 깃헙

  [https://github.com/wuixwui/temp](https://github.com/wuixwui/temp)

- 링크

  [https://wuixwui.github.io/temp/](https://wuixwui.github.io/temp/)

- 작업을 하면서 생긴 궁금점

  1. 텍스트 높이 같은 부분이 크롬과 파이어 폭스에서 다르게 나오는 경우가 있는데 이런 경우는 어떤 식으로 처리해야 하나요?

     post의 전체 높이가 4픽셀정도 맞지 않아서 확인하니 크롬에서 post—contents부분에서 4픽셀정도의 오차가 발생합니다. 그러나 파이어 폭스에서는 이러한 오차가 발생하지 않습니다.

     line-height, font-weight, font-size가 다 같은데 어째서 다른 값이 나오는 걸까요😥

---

- 26일 과제 (진행중)

### 질문

- 강한 연결과 느슨한 연결

  느슨한 연결을 베이스로 사용하기 위해서는 클래스를 많이 만들어야 할텐데, 클래스를 많이 사용하는 것(느슨한 연결)과 태그 선택자를 사용하는 것(강한 연결) 중 클래스를 사용하는 쪽이 이후 추가 및 수정이 더 쉬운것인가요?

- 배경 이미지를 사용했을 때의 데이터 측면에서의 장점?

  이미지 태그로 같은 이미지를 여러번 불러오게 되면 같은 이미지를 여러장 다운로드하게 되는 건가요?

---

## HTML

### font x-height

vertical align의 middle은 서체에 따라서 위치가 달라진다.

- h의 경계에서 base-line까지가 x-height가 된다.

vertical align을 픽셀값으로 조절해서 중심을 맞춰준다. (밑으로 내릴때 -값)

### Span 붙이기

Span의 컨테이너의 폰트 크기를 0으로 조절하고

### Flex 사용하지 않고 한줄에 배치하기

- text-align값을 이용해 원하는 방향으로 옮긴뒤
- 인라인 요소에 마진값으로 위로 올려서 한줄에 배치하는 것이다.

### Strong b em i

strong, em 의미론적으로의 강조

b i 시각적인 의미로의 강조

### OS의 CSS style

input, textarea, button, select, scroll 등은 default style이 OS를 기준으로 스타일이 입혀지기 때문에 컨트롤하기가 어려운 부분이 많다.

vender-prefix, 혹은 기본 스타일 위에 새로운 스타일을 만드는 방법을 사용한다.

---

### HTML UX ( 웹 접근성 )

마크업 작업은 기계가 읽는 **순서**를 생각해야 하고 CSS로는 시각적인 배치를 생각해야 합니다.

- CSS 상에서 위치를 기준으로 HTML 순서를 맞추면 안됩니다.

  논리적인 이야기 순서대로

### 랜더링

- 포지션층
- float 층
- 기본 flow

## Float

클래식한 방식의 수평정렬

float층으로 띄운다.

포지션 층과의 차이는 위치 배치가 포지션보다 자유롭지 않다는 점이다.

[CSS 레이아웃 핵심속성 float](https://jihyehwang09.github.io/2019/02/03/css-layout-float/)

기본 flow에서 자식이 float층으로 빠져나가게 되면 float을 해제(clear)해야만 부모가 다시 float 요소들을 감쌀 수 있다.

float 층 밑에 있는 text는(line box)는 float을 피해서 흘러간다.

**그렇기 때문에 flow층과 flex 사이에 여백을 주고 싶은 경우 float층에 여백을(margin)을 주면 된다.**

flex,grid는 웹에서 사용되지 않는 경우가 많은데 브라우저에 아직 적용이 안되는 경우들이 많기 때문이다.

[float 대신 grid와 flex만써도되나요.?? - 인프런 | 질문 & 답변](https://www.inflearn.com/questions/205288)

그렇기에 오히려 모바일 앱에서는 float 대신에 flex를 사용합니다.

### float 해제 (clear)

BFC

부모에 이러한 요소들이 존재한다면 자식요소에 float 해제가 필요하지 않는다.

[](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Block_formatting_context)

- 문서의 루트 요소(`[<html>](https://developer.mozilla.org/ko/docs/Web/HTML/Element/html)`).
- 플로팅 요소(`[float](https://developer.mozilla.org/ko/docs/Web/CSS/float)`이 `none`이 아님).
- 절대 위치를 지정한 요소(`[position](https://developer.mozilla.org/ko/docs/Web/CSS/position)`이 `absolute` 또는 `fixed`).
- 인라인 블록(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `inline-block`).
- 표 칸(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `table-cell`, HTML 표 칸의 기본값).
- 표 주석(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `table-caption`, HTML 표 주석의 기본값).
- `[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `table`, `table-row`, `table-row-group`, `table-header-group`, `table-footer-group` (HTML 표에서, 각각 표 전체, 행, 본문, 헤더, 푸터의 기본값) 또는 `inline-table`인 요소가 암시적으로 생성한 무명 칸.
- `[overflow](https://developer.mozilla.org/ko/docs/Web/CSS/overflow)`가 `visible`이 아닌 블록 요소.
- `[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `flow-root`.
- `[contain](https://developer.mozilla.org/ko/docs/Web/CSS/contain)`이 `layout`, `content`, `paint`.
- 스스로 플렉스, 그리드, 테이블 컨테이너가 아닌 경우의 플렉스 항목(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `flex` 또는 `inline-flex`인 요소의 바로 아래 자식)
- 스스로 플렉스, 그리드, 테이블 컨테이너가 아닌 경우의 그리드 항목(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `grid` 또는 `inline-grid`인 요소의 바로 아래 자식)
- 다열 컨테이너(`[column-count` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) 또는 (`[column-width` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width)가 `auto`가 아닌 경우. `column-count: 1` 포함).
- `[column-span` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-span)이 `all`인 경우. 해당하는 요소가 다열 컨테이너 안에 위치하지 않아도 항상 새로운 블록 서식 맥락을 생성해야 합니다. ([명세 변경](https://github.com/w3c/csswg-drafts/commit/a8634b96900279916bd6c505fda88dda71d8ec51), [Chrome 버그](https://bugs.chromium.org/p/chromium/issues/detail?id=709362))

## +

### Role?

[HTML - Role 한번 사용해보실래유?](https://happycording.tistory.com/entry/HTML-Role-%EC%99%9C-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC%EB%A7%8C-%ED%95%98%EB%8A%94%EA%B0%80)

### a11y

- accessibility

스크린 리더를 사용하는 사용자를 위한 정보가 담긴 HTML

CSS::after / ::before 같은 가상 선택자를 사용한다.

숨김처리

```css
position: absolute;
width: 1px;
height: 1px;
margin: -1px;
overflow: hidden;
clip: rect(0, 0, 0, 0);
```

clip에 대해 알아보기..!
