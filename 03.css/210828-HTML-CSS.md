|   date   | title |     skill     |
| :------: | :---: | :-----------: |
| 21.08.27 |  CSS  | HTML, CSS, JS |

---

# TIL

1. HTML
2. CSS
3. Figma
4. Etc

---

# 0828

## Progammers - today

1. 신규 아이디 추천
2. 숫자 문자열과 영단어
3. 체육복

## HTML

### data attribute

- HTML5에서 생긴 문법이지만 다양한 브라우저에서 지원하고 있다.

  [https://caniuse.com/?search=data-](https://caniuse.com/?search=data-)

[Using data attributes - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

HTML DOM에 직접적으로 속성(attribute)을 추가할 수 있다.

- HTML

  `data-key-name="value"`

  반드시 `data-` 를 작성한 뒤 key와 value를 적어준다.

- CSS

  속성선택자를 이용해서 스타일을 입힐 수 있다.

  (div)`[data-key-name="value"] {color:#000;}`

- JS

  쿼리셀렉터를 이용해서 선택한 후 `dataset.keyName` 을 이용해서 value를 사용할 수 있다.

  DomStringMap안에 해당 데이터는 객체 형태로 저장이 된다.

  - key는 저장되면서 1. data-삭제 2. -표기법은 camel 표기법으로 변환 의 단계를 거쳐 `{keyName: "value"}의 형태로 저장된다. (객체의 이름은 dataset?)

> 주의할 점

해당 데이터들은 DOM안에 저장이 된다. 그렇기 때문에 HTML 상에서 데이터들의 값이 바로 보여지기 때문에 보안에 민감한 데이터들은 위의 방식처럼 DOM에 저장하지 않고 JS를 이용해서 저장해야 한다.

## CSS

### background attachment

### margin with design

### vertical-align, text-align

inline 혹은 inline-block요소에 사용이 가능하다.

---

### position sticky

자신의 위치가 relative의 위치에 존재 할 수 있을 때까지는 relative의 위치를 지키고 있다가 그 위치를 벗어나야하는 상황(스크롤이 올라가거나)이 오면 sticky로 지정된 위치를 갖게 됩니다.

- 예를 들어 부모와 자식(sticky)의 top 간격이 20px정도의 기존 위치가 있었습니다. 그러나 sticky를 `top: 30px`로 지정을 한다면 스크롤링 하기 전에도 30px의 간격을 남기고 밑쪽으로 이동해 있을 겁니다.
  - 무조건적인 부모와의 거리를 정함
- 그런데 왼쪽에 붙어있던 요소에 left값을 더 주게 된다면 viewport기준으로 위치가 정해지게 된다. 이유가 뭐지

sticky를 위치 지정이 의도한 대로 동작하게 하려면 top, left, right,bottom 중 적어도 하나의 값이 필요합니다.

- 그러나 보통 top값을 사용하는 이유는 left나 right의 경우 스크롤이 X축으로 움직일때나 효과가 보일텐데 그러한 경우는 드물기도 하고. bottom일 경우는 굳이 밑부분과의 간격이 필요한 경우가 드물기 때문이다.

---

### Position absolute를 이용한 중앙정렬

- margin `-` 를 이용한 방법
- transform : translate(-50% -50%)를 이용한 방법
  - translate의 % 기준은 자신의 넓이이다. 그렇기 때문에 부모의 사이즈가 자식의 사이즈의 두배라고 한다면 단순히 `transform: translate(50%,50%)`로도 중앙 배치가 가능한다.

---

### CSS custom property

구버전, 혹은 몇 개의 브라우저는 지원하지 않는다.

[Custom properties (--\*): CSS variables - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)

- hard-coded : 수동적인 코드 작성법

  → 자주 사용하는 값은 의미를 부여해서 상수나 변수로 사용하는 것이 좋다.

Syntax: `--key: value;`

Use: `var(key)`

- 선언된 custum property는 자신과 자신의 자식요소에서만 사용이 가능하다.

  → 그렇기에 `:root{}` 요소에 변수를 선언하는 것이 좋다.

  @media query와 함께 사용하면 전체적인 스타일을 바꿀 때 쉽게 바꿀 수 있다.

  ```css
  :root {
    --color: #000;
  }

  @media screen and (max-width: 768px) {
    :root {
      --color: #ededed;
    }
  }
  ```

- **clac ()**

  clac를 사용해서 기본 변수값에 변화를 줄 수 있다. 그리드 디자인일 경우 8의 배수 10의 배수를 기준으로 디자인 되는 경우가 많기 때문에 유용하게 사용할 수 있다.

  calc()와 함께 사용하기

  ```css
  /* 기본 변수 선언 */
  --basic-spacing: 8px;
  /* calc 함수 함께 사용 */
  margin: calc(var(--basic-spacing) * 2); //16px
  ```

- 기본값

  만약 선언되지 않은 변수를 사용했을 때를 대비해서 기본값을 설정할 수 있다.

  `var(not-key**, 8px);**`

  , 뒤에 오는 값이 기본 값으로 사용된다.

## Figma

[피그마가 보이다. v0.9](https://www.notion.so/v0-9-d12f994234894805980100a6d1d34680)

[E.UID](https://www.youtube.com/c/%EC%9D%B4%EB%93%AC)

### 툴 테크닉

## ETC

### Dark Mode

[다크모드의 의의와 웹환경에서의 구현](https://tecoble.techcourse.co.kr/post/2021-04-26-dark-mode/)

브라우저 내에서 설정할 수도 있지만 대체로 브라우저가 사용자의 OS 설정을 확인하고 다크모드로 맞춰준다.

이러한 방법은 CSS의 `@media (prefers-color-scheme: dark(or light)`로 설정할 수 있다.

그러나 이 방식은 해당 서비스에서 모드를 변경하기 위해서는 다시 OS 설정을 바꾸는 일을 해야한다는 것인데, 그렇게 된다면 사용자에게 귀찮음을 안겨주게 된다. 그렇기 때문에 토글등을 이용하여 유저가 임의로 조정할 수 있게 해주는 것이 좋은데, 이는 유저가 테마를 직접 선택이 가능하다는 점에서 유저의 개인화에 대한 욕구를 충족시켜 줄 수 있다.
