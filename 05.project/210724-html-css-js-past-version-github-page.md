| date | title | skill |
|:---:|:---:|:---:|
| 21.07.24 | Past.version GitHub main page | html css js |


---

# TIL

1. BEM
2. Vender prefix
3. Gloval property

[Related github](https://github.com/wuixwui/github-page#readme)

## BPM



> CSS 작명규칙

- `A__B` -> A의 일부분인 B
- `btn--상태` -> btn의 상태 (ex `btn--danger` = 경고 버튼)
- `A-B` -> 일반적인 작명



## Vender prefix


- 브라우저 업체별 접두사

    주요 웹 브라우저 공급자가 새로운 실험적인 기능을 제공할 때 이전 버전의 웹 브라우저에 그 사실을 알려주기 위해 사용하는 접두사(prefix)

    아직 CSS 권고안에 포함되지 못한 기능이나, CSS 권고안에는 포함되어 있지만 아직 완벽하게 제정된 상태가 아닌 기능을 사용하고자 할 때 벤더 프리픽스를 사용하게 됩니다.

    이러한 벤더 프리픽스는 실험적인 해당 기능들이 CSS 표준 권고 안에 포함되거나, 완벽하게 제정된 상태가 되면 더는 사용할 필요가 없어집니다.

[Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/)

|  웹 브라우저 마다 사용 가능한 태그 및 속성을 알아보는 사이트

- 브라우저 업체별 접두사

`-webkit-`: chrome

`-ms-`: IE, edge

`-moz-`: firefox

### 예제

```css
<style>

.button {

background: red;          
<!-- gradient 속성을 지원하지 않는 모든 브라우저를 위한 코드 -->

background: -webkit-linear-gradient(red, yellow); 
<!-- 크롬과 사파리 이상을 위한 코드 -->

background: -moz-linear-gradient(red, yellow);    
<!-- 파이어폭스 이상을 위한 코드 -->

background: -ms-linear-gradient(red, yellow);     
<!-- 익스플로러 이상을 위한 코드 -->

background: -o-linear-gradient(red, yellow);      
<!-- 오페라 이상을 위한 코드 -->

background: linear-gradient(red, yellow);         
<!-- CSS 표준 문법 코드 -->

}

</style>
```

CSS 표준 문법 코드는 벤더 프리픽스(vendor prefix)로 작성된 코드가 모두 나오고 난 후에 나와야만, 벤더 프리픽스가 포함된 코드가 정상적으로 동작할 수 있습니다.

→ 혹은 SASS와 같은 컴파일러를 사용하는 방법
