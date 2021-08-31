|    date     |     title      |    skill     |
| :---------: | :------------: | :----------: |
| 21.08.29-30 | CT / HTML 수업 | HTML, CSS,JS |

---

# TIL

1. CT -kakao
2. HTML
3. CSS
4. JS
5. DESIGN

---

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)

# 0829

## CSS

### tooltip

[[HTML/CSS] 툴팁 적용하는 방법 (title 및 커스텀 툴팁)](https://deeplify.dev/front-end/markup/tooltip)

JS를 이용한 tooltip

[Standards](https://standards.site/)

### global setting

CSS 작업이 들어가기 전 CSS custom property를 이용해서 기본적인 값들을 입력해 둔다.

대체로 **color, font size, font weight, size(margin,padding,spacing등)**

> 작업하다가 생기는 지속적으로 똑같이 사용되는 단위가 생긴다면 global setting 에 추가해준다.

```css
--font-weight-bold: 700;
```

- typography

  자주 사용하는 h1 h2 p등의 타이포 속성들의 weight 이나 margin등을 미리 설정해서 전체적인 통일감을 살릴 수 있도록 한다.

### transition

일반적으로 트랜지션 250~300ms 정도의 속도를 일반적으로 사용하게 된다.

→ 이런 경우 animation duration등을 global setting으로 custom property 로 만들어 두는 것이 좋다.

### cursor

텍스트 위에 선택 모양인 `I` 가 나오지 않게 하기 위해서는 body setting에서 `body { cursor: default}` 로 설정해 두면 모든 선택지에서 디폴트인 화살표 모양이 나올 것이다.

### flex

- flex basis : item의 기본 비율을 정할 수 있다. (grid의 column)

## JS

### Use strict

[엄격 모드](https://ko.javascript.info/strict-mode)

[Strict mode - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Strict_mode)

JavaScript 의 엄격모드는 JavaScript 의 제한된 버전을 선택하여 암묵적인 "느슨한 모드(sloppy mode)" 를 해제하기 위한 방법입니다.

- 엄격 모드의 코드가 다른 방식으로 동작할 것입니다, 그 때문에 엄격 모드가 적절하게 적용된 피쳐 테스트 없이 엄격 모드에 의존하면 안됩니다.
- 엄격 모드의 코드와 비-엄격 모드의 코드는 공존

1. 기존에는 조용히 무시되던 에러들을 throwing합니다.
2. JavaScript 엔진의 최적화 작업을 어렵게 만드는 실수들을 바로잡습니다. 가끔씩 엄격 모드의 코드는 비-엄격 모드의 동일한 코드보다 더 빨리 작동하도록 만들어집니다.
3. 엄격 모드는 ECMAScript의 차기 버전들에서 정의 될 문법을 금지합니다.

---

모던 자바스크립트는 **'클래스’와 '모듈’**이라 불리는 진일보한 구조를 제공합니다.

이 둘을 사용하면 **use strict가 자동으로 적용**되죠. _따라서 이 둘을 사용하고 있다면 스크립트에 "use strict"를 붙일 필요가 없습니다._

### scrollIntoView()

[Element.scrollIntoView() - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)

### getBoundingClientRect()

[Element.getBoundingClientRect() - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect)

- .offsetWidth(.offsetHeight와의 차이점)

### Web API - IntersectionObserver

[Intersection Observer API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

비동기적으로 변화를 감지하는 API

# 0830

## Progammers - today

1. 신규 아이디 추천

   [[프로그래머스] 오늘의 문제.15](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.15)

2. 숫자 문자열과 영단어

   [코딩테스트 연습 - 숫자 문자열과 영단어](https://programmers.co.kr/learn/courses/30/lessons/81301)

   정리(0901)

3. 체육복

   [코딩테스트 연습 - 체육복](https://programmers.co.kr/learn/courses/30/lessons/42862)

   정리 (0831)

---

## HTML

### position sticky

자신의 위치가 relative의 위치에 존재 할 수 있을 때까지는 relative의 위치를 지키고 있다가 그 위치를 벗어나야하는 상황(스크롤이 올라가거나)이 오면 sticky로 지정된 위치를 갖게 됩니다.

- 예를 들어 부모와 자식(sticky)의 top 간격이 20px정도의 기존 위치가 있었습니다. 그러나 sticky를 `top: 30px`로 지정을 한다면 스크롤링 하기 전에도 30px의 간격을 남기고 밑쪽으로 이동해 있을 겁니다.
  - 무조건적인 부모와의 거리를 정함
- 그런데 왼쪽에 붙어있던 요소에 left값을 더 주게 된다면 viewport기준으로 위치가 정해지게 된다. WHY?

  - sticky는 가장 근접한 부모 요소에 의거해서 포지션을 잡게 되는데,

    그런데 이때 가장 근접한 부모 요소가 모든 요소를 말하는것이 아니고,

    **스크롤이 가능한 부모 요소중!** 이랍니다.

    가장 가까운 부모 요소는 스크롤링이 되지 않고, 그 위의 상위 부모가 스크롤링이 된다면 그 부모를 기준으로 포지션이 되어요

sticky를 위치 지정이 의도한 대로 동작하게 하려면 top, left, right,bottom 중 적어도 하나의 값이 필요합니다.

- 그러나 보통 top값을 사용하는 이유는 left나 right의 경우 스크롤이 X축으로 움직일때나 효과가 보일텐데 그러한 경우는 드물기도 하고. bottom일 경우는 굳이 밑부분과의 간격이 필요한 경우가 드물기 때문이다.

### Position

- relative : 자신의 원래 위치를 기준으로
  - 만약 다른 요소로 인해 기준 위치가 바뀌게 된다면 그 바뀐 위치를 기준으로 다시 left,top등 위치를 잡고 이동한다.
- absolute: 위치상 부모를 기준으로
- fixed: viewport를 기준으로 (`backdrop-filter:` 속성이 있을 경우 viewport를 기준으로 잡지 못한다.)

- 요소에 **width나 height 값이 있는 경우** `left: 0, right:0` 의 속성을 가지고 있을 때 left가 위치가 우선시 된다. (top과 bottom의 경우도 top이 우선시 된다.

  width나 height가 없으면 위치 속성에 따라서 부모에 맞춰서 늘어난다.

  - **width에 margin이 포함이 된다.**
  - **부모의 border전까지가 요소의 100% (부모의 content-box+padding)**

- position을 줄 때 width값이 없고 기준점이 없다면 width 값은 content 박스만큼만 차지한다.

- 부모 요소 안의 자식의 z-index가 높아도 부모의 z-index가 낮다면 **부모의 z-index를 기준으로 적용이** 된다.

### semantic

[[HTML 바로 알기] Semantic Web을 위한 Semantic Elements](https://blueshw.github.io/2020/05/09/know-html-semantic-elements/)

- heade와 footer는 한 페이지 안의 section이나 article등의 영역에서 재 사용이 가능하다.

- aside는 의미상의 side

  블로그에서 측면의 **카테고리 목록이나 태그 목록** 등이 포함된 영역이 이에 해당한다. 하지만, <aside>를 본문 내에서도 사용할 수 있다. <article> 혹은 <section>에 <aside>가 위치하면, 본문 내용과 관련된 **부가정보**를 노출한다. 주석이나 각주 등이 이에 해당한다.

- main은 페이지에서(문서에서) 한번만 사용이 가능하다.

  본문을 뜻하며, **콘텐츠 내용 전체를 감싼다.**

- nav는 페이지전환,로그인등 **사이트의 공통기능을**

  사이트 전체 흐름을 제어하는 기능을 담당한다.

  → 문서의 변화와 상관없이 항상 노출되어 있는 경우가 많다.

- summary 태그와 details 태그

  `<details><summary></summary></details>`

  클릭했을 때, 상세 내용이 확장되는 UI에서 흔히 볼 수 있다.

- figure 태그와 figcaption 태그

    <figure>는 독립적인 콘텐츠를 의미한다. 내부에 <figcaption>을 사용해 부가 설명을 붙일 수 있다. 주로 인용문, 이미지, 소스코드에 설명을 쓸 때 사용한다.

> 시멘틱 요소는 검색엔진 최적화 SEO에도 영향을 준다.

영역 구분이 확실한 문서가 더 적절한 키워드를 추출하기 쉽기 때문에

### 구조 파악하기

```
['div', 'span', 'ul', 'li', 'dd', 'dl', 'section', 'h1', 'a', 'img', 'form', 'button', 'header', 'footer', 'input', 'p'].forEach(e => {
    document.querySelectorAll(e).forEach(element => {
        element.style.outline = "1px solid dodgerblue"
    })
})
```

## CSS

### background attachment

[background-attachment - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/background-attachment)

- local

  배경을 요소 콘텐츠에 고정 → 요소에 스크롤이 존재하면 **배경은 콘텐츠와 함께 스크롤** 됩니다.

  배경 페인트 영역과 배경 위치 영역은 테두리 틀이 아닌 스크롤 가능 영역을 기준점으로 삼습니다.

  (스크롤과 관련 있는 속성들은 기준점이 스크롤영역과 관련이 있는 듯 싶다. - position: sticky 또한 위치 상 부모 영역이 아닌 스크롤이 가능한 지점을 기준으로 위치를 잡는다.)

  ***

- fixed

  배경을 viewport에 고정

  background-clip: text와 호환되지 않습니다.

  - `backgroung-clip:text`

  [background-clip - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/background-clip#text)

  요소의 배경이 테두리, 안쪽 여백, 콘텐츠 상자 중 어디까지 차지할 지 지정합니다.

  text는 **text의 color가 transparent일 경우 폰트 안에 배경이미지를 삽입** 할 수 있다.

  - border-box, padding-box, content-box,text

  ***

- scroll

  배경을 요소 자체에 대해 고정합니다.

  요소에 스크롤이 존재해도 **배경은 함께 스크롤 되지 않습니다.**

  → **요소의 테두리에 배경 이미지를 부착**한 것과 같은 효과 입니다.

→ 예시 만들어 보기

→ clip이 자주 보이는데 어떤 속성인지 알아보기!

## JS

### Web API - IntersectionObserver

[Intersection Observer API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

비동기적으로 변화를 감지하는 API

## Design

### margin with design

### 토스 디자인 컨퍼런스

1. 맥락이 있는 상품과 혜택 - 광고주와 사용자의 윈윈
2. UX 단순히 답변이 아닌 답변을 한 사람에 대한 분석까지도 필요함. → 왜? 라는 질문의 중요성
   - 하나의 가설의 증명은 5명으로도 충분히 파악이 가능
3. 사용자를 위한 추천

---

## Web app

- Mobile **web APP**

  - mobile web?

    pc용 홈페이지를 모바일 스크린의 크기에 맞춘 것 (반응형 페이지)

    기본은 웹이지만 최대한 앱의 형식을 맞추려고 하는 반응형 웹

  모바일웹과 네이티브앱을 결합한 형태

  일반적인 웹기술로 개발되고 모바일 브라우저에서 실행된다.

  단일 페이지 방식

  - 장점
    1. 웹사이트를 보는 것이기 때문에 따로 설치할 필요가 없습니다.
    2. 모든 기기와 브라우저에서 접근할 수 있습니다.
    3. 별도 설치 및 승인 과정이 필요치 않아 유지 보수가 용이 합니다.
       - 설치 및 승인 과정? 네이티브의 앱일 경우 버전이 업그레이드가 되어 새로운 버전이 나왔을 때 사용자가 업데이트를(설치) 해야하며, 스토어에 다시 승인 과정을 밟아야 한다.
  - 단점
    1. 플랫폼 API (카메라 등) 을 사용할 수 없고 오로지 , 브라우저 API만을 사용할 수 있습니다.
    2. 친화적인 터치 앱을 개발하기가 약간 번거로운 점이 있습니다. (까다로움)
    3. 네이티브 , 하이브리드 앱보다 실행이 까다롭습니다. (브라우저를 열고 검색해 들어가야 합니다.)
