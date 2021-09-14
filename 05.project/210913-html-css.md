|   date   |       title        |  skill   |
| :------: | :----------------: | :------: |
| 21.09.13 | HTML - toy project | HTML, CT |

---

# TIL

1. HTML
2. CSS
3. CT

---

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)

# 0913

## HTML

[https://wuixwui.github.io/KDT_bank/](https://wuixwui.github.io/KDT_bank/)

- before 이용해서 +를 추가해보기
- swiper → 화면 추가해보기
- swiper → 리스트 넘기기
- 시계 기능 구현해보기

---

팀원분들 html css 확인해보기

### 체크리스트

- 클래스네임 확인하기
- 적절한 주석 사용
- 웹 접근성
  - 논리적 구성
  - 대체 텍스트 사용
- 구조와 표현의 분리 (닫기 버튼의 위치)
- 의미적인 태그 사용
- 플렉스를 필요 이상으로 사용한 부분이 있는지 체크
- 크로스 브라우징

## CSS

## JS

### 객체와 변수

```jsx
const woori = '123woori';
const name = {
  woori,
};
console.log(name.woori); //"123woori"
```

객체에 변수가 들어갈 경우 자동으로 변수명이 key, 값이 value가 된다.

## ETC

### 정규 표현식

- `\w` \_포함 문자,숫자포함
- `\d` 숫자
- `+` 하나이상
- `*` 0개 이상
- `?` 있거나 없거나 (있어도 되고 없어도 되고)
- `[ ]` 안에 있는 숫자나 문자를 포함하는지
  - `[a-z]` a부터 z까지
  - `[가-힣]` 한글 전체 (EUC-KR)?
- `{n}` n 번 반복
- `\s` 공백문자 (스페이스, 탭, 뉴라인)
- `\S` 공백을 제외한 문자
- `\D` 숫자를 제외한 문자
- `\W` 글자 대표 문자를 제외한 글자들 (특수문자, 공백만)

  ### JS 정규 표현식

  `/ /g` `/` 사이에 정규 표현식을 입력해줍니다.

  flag

  - `g` 는 global의 약자로 , 정규표현식과 일치하는 모든 내용을 찾아오라는 옵션
  - `i` 대소문자 구분 없이

  `String.prototype.match()`

  match() 메서드는 문자열이 정규식과 매치되는 부분을 검색

## 코딩테스트 스터디

### for → forEach → map

- for 멈추고 싶을때, break, continue 사용이 가능
- forEach 순회 → 배열을 반환하지 않기 때문에 메소드 체이닝을 하기 위해서는 새로운 배열을 생성해야한다.
- map 배열 반환
- Set () + 전개 연산자

  [JavaScript - Set](https://velog.io/@vvee1253/JavaScript-Set)

  ```
  // 교집합은 다음으로 흉내(simulate)낼 수 있음
  var intersection = new Set([...set1].filter(x => set2.has(x)));

  // 차집합은 다음으로 흉내낼 수 있음
  var difference = new Set([...set1].filter(x => !set2.has(x)));
  ```

[코딩테스트 연습 - 오픈채팅방](https://programmers.co.kr/learn/courses/30/lessons/42888)

[JavaScript - 배열 내 객체 중복 id 값 제거, js, html, css, 웹개발, 개발자, 프론트엔드, 백엔드, web](https://kyounghwan01.github.io/blog/JS/JSbasic/dupulication-property-remove/#lodash)

```jsx
function solution(record) {
  // id와 닉네임을 담고 있는 객체 생성
  const idCon = {};
  // 상태(state)에 따른 메세지와 id를 담은 배열
  const arr = [];

  // 배열 고차 함수를 이용해서 한 문장씩
  record.forEach((cur) => {
    // 공백을 기준으로 배열을 나누어 변수에 담아준다.
    // state, id, name에 각각 담긴다.
    const [state, id, name] = cur.split(' ');
    // Enter, Leave의 상태일 때만 메세지를 출력함.
    if (state !== 'Change') {
      arr.push({
        id,
        text: state === 'Enter' ? '님이 들어왔습니다.' : '님이 나갔습니다.',
      });
    }
    // Leave의 경우 이름을 표시하지 않음.
    // 새로 들어오는 경우와 채팅방 내에서 이름 수정이 있을 경우 id에 맞춰서
    // 닉네임을 갱신시켜준다.
    if (name) {
      idCon[id] = name;
    }
  });
  // 배열에 담긴 메세지를 map을 이용해서 변경 후 출력해 줍니다.
  return arr.map((item) => `${idCon[item.id]}${item.text}`);
}
```

- reduce 로 중복을 없애는 방법

[구조 분해 할당 - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

- [ ] 구조 분해 할당 제대로 공부하기

- 값 자료형 1 === 1
- 레퍼런스(주소) 자료형 [1,2] ! == [1,2]

[Map - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)

해쉬 자료 구조 → 구현 Map

- 조회, 갱신, 추가, 삭제 (Map과 Object)

- Map은 객체에 더 익숙해진 다음에 공부하자..

---

### 리엑트 JSX

- 삼항 연산자
- 고차배열은 사용가능한데 for문은 사용하지 못함.

> JS 더 파는 걸로..!

---

### 페어코딩

- 이해
  1. 문제에 대한 이해
  2. 내가 원하는 것은 무엇인가
- 계획 (test)

  > 디테일한 지시

  pseudo code로 계획 작성

- implement 실행

  코드 구현

  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/01665f31-7424-4e8d-a7ed-42ea4fcf0eee/Untitled.png)
