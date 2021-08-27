|   date   | title |     skill     |
| :------: | :---: | :-----------: |
| 21.08.27 |  CSS  | HTML, CSS, JS |

---

# TIL

1. HTML
2. CSS
3. JS

---

# 0827

## Progammers - today

[[프로그래머스] 오늘의 문제.14](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.14)

```jsx
function toWeirdCase(s) {
  var result = '';
  for (var word of s.split(' ')) {
    for (var i in word) {
      result += word[i][parseInt(i) % 2 == 0 ? 'toUpperCase' : 'toLowerCase']();
    }
    result += ' ';
  }
  return result.slice(0, -1);
}
```

### **computed property**

computed property name은 표현식(expression)을 이용해 객체의 key 값을 정의하는 문법입니다.괄호 [] 안에 식을 넣을 수 있고, **식이 계산되고 그 결과가 속성명**으로 사용됩니다.

```jsx
js;
var i = 0;
var a = {
  ['foo' + ++i]: i,
  ['foo' + ++i]: i,
  ['foo' + ++i]: i,
};

console.log(a.foo1); // 1
console.log(a.foo2); // 2
console.log(a.foo3); // 3
```

풀이 코드의

```jsx
for (var i in word) {
  result += word[i][parseInt(i) % 2 == 0 ? 'toUpperCase' : 'toLowerCase']();
}
```

`word[i][parseInt(i) % 2 == 0 ? "toUpperCase" : "toLowerCase"]()`부분은 인덱스가 홀수라면 (0부터 시작하기에 홀수일 경우 소문자로 출력) `word[i].toLowerCase()`로 사용이 되게 됩니다.

- `for(var i in word)`은 주로 객체 안에서 `for (let key in objsct)`형태로 사용이 되지만 **\*배열**에서 `for in`을 사용하게 되면 `i`의 위치의 인덱스 번호가 위치하게 됩니다.
- 공백이 많은 문자열 "try hello world"를 split(" ")으로 나누게 되면 'try', '', 'hello', '', '', '', 'world' 처음 공백을 제외한 나머지 공백의 수만큼 ''"로 배열에 담깁니다.

```jsx
result += ' ';
```

split으로 없어진 공백을 다시 추가해주는 부분입니다.

## assignment

---

