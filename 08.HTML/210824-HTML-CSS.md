|   date   |      title      |   skill   |
| :------: | :-------------: | :-------: |
| 21.08.24 | HTML assignment | HTML, CSS |

---

# TIL

1. HTML
2. CSS

---

## 0824

## Progammers - today

[[프로그래머스] 오늘의 문제.12](https://velog.io/@wuix/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%98%A4%EB%8A%98%EC%9D%98-%EB%AC%B8%EC%A0%9C.12)

## HTML

### line box / line-height

**→ line box의 높이 === line height**

→ **content box의 높이 === linebox의 높이 \* line의 개수**

line-height 는 정해진 폰트 사이즈를 제외한 크기를 여백으로 나눠서 배치한다. (space-evenly)

- **line-height는 더 넓은 요소로 적용**

  ~~그러나 line hight 값이 사라진 것은 아니다. (작은 값도 적용된 요소에 존재하기는 한다.)~~

  - vertical-align: top일 경우..?

    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d372d9f3-18a9-4b18-9e9c-b65593174e4c/Untitled.png)

    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a8b7ef1b-9cf3-4bd6-a0c1-87a236b62ff8/Untitled.png)

    a 요소에 vertical-align을 사용하는 것은 올바른 사용 방법이 아니다.

  ### vertical-align

  **엘리먼트의 box를 이것이 포함된 line box 내부에서 수직 정렬하고자 할 때**

  vertical-align은 오로지 inline과 table-cell 엘리먼트에만 적용

  _부모가 아닌 전체 라인에 대해,수직정렬하는 값입니다:_

  - **`top`**해당 엘리먼트의 top과 이것의 자손들의 top을 전체 라인의 top으로 정렬합니다.
  - **`bottom`**해당 엘리먼트의 bottom과 이것의 자손들의 bottom을 전체 라인의 bottom으로 정렬합니다.

box요소의 높이가 없을 시 line heights는 높이를 결정한다.(`height: auto`)

그러나 높이가 존재할 경우 높이는 height로 정해진다. (line-height <height)

inline요소안에서 border는 line-height의 높이가 아닌 inline 요소의 주변으로 생긴다.

(content의 크기에 맞춰서 border가 만들어진다.)

line-height는 드래그로 선택되는 높이 ~~아님.~~ 임

[base-line / line-height](https://codepen.io/cod-we/pen/zYzYojB)

---

### main gap의 차이

(**8과 10)**

[8pt 그리드](https://brunch.co.kr/@monodream/29)

[https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/1Gdv/image/cy25j35DVoTzV-0xYauYBYO1Es0.png](https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/1Gdv/image/cy25j35DVoTzV-0xYauYBYO1Es0.png)

## CSS

### Glassmorphism

![https://miro.medium.com/max/1200/1*neYOcbYpPcvHoX0leSjH7w.png](https://miro.medium.com/max/1200/1*neYOcbYpPcvHoX0leSjH7w.png)

> 글래스모피즘?

글래스모피즘은 배경에 블러(Blur) 효과를 준 것을 기반으로 하는 디자인으로 불투명한 유리를 통해 배경을 바라보는 느낌을 줄 수 있습니다.

```css
/* 요소 자체에 블러 효과를 준다. */
filter: blur(px)

/* 요소의 배경에 블러 효과를 준다. */
background-filter: blur(px)
```

[NWgWwoR](https://codepen.io/cod-we/pen/NWgWwoR)

### Place

그리드 또는 Flexbox의 justify,align 의 통합속성

align justify 순으로 입력한다.

- -self

  [place-self - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/place-self)

  적용하고 싶은 모든 item 요소에 적용된다.

---

- -items

  [place-items - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/place-items)

  요소들의 한줄

- -content

  [place-content - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/place-content)

  요소들의 전체

## Assignment

[https://wuixwui.github.io/temp/](https://wuixwui.github.io/temp/)
