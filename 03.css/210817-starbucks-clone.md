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
new Swiper('.promotion .swiper-container', {
  direction: 'horizontal',
  slidesPerView: 3, //한번에 보여줄 슬라이드 개수
  spaceBetween: 10, //슬라이드 사이 여백
  centeredSlides: true, // 1번 슬라이드가 가운데 보이기
  autoplay: {
    // 객체를 이용해서 속성 추가 가능
    delay: 5000,
  },
  loop: true, // 끝과 끝을 연결
  pagination: {
    el: '.promotion .swiper-pagination', // 페이지 번호 요소 선택자
    clickable: true, // 사용자의 페이지 번호 요소 제어
  },
  navigation: {
    prevEl: '.promotion .swiper-prev',
    nextEl: '.promotion .swiper-next',
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

- flex item의 경우 별도의 높이가 지정되어 있지 않는 경우 최대한으로 늘어나려는 특성을 가지고 있다. `align-items:stretch`

- 확대했을 때 기준점은 요소의 왼쪽 모서리를 기준으로 잡는다.

  그렇기 때문에 확대했을 때 가운데에 위치하게 하기 위해서는 `left:50%` 로 기준점을 옮긴뒤

  `margin-left:-(해당 요소의 반 사이즈)로 가운데로 다시 옮겨주는 식으로 배치한다.

- 가로 세로의 비율을 유지하면서 사이즈를 조절하는 방법

  > `padding` `margin` 의 %는 부모 요소의 가로 사이즈를 기준으로 정해진다.

  대체로 영상을 삽입하는 경우 영상의 비율을 유지한 채 사이즈를 조절 할 때 사용한다.

  .container

  .item (`padding-top: 비율의 %값`, `height:0`)

  ```css
  .youtube .youtube__area {
    width: 1920px;
    position: absolute;
    /* 16비율 */
    left: 50%;
    margin-left: calc(1920px / -2);
    /* 9비율 */
    top: 50%;
    margin-top: calc(1920px * 9 / 16 / -2);
  }
  .youtube .youtube__area::before {
    content: '';
    display: block;
    /* 16:9 영상 비율로 요소 크기 만들기! */
    width: 100%;
    height: 0;
    padding-top: 56.25%;
  }
  ```

  .영상 (id="player")

  ```jsx
  // Youtube IFrame API를 비동기로 로드합니다.
  var tag = document.createElement('script');
  tag.src = "https://www.youtube.com/iframe_api";
  var firstScriptTag = document.getElementsByTagName('script')[0];
  firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

  // onYouTubePlayerAPIReady 함수 이름은,
  // Youtube IFrame Player API에서 사용하는 이름이기 때문에,
  // 다르게 지정하면 동작하지 않습니다!
  // 그리고 함수는 전역(Global) 등록해야 합니다!
  function onYouTubePlayerAPIReady() {
    // <div id="player"></div>
    new YT.Player('player' 선택자, {
      videoId: 'An6LvWQuj_8', // 최초 재생할 유튜브 영상 ID
      playerVars: {
        autoplay: true, // 자동 재생 유무
        loop: true, // 반복 재생 유무
        playlist: 'An6LvWQuj_8' // 반복 재생할 유튜브 영상 ID 목록
      },
      events: {
        // 영상이 준비되었을 때,
        onReady: function (event) {
          event.target.mute() // 음소거!
        }
      }
    })
  }
  ```

  videoId 보다 playlist가 우선시 되는 거 같음. 다른 영상을 더 재생하고 싶으면 배열의 형태로 추가해줌.

---

### JS

[YouTube 내장 플레이어 및 플레이어 매개변수 | YouTube IFrame Player API](https://developers.google.com/youtube/player_parameters.html?playerVersion=HTML5&hl=ko#Parameters)

```
gsap.to(요소, 시간, 옵션)
// 또는
TweenMax.to(요소, 시간, 옵션)
```

같은 기능으로 사용된다.

---

### 추가

- 커밋 컨벤션

  [[협업] 협업을 위한 git 커밋컨벤션 설정하기](https://overcome-the-limits.tistory.com/entry/%ED%98%91%EC%97%85-%ED%98%91%EC%97%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B8%B0%EB%B3%B8%EC%A0%81%EC%9D%B8-git-%EC%BB%A4%EB%B0%8B%EC%BB%A8%EB%B2%A4%EC%85%98-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0)