- 26일 과제

  [https://wuixwui.github.io/temp/02_float_tab/index.html](https://wuixwui.github.io/temp/02_float_tab/index.html)

### 질문 - 답변

- 강한 연결과 느슨한 연결

  느슨한 연결을 베이스로 사용하기 위해서는 클래스를 많이 만들어야 할텐데, 클래스를 많이 사용하는 것(느슨한 연결)과 태그 선택자를 사용하는 것(강한 연결) 중 클래스를 사용하는 쪽이 이후 추가 및 수정이 더 쉬운것인가요?

  - 느슨한 연결을 사용하는 편이 추가 수정이 더 편한 부분이 있다.
  - 그러나 지나치게 클래스 네임이 길어지고 디테일 해질 경우 다른 팀원들에게 또는 복잡도가 올라갈 수 있다.
    - 그렇기에 **coding convention**이 존재한다.
    - [https://nuli.navercorp.com/upload/2020/6672a2b7-abdd-411e-8a50-362911bc7999_Coding_Conventions_for_Markup.pdf](https://nuli.navercorp.com/upload/2020/6672a2b7-abdd-411e-8a50-362911bc7999_Coding_Conventions_for_Markup.pdf)
  - **coding convention**

    ## 코딩 컨벤션 \_네이밍 규칙

    > 영문, 소문자, 숫자, 언더스코어(\_)로 작성한다.

    - CSS 주석에는 대문자 사용 가능

    ### id, class

    레이아웃을 제외한 id는 스타일을 지정하지 않는다.

    - 레이아웃에 디자인 속성을 추가/변경 하려면 class를 사용한다.

    id 사용은 예약된 범위에서만 사용 (주로 레이아웃)

    팝업 레이아웃은 앞에 pop\_을 조합한다. (ex: #pop_header)

    ### 종속 확장 class / 독립 확장 class

    - 종속 확장 class :기본형 class에 종속되어 여백, 색깔, 행간 등의 몇가지 속성을 부여하고자 할 때 사용하는 class
    - 독립 확장 class : 기본형 class의 변형이 타입으로 분류할 만큼 클 경우 사용
    - 네이밍 확장
      - 기본형 : list
      - 종속 확장 : list_v1
      - 독립 확장 : list2

    ### 이미지 네이밍 규칙

    > 형태*의미*상태

    - 임의로 축약하지 않는다.
    - 영문 소문자를 사용한다.
    - 숫자로 시작하지 않는다.
    - 확장자와 관계없이 순차적으로 사용한다.
    - 임시 이미지의 경우 앞에 tmp\_ 를 붙여준다.

    ### 파일 및 폴더 네이밍 규칙

    1. 파일

       - HTML

         > 메뉴이름*의미*상태 순서로 조합

         1. 기본: 서비스 영문 이름.html
         2. 팝업 파일: pop\_.html
         3. iframe 파일: ifr\_.html
         4. include 파일: inc\_.html
         5. tmp 파일: tmp\_.html

       - CSS

         > 서비스이름\_ 을 앞에 배치하며 조합

         1. 기본: 서비스 영문 이름.css
         2. 예외 대응시: 서비스 영문 이름\_[etc].css

    2. 폴더
       - 신규 프로젝트: p_yyyymmdd_projectname
       - img, css, js
       - tmp\_

    ### +

    - HTML

      - element의 attribute 중 class와 style은 제일 뒤쪽에 배치한다.
      - head는 meta → title → link → script → style 순서로
      - form,fildset, legend 를 사용한다.
      - input

        **label 요소, title 속성, alt 속성**등을 통해 스크린 리더 사용자는 주변 맥락에 대한 이해 없이 요소에 독립적으로 접근해도 폼을 이해할 수 있다.

        type이 radio, checkbox인 경우 그루핑이 필요하면 선택적으로 name 속성을 이용하여 항목들을 그루핑한다.

        [- HTML: Hypertext Markup Language | MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/select)

    ***

- 배경 이미지를 사용했을 때의 데이터 측면에서의 장점?

  이미지 태그로 같은 이미지를 여러번 불러오게 되면 같은 이미지를 여러장 다운로드하게 되는 건가요?

  img를 불러올 때마다 HTTP요청이 발생한다.

  - img태그를 불러와서 사용할 때: 주로 사진등의 이미지 (png,jpg)등에서 사용한다.
  - background-image는 주로 svg 파일이나 image replace등을 사용할 때 이용한다.

---

## HTML

### Float

[CSS 레이아웃 핵심속성 float](https://jihyehwang09.github.io/2019/02/03/css-layout-float/)

- float된 요소는 마크업 순서가 중요하다.

  float는 상단에서 float가 이루어지고 그 후에 다른 요소가 그 주위로 흐르기 때문에 **float 요소는 마크업 순서가 contents 요소보다 먼저 와야 한다!**

- `transition`과 `transform` 속성은 ie 크로스브라우징을 어느 정도 무시해야 한다는 생각이 있을 때 사용한다.(6-9버전)에서 사용할 수 없기 때문이다.

> 실무에서는 ie9버전을 맞춰야 하기 떄문에 float를 배우는 것이다.

### background 응용 애니메이션

[https://codepen.io/cod-we/pen/BaZNGxM?editors=1100](https://codepen.io/cod-we/pen/BaZNGxM?editors=1100)

background로 border을 만들어 돌린다고 생각하면 됩니다.

repeat과 gradient의 만남

### CSS marquee

[https://codepen.io/cod-we/pen/QWgbzvE?editors=1100](https://codepen.io/cod-we/pen/QWgbzvE?editors=1100)

line안에 있는 span을 inline-block을 사용해서 width값을 전체로 사용하게 한 뒤 서로의

---

grid column을 이용해서 표 느낌의 레이아웃을 만들 수 있다.

`grid-template-column: 1fr 4fr 5fr;`

- grid - auto value

  **`auto`**

  As a maximum represents the largest `[max-content](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content)` size of the items in that track.

## +

### Role?

[WAI-ARIA Roles - 접근성 | MDN](https://developer.mozilla.org/ko/docs/Web/Accessibility/ARIA/Roles)

element에 역할을 부여해준다고 생각해두기. 자세한 부분들은 이후에 더 찾아보자. 갈 길이 멀다.

---

내용 추가

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)
