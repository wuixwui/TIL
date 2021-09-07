|   date   |   title   |    skill     |
| :------: | :-------: | :----------: |
| 21.09.02 | HTML 수업 | HTML, CSS,JS |

---

# TIL

1. HTML-markup
2. CSS

---

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)

# 0907

## HTML

- 고정된 여백을 가진 % / 사이즈에 맞춘 여백 복습 필요

### 논리 해상도와 물리 해상도

> 디스플레이의 픽셀값과의 차이로 발생한다.

비트맵 이미지일 경우 스크린에 맞춘 사이즈로 받아야한다.

`<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

디스플레이의 픽셀의 수와 물리 논리해상도의 픽셀값을 맞추는 코드이다.

[8pt 그리드](https://brunch.co.kr/@monodream/29)

화면은 기기에 따라서 분기점을 나눈다.

---

### 데이터 지향적

### XML

```jsx
const menu = document.querySelector('.menu');
// 서버에 있는 json파일을 불러온다.
const url = 'https://jsonplaceholder.typicode.com/users';

const reqObj = new XMLHttpRequest();
reqObj.open('GET', url);
reqObj.responseType = 'json';
reqObj.send();
reqObj.addEventListener('load', work);

function work() {
  const tabData = reqObj.response;
  react(tabData);
}

// 데이터를 이용한 요소 관리
function react(data) {
  for (let i = 0; i < data.length; i++) {
    const menuList = document.createElement('li'); // li 만들고
    const listItem = document.createElement('a'); // a 만들고
    listItem.textContent = data[i].username; // 내용 입력하고
    menuList.appendChild(listItem); // li에 a 추가하고
    menu.appendChild(menuList); // li에 a 추가하고
  }
}
```

## CSS

브라우저의 계산이 다시 일어나는 것들은 자원의 낭비가 존재한다.

- 0831 inline 요소 어긋남 문제 이유

  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a5e322b-fc90-4924-8577-6e223c925c9c/Untitled.png)

  font마다 line-height가 다른 상황에서 vertical-align이 다른 상황에서 일어나는 문제이다.

  [http://wit.nts-corp.com/wp-content/uploads/2017/09/-12](http://wit.nts-corp.com/wp-content/uploads/2017/09/-12)

  line box는 line height가 제일 높은 부분에서 제일 낮은 부분까지의 높이를 자신의 높이로 설정하게 되는데, 이 때문에 line-box는 작은 폰트의 사용으로 인해서 오히려 높이가 높아질 수도 있다.

  저 상황에서 vertical-align이 baseline인 상태에서 a는 11px a를 감싸고 있는 li는 12px이다 그렇기 때문에 내용이 존재하지는 않지만 효과는 존재하기 때문에 line-height가 존재하며 그렇기 때문에 윗부분의 여백이 발생하게 된 것이다.

  그렇기 때문에 vertical-align을 통해서 line-box 위쪽으로 정렬해서 맞추게 된다면 line-box의 높이가 줄어들고 둘다 기준점이 위로 가기 때문에 정렬이 된 것처럼 보이게 될 것이다.

  [http://wit.nts-corp.com/wp-content/uploads/2017/09/-13](http://wit.nts-corp.com/wp-content/uploads/2017/09/-13)

  - 기본적으로 inline 요소에서 line-height를 시각적으로 나타낼 수 없다. border와 background는 content area즉 font마다 다른요소의 주변으로 생성이 됩니다.
  - line-height의 기본값은 font마다 다릅니다. line-height가 기본값일 때 line-height와 content-area는 같은 값을 가지고 있습니다.
    - line-height를 고정할 경우, line-height는 content area보다 클 수도 작을 수도 있습니다.
  - line 박스의 높이는 드래그를 통해서 알 수 있습니다.
  - content-area는 font-size가 아닙니다. font사이즈에 비례해서 생기는 공간을 포함하는 영역을 뜻합니다. (이는 font마다 다를 수가 있습니다.)

    → 그렇기에 폰트가 10px 일 때, line-height는 10px이 아닙니다.

  - vertical-align의 값 중 top과 bottom은 line-box를 기준점으로, text-top,bottom은 content-area를 기준으로 잡습니다.

    [http://wit.nts-corp.com/wp-content/uploads/2017/09/-14](http://wit.nts-corp.com/wp-content/uploads/2017/09/-14)

### Media query

media screen ans (max-width: 420px) {

}

media에 속해있는 값은 기본값으로 사용된다.

- 우선 순위 cascading

  media query로 새로운 속성을 부여할 때 우선순위를 확인해 봐야 한다.

  만약 기본값보다 우선순위가 낮은 경우 우선순위를 높여주어야 한다.

  → media query를 불러올 때 기본값에서 사용한 선택자를 그대로 사용해 주면 이러한 문제를 피할 수 있다.

## ETC
