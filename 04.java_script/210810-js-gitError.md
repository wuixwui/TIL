|    date    |    title     |  skill  |
| :--------: | :----------: | :-----: |
|  21.08.10  |  JavaScript  |   js    |

---

# TIL

1. 비구조화 할당

2. position의 위치 (z-index)

3. 문자열.repeat()

4. 배열 탐색

- array.includes(item)
- switch - case
- 객체를 이용한 검색 및 함수실행

## JS recap

- STRING `.repeat(count Num)`

    문자열 반복함수

### for of / for in

- for of

    ```jsx
    for (let number of numbers){
    	배열 안에 있는 것들을 돌릴 때 사용
    }
    ```

- Object.keys(객체) → 키를 배열로 반환
- Object.values(객체) → 값을 배열로 반환
- Objects.entries(객체) → 키와 값을 배열로[키,값] 만들어진 배열을 반환
- for in

    ```jsx
    for (let key in objsct) {
    	객체 안의 키를 꺼내와서 사용한다.
    }
    ```

---

### 배열 안 조건 탐색

- ARRAY `.includes(item)`

    array 안에 item이 있으면 true 없으면 false  

- 조건에 맞는 값 반환
    - if 문의 반복
    - switch - case

        ```jsx
        function getSomething(some) {
        	switch (some){
        	case 'some1':
        		return "some1의 경우";
        	case 'some2':
        		console.log("some2의 경우");
        		break;
        	default:
        		return "맞는 조건이 없는 경우"
        }
        }
        ```

    - 객체를 사용해서 검색

    조건에 맞는 키와 값을 가진 객체를 생성하고 인수로 받아온 값을 키로 넣어 검색한다.

    return object[somekey] key랑 맞는 || false인 경우 반환할 값

    - **객체**를 이용해서 키: 함수 형식으로 만들어서 사용할 수 있다.

    ```jsx
    function something(some) {
    const objects = {
     key1: () => {
    some이 key1일 때 실행할 코드}
    key2() {
    some이 key2일 때 실행할 코드}
    }
    const ob = object[some];

    if (!ob) {
    조건이 맞는 게 없을 경우
    return}
    마지막 실행할 수 있게 함수 호출
    ob()
    } 

    ```

---

### 비구조화 할당

```jsx
const object = {a:1,b:2};
const{a,b} = object;

console.log(a); // 1출력
```

함수에서도 비구조화 할당이 가능하다.

비구조화 할당에서도 기본값을 설정할 수 있다.

```jsx
function print({a,b =2}) {
console.log(a);
console.log(b);
}

print(object);
```

객체의 키값을 비구조화 할당으로 바꿔 줄 수도 있다.

```jsx
const { a : one } = object;

console.log(one); //1 출력
```

### 배열 비구조화 할당

```jsx
const array = [1, 2]
//array[0]처럼 인덱스에 이름을 만들어준다.
const [one, two, three = 3] = array
// 기본값 지정 가능
console.log(one); //1이 출력 
```

### 깊은 객체 비구조화 할당

```jsx
const deepObject = {
	state: {
		information: {
			name: 'maru',
			languages: ['korean', 'english', 'chinese']
		}
	}
	value: 5
}
```

state의 값인 information의 값인 객체를 꺼내오고 싶을 때는

```jsx
const {name, language} = deepObjects.state.information;
```

객체는 object[key] 혹은 object.key

---

분명 월요일도 TIL을 작성했었는데 파일도 보이지 않고 커밋도 없어서
내가 잘못 기억했나 싶었는데 오류가 발생했다.
![error](./errorimage.png)

구글링에 나오는 방법들을 다 사용해 봤는데 고쳐지지 않아서 결국 clone으로
깃헙에 있던 내용을 가져올 수 밖에 없었다..

열심히 커밋을 해야하는 이유가 생겼고
커밋을 올리고 제대로 확인해야겠다.
