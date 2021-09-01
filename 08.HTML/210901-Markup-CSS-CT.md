|   date   |     title      |    skill     |
| :------: | :------------: | :----------: |
| 21.09.01 | CT / HTML 수업 | HTML, CSS,JS |

---

# TIL

1. CT -kakao3
2. HTML-markup
3. CSS
4. JS
5. DESIGN

---

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)

# 0901

## Progammers - today

1. 신규 아이디 추천

   [[프로그래머스] 오늘의 문제.15](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.15)

2. 숫자 문자열과 영단어

   [[프로그래머스] 오늘의 문제.17](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.17)

3. 체육복

   [[프로그래머스] 오늘의 문제.16](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.16)

---

## HTML

[https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FQzdiOfp8QbWQhaUVQiRe2e%2Fnaver-page](https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FQzdiOfp8QbWQhaUVQiRe2e%2Fnaver-page)

## CSS

### layout

여러가지의 페이지 중에서 규칙이 깨지는 부분을 확인하고 해결 방법을 생각해본다.

- 규칙
  - typo와 관련된 margin과 padding을 어느 부분이 가져야 하는 지를 판단해서 주어야 한다.
- 접근성을 생각하면서 마크업 순서 짜기

### vertical align

(인라인레벨요소에 적용 가능)

> item에 부여되는 속성으로 부모 (inline 혹은 table-cell)요소의 line-height에서의 수직위치를 정하는 속성이다.

[https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FPL82o%2FbtqC22MSVfa%2FBq5aEaCRKWRQARtg79tyBK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FPL82o%2FbtqC22MSVfa%2FBq5aEaCRKWRQARtg79tyBK%2Fimg.png)

- line과 inline 요소에 대한 이해가 필요하다.

  - line-height는 inline 요소일 경우 bg와 bd에 영향을 주지 않는다. 그저 text의 위치에 영향을 줄 뿐.

    [https://codepen.io/cod-we/pen/mdwPrvv](https://codepen.io/cod-we/pen/mdwPrvv)

[CSS: line-height 속성 이해하기](https://ohgyun.com/572)

- content 영역과 line영역을 헷갈리지 말자.

  line영역은 line-height 속성에 의해 결정되고, content 영역은 font-size 속성에 의해 결정된다.

- 행간 : line영역에서 content 영역을 제한 것

  만약, `line-height`가  `font-size`보다 작은 경우엔, 컨텐트 영역이 인라인 박스를 삐져나오게 되고, **상/하 행간은 인라인 박스의 반으로 적용된다.**

- **이미지가 추가되거나, button, input 등 브라우저에서 덮어쓴 인라인 엘리먼트가 추가되는 경우, 라인 박스의 크기는 가장 큰 엘리먼트의 박스에 맞게 늘어난다.**

  [https://t1.daumcdn.net/cfile/tistory/242EDA3B554DAE1A1F](https://t1.daumcdn.net/cfile/tistory/242EDA3B554DAE1A1F)

### word-break

[word-break - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/word-break)

> 텍스트가 자신의 콘텐츠 박스 밖으로 overflow 할 때 줄을 바꿀 지 지정합니다.

- keep-all 줄을 바꿀 때 단어를 끊지 않습니다.

### white-space

[white-space - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ko/docs/Web/CSS/white-space)

- 요소가 공백 문자를 처리하는 법을 지정합니다.

  - nowrap 줄바꿈 없이 한줄로
  - pre-wrap : 연속 공백 유지 / pre-line : 연속 공백 합침

    둘 다 줄 바꿈은 개행과 br 에서 일어나며, 한 줄이 길면 자동 줄 바꿈

  - break-spaces 몇가지의 차이를 빼면 pre-wrap과 동일
    - 연속 공백이 줄의 끝에 위치하더라도 공간을 차지합니다.
    - 연속 공백의 중간과 끝에서도 자동으로 줄을 바꿀 수 있습니다.
    - 유지한 연속 공백은 `pre-wrap`과 달리 요소 바깥으로 넘치지 않으며, 공간도 차지하므로 박스의 본질 크기(`min-content`, `max-content`)에 영향을 줍니다.

## JS

### scrollIntoView()

[Element.scrollIntoView() - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)

### getBoundingClientRect()

[Element.getBoundingClientRect() - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect)

- .offsetWidth(.offsetHeight와의 차이점)

### Web API - IntersectionObserver

[Intersection Observer API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

비동기적으로 변화를 감지하는 API

## Design

### 토스 디자인 컨퍼런스3

1. 인터렉션
2. 동적 인터페이스를 이용한 사용자 접근성 향상

---

### 실무에서 클린 코드

1. 흐름 파악이 어렵고, 도메인 맥락 표현이 안되어 동료에게 물어봐야 알 수 있는 코드는 좋지 못한 코드이다.
   - 하나의 목적인 코드가 흩뿌려져 있으면
   - 하나의 함수가 여러가지 일을 하고 있으면
   - 세부구현 단계가 제각각이라면
2. 클린 코드 = 유지보수 시간의 단

   - 원하는 로직을 빠르게 찾을 수 있는 코드

     클린코드 ≠ 짧은 코드

     - 응집도 - 당장 몰라도 되는 디테일을 모아둔다.

       핵심데이터만 전달하고 세부 구현은 뭉쳐 숨겨두는 프로그래밍 → 선언적 프로그래밍

       세부구현이 뭉쳐지지 않으면 명령형 프로그래밍

       - 두가지를 적절하게 사용해야합니다.

     - 단일책임

       코드가 하는 일을 확실하게 이름으로 나타내준다.

       - 한가지 일만 하는 명확한 이름의 함수
       - 기능성 컴포넌트
       - 조건이 많아지면 한글 이름도 유용합니다.

     - 추상화

       핵심개념을 담는다.

       추상화 수준이 섞여 있으면 코드 파악이 어렵다.

3. 액션
   - 담대하게 기존 코드 수정하기
   - 큰 그림 보는 연습하기
