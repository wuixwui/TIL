| date | title | skill |
|:---:|:---:|:---:|
| 21.07.26 | Basic JavaScript | js |


---

# TIL

1. let, const
2. `!` not, `&&` and, `||` or
3. `+` `-` `/` `*` `%` `n++` `++n` `+=` `===` `!==`
4. function
5. object
6. array
7. for if while break, continue



## JS

### ES6 = ES2015

> ECMA Script 6

자바스크립트 문법

- Babel

### 변수

---

> let, const

이미 선언된 이름의 변수는 **재선언 할 수 없다.**

- 변수 선언 : let

변할 수 있는 데이터

```jsx
let value = 1;
```

- 상수 선언 : const

변하지 않는 데이터

```jsx
const value = 1;
```

value = 2; 처럼 재선언 하려고 하면 오류가 발생한다.

### 데이터 타입

---

- number : float int
- string : ' ' " "
- boolean : true false

 

- null : 없는 값
- undefined: 아직 정의되지 않은 값

### 연산

---

- let i = 1
    1. console.log(i++); → 1을 출력하지만 2로 변경됨

        보여준 다음에 계산

    2. console.log(++i); → 2로 변경되어 2를 출력

- 논리 연산자

    > 논리 연산자 사이에서 우선순위가 존재함. (not → and → or)

1.  not ! boolean 반전
2. and &&
3.  or ||

- 비교 연산자
    - == 데이터 타입을 무시하고 비교
    - ! = 데이터 타입 무시
    - === 데이터 타입을 확인하며 비교
    - ! == 데이터 타입 확인

### 조건문

---

> if (조건) {조건이 성립되면 실행};

```jsx
const w = 10;
if (w <= 10 || w % 5 === 0) {
	console.log(w);
}
// 10보다 작거나 같거나 또는 5로 나누어 떨어지면 w를 출력해라.
```

- `if () {}` `else if () {}` `else {}` 문

> switch / case - 특정 value에 따라 다른 작업 수행

- `switch() {case 'value': 수행할 작업 break default:}`

### 함수 Function

---

> 특정 코드들의 묶음을 하나의 명령으로 실행할 수 있게 해주는 기능

- function

    ```jsx
    function hello (name) {
    	console.log("안녕하세요 " + name);
    };

    hello('우리')
    // "안녕하세요 우리" 출력
    ```

- const *(or let) (parm)* ⇒ {code;}

### 객체 Object

---

> 하나의 이름에 여러 종류의 값을 넣을 수 있다.

```jsx
const myCat = {
	first: 'maru',
	second: 'tobi',
	third: 'muse',
// 객체 안 함
	love: function love() {
	console.log(`I love ${this.first},${this.second},${this.third}`)
	}
};

myCat.love();
```

- 객체 비구조화 할당 (=== 객체 구조 분해)

- 객체 안에 함수

- Getter, Setter

    [getter setter in ES6 :: 마이구미](https://mygumi.tistory.com/161)

    > 특정 값을 바꾸려고 하거나, 특정 값을 조회하려고 할 때 **우리가 원하는 코드를 실행**

    - getter와 setter의 이름은 같을 수 있으며 이 경우 동시 실행된다. (get → set)

    - get (조회 및 함수호출) - **return 필수**

        ```jsx
        const numbers = {
        	a: 1,
        	b: 2,
        	get sum() {
        		console.log(sum...);
        		return this.a + this.b;
        	}
        };

        console.log(numbers.sum); // →3
        // 함수를 실행하지 않고 sum을 조회만 했는데 함수가 실행되어 계산이 이루어져 있다.
        ```

    - set (조회로 **수정 및 변경** 및 함수 호출 가능) - **param 필수**

        ```jsx
        const dog = {
        	_name: '멍멍이',
        	get name() {
        		console.log('_name을 조회합니다..');
        		// name key로 _name을 호출 할 수 있게 해준다.
        		return this._name
        	},
        	set name(value) {
        		console.log('이름이 바뀝니다.')
        		this._name = value;
        	}
        };

        console.log(dog._name); // -> '멍멍이' 출력
        // 대입 연산자가 set의 param 역할을 한다.
        dog.name = "뭉뭉이"; // -> set 실행 
        console.log(dog._name); // -> '뭉뭉이' 출력
        ```

    - get과 set 같은 이름으로 사용 예

        ```jsx
        const numbers = {
        	_a: 1,
        	_b: 2,
        	sum: 0,
        	cal: function calculate() {
        		console.log('sum update..');
        		this.sum = this._a + this._b;
        	},
        // a로 _a를 호출 할 수 있게함.
        	get a() {
        		return this._a;
        	},
        	get b() {
        		return this._b;
        	},
        // _a,_b의 값이 가변할 때 함수 calculate()가 실행되어 sum의 값이 바뀜
        	set a(value) {
        		this._a = value;
        		this.cal();
        	},
        	set b(value) {
        		this._b = value;
        		this.cal();
        	}
        };

        console.log(numbers.sum); // 0
        console.log(numbers.a); // 1
        numbers.a = 3; // sum update..
        console.log(numbers.sum); // 5
        console.log(numbers.a); // 3
        console.log(numbers.b); // 2
        numbers.b = 6; // sum update..
        console.log(numbers.sum); // 9
        ```

### 배열 Array

---

> 여러 개의 항목들이 들어있는 **리스트**

<-> 객체는 한 변수 혹은 상수에 여러가지 정보를 담기 위함

- 배열 안에 객체를 넣을 수 있다.
    - 예시
- 배열 안에 배열을 넣을 수 있다.

- 배열 내장 함수 **push , length**
    - push 예시

        ```jsx
        const objects = [{ name: '멍멍이' }, { name: '야옹이' }];

        *// 새로운 항목 추가*
        objects.push({
        	name: '우리'
        });

        console.log(objects); // name: '우리'가 추가되어 있다.
        ```

    - length 예시

        ```jsx
        // 배열의 크기를 알아내는 법
        console.log(objects.length);
        ```

### 반복문 Return

---

> 특정 값에 변화를 주어가면서 우리가 정한 조건이 만족된다면 계속 반복

- for
- while

- **객체의 정보**를 **배열 형태**로 받아올 수 있는 **함수**
- for of/ for in
    - of  (보통 배열을 반복할 때는 배열의 내장함수를 사용한다.)

        > **배열에 관한 반복문**을 돌리기 위해서 만들어진 반복문

        ```jsx
        let numbers = [10, 20, 30, 40, 50];
        for (let number of numbers) {
          console.log(number);
        } 
        // 10, 20, 30, 40, 50 출력
        ```

    - in

        > 객체가 지니고 있는 값에 대하여 반복

        ```jsx
        const doggy = {
          name: '멍멍이',
          sound: '멍멍',
          age: 2
        };

        for (let key in doggy) {
          console.log(`${key}: ${doggy[key]}`);
        }
        ```

- continue, break

    ```jsx
    for (let i = 0; i < 10; i++) {
      if (i === 2) continue; // 다음 루프를 실행 - 건너뛰기
      console.log(i);
      if (i === 5) break; // 반복문을 끝내기
    }
    ```
