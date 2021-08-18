|   date   |       title        |    skill     |
| :------: | :----------------: | :----------: |
| 21.08.18 | 스타벅스 클론 코딩 | HTML, CSS,JS |

---

# TIL

1. ScrollMasic
2. JS prototype, class
3. CSS

---

# 0818

## Progammers - today

[[프로그래머스] 오늘의 문제.8](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.8)

## JS

### 프로토타입

- 객체 생성자

  객체 생성자의 이름은 대문자로 작성해야한다.

  ```jsx
  function Object(parm1, para2, parm3) {
    (this.one = parm1),
      (this.two = parm2),
      (this.three = parm3),
      (this.fun = function () {
        console.log("함수가 실행됩니다.");
      });
  }
  ```

- 객체 생성

  ```jsx
  const newObject = new Object("one", "two", "three");
  ```

  이렇게 함수가 객체 생성자 내부에 존재할 경우 새로운 객체를 생성할 때마다 함수가 생성되게 되며, 같은 함수가 여러번 반복 생성되는 것은 비효율적입니다.

- [프로토타입] 객체 생성자

  ```jsx
  function Object(parm1, para2, parm3) {
  this.one = parm1,
  this.two = parm2,
  this.three = parm3,
  }
  ```

  ```jsx
  // 프로토 타입 함수 생성
  Object.prototype.fun = function() {
  console.log("프로토 타입 함수가 실행됩니다."}
  // 프로토 타입 변수 생성
  Object.prototype.sharedVar = 123;
  ```

- [프로토타입] 객체 생성

  ```jsx
  const newObject = new Object("one", "two", "three");
  ```

- [프로토타입] 객체 생성자 상속

  비슷한 객체 생성자를 계속해서 새로 작성하는 것보다 객체 생성자를 상속받아 사용하는 것이 좋습니다.

  ```jsx
  function NewObject(parm2, parm3) {
    Object.call(this, "parm1_default", parm2, parm3);
  }
  // call로 객체를 불러올때 this는 NewObject의 this입니다.
  NewObject.prototype = Object.prototype;
  ```

---

### 클래스

- 클래스 생성

  객체 생성자와 프로토타입을 조금 더 쉽게 사용할 수 있다.

  `constructor` 을 사용해서 인자를 생성한다.

  ```jsx
  class Object {
  constructor(parm1, parm2, parm3) {
  	this.one = parm1,
  	this.two = parm2,
  	this.three = parm3,
  }
  // 자동으로 프로토타입 함수로 설정된다.
  fun() {
  console.log("클래스 함수가 실행됩니다."}
  }
  ```

  ```jsx
  console.log(Object.prototype.fun);
  // 해당 fun함수가 콘솔에 출력됩니다.
  ```

- 클래스 객체 생성

  ```jsx
  const newObject = new Object("argu1", "argu2", "argu3");
  ```

- 클래스 상속

  ```jsx
  class NewObject extends Object {
    constructor(parm2, parm3) {
      super("Default parm1", parm2, parm3);
    }
  }
  // super는 상속 받은 Object의 인자들을 가리킨다.
  ```

### ScrollMagic library

화면에 요소가 보이는지에 대한 감지가 가능한 library

```jsx
new ScrollMagic.scene({
// 감시당할 요소
trigerElement: "Element",
// 감지되는 시점의 위치
trigerHook:0~1 // viewport의 top을 0, bottom을 1f로 친다.
})
.setClassToggle(Element,"class_name") //감지되면 해당 요소에 클래스 추가
.addTo(new ScrollMagic.Controller());
```

### Swiper

swiper -prev, next, pagination은 swiper-container 외부에 위치한다.

### Gsap ScrollToPlugin

scrollTo 옵션을 사용할 수 있게 해주는 Gsap의 plugin

```jsx
gsap.to(window, times, {
  scrollTo: 0,
}); // 화면 제일 위로 이동
```

## CSS

- img가 `display:block` 값이면 width값이 없어도 이미지의 원래 크기를 width 값으로 사용해 margin auto 속성을 사용가능하다.

- CSS 애니메이션으로 우선 구현해보고 CSS로 구현되지 않는 효과를 JS를 사용해서 구현한다.

  CSS보다 JS 가 좀 더 무겁기 떄문!

- `grid-gap` 과 gird-container의 `background` 의 속성을 이용해서 라인을 만들 수 있습니다.

  ← gap은 `grid-column-gap, grid-row-gap` 의 통합 속성입니다.

  - 이럴 경우 배경의 색과 item의 배경색의 차이로 라인을 생성하기 때문에 비어있는 공간은 <span>혹은 <div>등의 비어있는 태그로 채워주어야 합니다.

### grid와 flex의 align-items

- **flex:** stretch, flex-start, flex-end, center, baseline
- **grid:** normal(=stretch), start, center, end, stretch

### marquee

[: The Marquee element - HTML: HyperText Markup Language | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/marquee)

사용을 권장하지 않는다.

[Sale label](https://codepen.io/Anna_Batura/pen/dypeoxj)

- CSS로 구현

  ```css

  @keyframes marquee {
  	0% {
    left:0;
  	transform: translateX(-100%);
  	}
  	100% {
  	left:0;
  	transform: translateX(100%);
  	}
  }
  /* animation */
  /* 끝없이 정방향만 반복 */
  animation(marquee 4s linear infinite);
  		&:nth-child(1) {
  			position: absolute;
  			left: -100%;
  /* 딜레이가 있기 때문에 미리 위치를 화면 밖으로 보내둔다.*/
  			animation(marquee 4s 2s linear infinite);
  		}
  /* 딜레이는 요소의 간격을 주기 위해서 넣어줌 */
  ```

  container에는 `overflow: hidden; white-space: nowrap;` 속성이 있어야 한다.

  [https://happy-noether-c87ffa.netlify.app/presentations/level2/css3/](https://happy-noether-c87ffa.netlify.app/presentations/level2/css3/)

### 카드 뒤집기

`transform: rotateY()` 를 이용해서 3D 애니메이션을 제작할 수 있다.

.container

.front

.back

의 형태로 container는 자식의 크기와 동일하여야 하고 자연스러운 동작을 위해서 `perspective` 속성을 넣어주어야 한다.

- common

  `backface-visiblity:hidden` 값을 이용해서 뒤로 돌 경우 보이지 않게 한다.

- back

  transform rotateY()를 `-` 이용해서 뒤로 돌려둔다.

### :: Pseudo-Element

가상요소는 해당요소의 안에 생성되기 때문에 가상요소의 부모는 해당요소가 된다.

## HTML

### HTML entities

[Character Entity Reference Chart](https://dev.w3.org/html5/html-author/charref)

## Git

- 개행문자 설정: `git config --global core.autocrlf true(MAC:input)`
- Reset

  `git reset --hard HEAD~1`

  `git reset --hard ORIG_HEAD` reset을 하기 전 시점으로 한번 되돌릴 수 있다.
