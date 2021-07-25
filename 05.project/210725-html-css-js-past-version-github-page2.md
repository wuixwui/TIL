| date | title | skill |
|:---:|:---:|:---:|
| 21.07.25 | Past.version GitHub main page 2 | html css js |


---

# TIL

1. `@media`
2. use `@media` with `<link>`
3. `svg`
4. how to placed on center of the parent tag
5. When I use `&nbdp`


[Related github](https://github.com/wuixwui/github-page#readme)

---
## @media

다양한 미디어 유형이나 장치에 따라 서로 다른 스타일 규칙을 적용

>@media 미디어타입 and (미디어특성) {
CSS 코드
}

- 미디어 타입 (생략가능)
    1. **screen** 컴퓨터 화면, 타블렛, 스마트폰
    2. print 인쇄 전용
    3. all (기본값) 
    
- 미디어 특성
    1. width
    2. max-width
    3. min-width
    4. height
    5. max-height
    6. min-height
    7. orientation 뷰포트 방향
      - portrait - 세로가 더 긴 상태 
      - landscape - 가로가 더 긴 상태

---

미디어쿼리에서는 컨텐츠의 속성을 정의하는 것보다는 상태를 나타내는 것이 좋다.

### 미디어 파일 관리

`<link rel="stylesheet" media=" (max-widh: 1024px)" href="./css/main_medium.css">`

css파일을 미디어 사이즈에 따라 바꿔서 사용한다.
