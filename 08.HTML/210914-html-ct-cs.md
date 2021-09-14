|   date   |        title        |    skill     |
| :------: | :-----------------: | :----------: |
| 21.09.14 | CS강의, Toy Projext | HTML, CS, CT |

---

# TIL

1. HTML
2. CS
3. CT

---

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)

# 0914

## HTML

### 토이 프로젝트 체크리스트

- [ ] before 이용해서 +를 추가해보기
- [ ] swiper → 화면 추가해보기
- [ ] swiper → 리스트 넘기기
- [ ] 시계 기능 구현해보기

---

팀원분들 html css 확인해보기

### 체크리스트

- [ ] 클래스네임 확인하기
- [ ] 적절한 주석 사용
- [ ] 웹 접근성
  - 논리적 구성
  - 대체 텍스트 사용
- [ ] 구조와 표현의 분리 (닫기 버튼의 위치)
- [ ] 의미적인 태그 사용
- [ ] 플렉스를 필요 이상으로 사용한 부분이 있는지 체크
- [ ] 크로스 브라우징

### Semantic page

- double

[HTML](https://html.spec.whatwg.org/multipage/grouping-content.html#the-main-element)

[hidden - HTML: Hypertext Markup Language | MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Global_attributes/hidden)

### **hidden**

> `display: none;` `<input hidden/>`

디스플레이로 요소를 스타일링하는 것보다 요소에 숨겨진 속성을 배치하는 것이 더 의미가 있다는 것입니다.

**참고 :** `hidden` 속성을 가진 요소 에서 CSS `[display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) 속성 값을 변경 하면 동작이 무시됩니다. 예를 들어 `hidden` 스타일 의 존재 에도 불구하고 `display: flex` 요소 가 표시됩니다 .

`hidden` [전역 속성은](https://runebook.dev/ko/docs/html/global_attributes) 요소가 아직 없습니다, 또는 더 이상임을 나타내는 부울 속성입니다.

예를 들어, 로그인 프로세스가 완료 될 때까지 사용할 수 없는 페이지 요소를 숨기는 데 사용할 수 있습니다. **브라우저는 `hidden` 요소를 렌더링하지 않습니다**

그만큼 `hidden` 속성은 하나의 프리젠 테이션에서 숨기기 콘텐츠를 사용할 수 없습니다.

숨김으로 표시된 항목은 예를 들어 스크린 리더를 포함한 모든 프레젠테이션에서 숨겨집니다.

**숨겨진 요소는 숨겨지지 않은 요소와 연결되어서는 안되며** 숨겨진 요소의 하위 요소 인 요소는 여전히 활성 상태이므로 스크립트 요소는 계속 실행하고 양식 요소는 계속 제출할 수 있습니다.

- 예를 들어 `href` 속성을 사용하여 `hidden` 속성으로 표시된 섹션에 연결 하는 것은 올바르지 않습니다 . 컨텐츠가 적용 가능하지 않거나 관련이없는 경우 링크 할 이유가 없습니다.

그러나 요소와 스크립트는 다른 상황에서 숨겨진 요소를 나타낼 수 있습니다.

그러나 ARIA `aria-describedby` 속성을 사용하여 숨겨져 있는 설명을 참조하는 것이 좋습니다. 설명을 숨기는 것은 그 자체로 유용하지 않다는 것을 의미하지만, 설명하는 요소에서 참조되는 특정 컨텍스트에서 유용하도록 작성 될 수 있습니다.

마찬가지로 `hidden` 속성이 있는 캔버스 요소 는 스크립트 그래픽 엔진에서 오프 스크린 버퍼로 사용할 수 있으며 양식 컨트롤은 해당 양식 속성을 사용하여 숨겨진 양식 요소를 참조 할 수 있습니다.

---

[How to Use The HTML5 Sectioning Elements [Article] | Treehouse Blog](https://blog.teamtreehouse.com/use-html5-sectioning-elements)

### section

If you just need to group content together for styling purposes you should use a <div> element rather than a <section>.

### main

여러 페이지에서 반복되는 내용(로고, 검색 상자, 바닥글 링크 등)은 <기본> 요소 내에 배치해서는 안 된다.

**Note:** 여기서 ARIA role="main" 특성을 사용했는데, 이 특성은 아직 <main> 요소를 지원하지 않는 프로그램(예: 일부 화면 판독기)에 대한 이 요소의 중요성을 나타냅니다.

### nav

Marking up your links within a list will often make your navigation easier to use, however this is not a requirement when using a <nav> element.

### header

콘텐츠와 관련된 일부 메타데이터가 포함됩니다. 또한 더 긴 문서를 위해 목차(<nav> 요소 내)를 포함할 수 있다.

### address

This element is not for marking up postal address, but rather for representing the contact information for an article or web page.

- This element is often used within the <footer> for an <article>.

> Note: Not all screen readers have support for these semantic elements yet. You may want to continue using ARIA roles just to be safe.

---

### WAI-ARIA

[WAI-ARIA 의 개념과 role](https://yongbeomkim.github.io/html/html-web-aria/)

## CSS

## JS

### JSON 다루기

## DB

## CS

### 좋은 개발자

- CS 지식 (운영체제, 네트워크) + 컴퓨터 구조
- 데이터 베이스 SQL,NoSQL
- 자료구조, 알고리즘 및 코딩 테스트

### 폰노이만 구조

![https://mblogthumb-phinf.pstatic.net/MjAyMDA1MjhfMjgx/MDAxNTkwNjQxMTY1NDMy.w51HcT4jYp2OKHYNkUukDXx93m4YnGX04-_kYpOhLlQg.QGXBnWQ2n3haBw0IOM-lqJyBrJrbS_koOxI9mthgxlcg.PNG.with_msip/SE-0a7a2aaa-2572-4930-bc3c-45722a6ec0a7.png?type=w800](https://mblogthumb-phinf.pstatic.net/MjAyMDA1MjhfMjgx/MDAxNTkwNjQxMTY1NDMy.w51HcT4jYp2OKHYNkUukDXx93m4YnGX04-_kYpOhLlQg.QGXBnWQ2n3haBw0IOM-lqJyBrJrbS_koOxI9mthgxlcg.PNG.with_msip/SE-0a7a2aaa-2572-4930-bc3c-45722a6ec0a7.png?type=w800)

이 구조의 가장 큰 장점은 프로그램 내장 방식 컴퓨터라는 점입니다. 예시를 통해 쉽게 설명해보겠습니다.

이전 컴퓨터는 1+1, 3-2 라는 두 가지의 명령을 수행하려면 하드웨어의 전선을 직접 1, 더하기, 1, 3, 빼기, 2를 의미하는 것으로 매번 바꿔 끼워 입력해야 했습니다.

그러나 폰 노이만 구조에서는 **더하기, 빼기 기능을 담은 소프트웨어가 메모리 안에 내장**되어 있습니다. 그래서 계산이 필요할 때마다 메모리 안의 프로그램과 데이터를 CPU에 전달하여 계산을 처리합니다.

> fetch, 명령어의 의미를 해석하는 decode, 명령어를 실행하는 execute, 결과를 저장하는 store의 순서

- ‘내장 메모리 순차처리 방식’을 따르고 있기 때문에 CPU는 순차적으로 한 번에 명령어 하나씩 실행합니다.

### 컴퓨터 구조

- Central Processor Unit

  - 산술(arithmetic Operation) 연산 (+)
  - 논리 연산 (if >)

- Memory (코드와 데이터를 저장하는 장치)
  - 내부 기억장치 (주)
    - CPU 안에 레지스터, 캐쉬
    - DRAM등 메모리 (RAM...)
  - 외부 기억장치 (보조)
    - SSD, HDD
  - Bus
    - CPU, Memory,IO Devises를 연결해주는 장치

### binary

> 2진법

- 유니코드

  [Unicode와 UTF-8 간단히 이해하기](https://jeongdowon.medium.com/unicode%EC%99%80-utf-8-%EA%B0%84%EB%8B%A8%ED%9E%88-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-b6aa3f7edf96)

  > 국제적으로 전세계 언어를 모두 표시할 수 있는 표준코드를 만들기로 했다. 바로 유니코드(Unicode)다.

  - **UTF-8은 유니코드를 인코딩(encoding)하는 방식이다. 전세계에서 사용하는 약속이다.**
  - UTF-8은 가변 인코딩방식

- Logical Operation

  and는 직렬 / or은 병렬로 볼 수 있다.

  not (Nand / Nor)
