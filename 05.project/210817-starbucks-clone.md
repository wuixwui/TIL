|   date   |       title        |    skill     |
| :------: | :----------------: | :----------: |
| 21.08.17 | 스타벅스 클론 코딩 | HTML, CSS,JS |

---

# TIL

1. Swiper
2. Youtube Iframe API
3. CSS
4. Parallax Scrolling

---

# 0817

## JS library

- swiper

  [Swiper - The Most Modern Mobile Touch Slider](https://swiperjs.com/)

  swiper-container

       - swiper-wrapper

          - swiper-slide

```jsx
new Swiper(".promotion .swiper-container", {
  direction: "horizontal",
  slidesPerView: 3, //한번에 보여줄 슬라이드 개수
  spaceBetween: 10, //슬라이드 사이 여백
  centeredSlides: true, // 1번 슬라이드가 가운데 보이기
  autoplay: {
    // 객체를 이용해서 속성 추가 가능
    delay: 5000,
  },
  loop: true, // 끝과 끝을 연결
  pagination: {
    el: ".promotion .swiper-pagination", // 페이지 번호 요소 선택자
    clickable: true, // 사용자의 페이지 번호 요소 제어
  },
  navigation: {
    prevEl: ".promotion .swiper-prev",
    nextEl: ".promotion .swiper-next",
  },
});
```

---

### CSS

- `calc( )`

  CSS상에서 계산을 할 수 있는 CSS 함수

- `text-transform : uppercase`

  화면 상에서 대문자로 나타내고 싶을 때

  HTML 상에서 대문자로 전체를 적는 것보다 text-decoration: uppercase를 사용한다.

- `color: inherit`

  a 태그에 글자 색상을 상속 시키고 싶은 경우 상속을 사용한다.

- SCSS상에서 \_variables를 사용할 때 많이 사용되는 것 외에도 의미있는 단위로 사용하기도 함.

- `:not(.class)` 부정선택자 클래스 이름 지칭가능

- flex item의 경우 별도의 높이가 지정되어 있지 않는 경우 최대한으로 늘어나려는 특성을 가지고 있다. `align-items:streach`

- 확대했을 때 기준점은 요소의 왼쪽 모서리를 기준으로 잡는다.

  그렇기 때문에 확대했을 때 가운데에 위치하게 하기 위해서는 `left:50%` 로 기준점을 옮긴뒤

  `margin-left:-(해당 요소의 반 사이즈)로 가운데로 다시 옮겨주는 식으로 배치한다.

---

### JS

[YouTube IFrame Player API](https://developers.google.com/youtube/player_parameters.html?playerVersion=HTML5&hl=ko#Parameters)

---

### 추가

- 커밋 컨벤션

  [커밋 컨벤션 참고](https://overcome-the-limits.tistory.com/entry/%ED%98%91%EC%97%85-%ED%98%91%EC%97%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B8%B0%EB%B3%B8%EC%A0%81%EC%9D%B8-git-%EC%BB%A4%EB%B0%8B%EC%BB%A8%EB%B2%A4%EC%85%98-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0)

- Parallax Scrolling
  원거리 배경은 느리게 흐르고 근거리 배견은 빠르게 흐르는 형태로 입체감을 느낄 수 있게하는 애니메이션 기법
