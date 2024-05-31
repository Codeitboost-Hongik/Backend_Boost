# 2주차 JavaScript 기초

# 프로그래밍 시작하기

## JavaScript 소개

**JavaScript가 활용되는 곳**

- **Web 개발**
- 모바일 앱
- pc 전용 프로그램
- VR, AR
- 블록체인

## 프로그래밍 기본 개념

### 세미콜론

JS는 한 줄에 한 문장씩 작성할 경우 코드가 실행될 때 자동으로 `;`를 추가.

한 줄에 두 문장을 작성할 경우 오류 발생.

### 코멘트

컴퓨터가 인식하지 않고, 코드를 설명하기 위해 사용. 필요한 만큼만 간결하게 표현하는 것이 중요.

- `//` : 한 줄 코멘트.
- `/* */` : 여러 줄 코멘트.

### 자료형(Data type)

- **숫자** : 사칙연산 가능.
    - 정수 (Integer)
    - 소수 (floating point)
- **문자열** : `‘’`, `“”`로 감싸서 표현하는 형태. `+` 사용해서 문자열 연결 가능.
- **불린 (Boolean)** : 참(true) / 거짓(false). 조건을 나타내기 위해 사용.

### 추상화(Abstraction)

구체적인 정보는 숨기고, 꼭 필요한 **핵심만** 뽑아내서 표현하는 방식.

복잡한 것을 **목적**에 맞게 **단순화** 하는 것.

⇒ 프로그래밍에서도 추상화를 통해 코드를 작성해야 함.

### 변수(variable)

프로그래밍에서 값을 저장하는 상자 역할.

`=` → 왼쪽 피연산자에 오른쪽 피연산자를 할당한다.

```jsx
//변수 선언
let espressoPrice;
espressoPrice = 3000;

let espressoPrice = 3000;
```

**변수 이름을 짓는 방법**

1. 문자, 밑줄, $로 시작해야함.
2. 대문자와 소문자는 구별함.
3. 예약어는 사용하면 안됨.

**필수는 아니지만 지키면 좋은 룰**

1. 의미 없는 이름x.
2. 너무 추상적인 이름x.
3. camelCase로 작성.

### 함수

```jsx
// 함수 선언
function 함수이름() {
	명령;
	명령;
};

// 함수 호출
함수이름();
```

1. 내부에 작성한 코드들의 포괄적인 의미를 함수의 이름을 통해 한 번에 드러낼 수 있음.
2. 다양한 명령들을 하나로 묶어 반복해서 사용할 때 효율적임.

### 파라미터 (매개변수)

함수를 호출할 때 소괄호 안에 입력하는 값.

상황에 따라 다양한 값을 출력하도록 활용.

```jsx
function 함수이름(파라미터) {
	console.log(파라미터);
	};
	
	함수이름(값);
```

**여러개의 파라미터**

```jsx
function 함수이름(파라미터1, 파라미터2) {
	console.log(파라미터1 + 파라미터2);
	};
	
	함수이름(값);
```

### return문

함수 내부에서 정해진 명령들을 실행하고 난 뒤 함수가 실행된 자리에 특정 값을 반환.

```jsx
function getTwo() {
	return 2;
};
```

# 프로그래밍 핵심 개념

## 자료형

### 숫자형

- 사칙연산
- `%` : 나머지 연산
- `**` : 거듭제곱

JS도 일반적인 사칙연산의 우선순위를 따름!

`()`가 있으면 `()`안부터 먼저 계산.

### 문자열

글자들을 값으로 쓸 때 사용하는 자료형.

`‘’`, `“”` 로 문자열을 만들 수 있음. 반드시 같은 따옴표로 감싸줘야 함.

```jsx
console.log('I'm Iron man'); // 오류
console.log("I'm Iron man");
console.log("He said "I'm Iron man""); // 오류
console.log("He said \"I'm Iron man\""); // \를 써주면 기호로 인
console.log(`He said "I'm Iron man"`);
```

```jsx
console.log('Hello' + 'Codeit'); // HelloCodeit
console.log('3' + '5'); // 35
```

### 불 대수

일상적인 논리를 수학적으로 표현한 것.

- 불대수의 값, 진리값 → **true, false**
- 불대수의 연산 → **AND, OR NOT**
    - AND `&&` : x, y가 모두 참일 때만 참.
    - OR `||` : x, y중 하나라도 참이면 참.
    - NOT `!` : 참→거짓, 거짓→참.
    

**불린형**

```jsx
console.log(2 > 1); // true
console.log(3 <= 3); // true
console.log(3 === 3); // true
console.log(3 !== 3); // false

console.log('Codeit' === 'Codeit'); // true

console.log(true && true); // true
console.log(true || false); // true
console.log(!true); // false
```

불린 연산자가 하나만 있을 때는 연산자 기준 왼쪽부터 순서대로 확인하면 된다.

```jsx
// 불린 (Boolean)
console.log(2 < 1 && 'Codeit' !== 'Codeit');
```

### typeof 연산자

내가 지금 사용하는 값이 어떤 자료형인지 확인.

```jsx
console.log(typeof 101); // number
console.log(typeof 'Codeit'); // string
console.log(typeof '1'); // string
console.log(typeof 8-3); // NaN. typeof 우선순위가 높아 number-3을 계산하게 됨.
```

typeof 연산자는 사칙연산자보다 우선순위가 높음.

### 연산자 우선순위

| 우선순위 | 연산자 유형 | 기호 |
| --- | --- | --- |
| 21 | 그룹 | (...) |
| ... |  |  |
| 17 | 논리 NOT | ! ... |
| 17 | typeof | typeof ... |
| 16 | 거듭제곱 | ... ** ... |
| 15 | 곱셈 | ... * ... |
| 15 | 나눗셈 | ... / ... |
| 15 | 나머지 | ... % ... |
| 14 | 덧셈 | ... + ... |
| 14 | 뺄셈 | ... - ... |
| ... |  |  |
| 12 | 미만 | ... < ... |
| 12 | 이하 | ... <= ... |
| 12 | 초과 | ... > ... |
| 12 | 이상 | ... >= ... |
| 11 | 동등 | ... == ... |
| 11 | 부등 | ... != ... |
| 11 | 일치 | ... === ... |
| 11 | 불일치 | ... !== ... |
| ... |  |  |
| 6 | 논리 AND | ... && ... |
| 5 | 논리 OR | ... II ... |
| ... |  |  |
| 3 | 할당 | ... = ... |

### 형 변환

자료형을 다른 자료형으로 바꾸는 것.

```jsx
console.log(String(10) + String(5)); // Number->String 변환. 105
```

📌 Boolean값의 형변환

- Boolean값을 Number로 변환할 때 true = 1, false = 0
- 다른 값을 Boolean값으로 변환할 때 비어있는 느낌을 주는 것들이 false가 된다.
    - ex. `‘’`, `0`, `NaN` ← falsy

**자동형변환**

```jsx
console.log('4' - true); // 3
```

- **산술 연산**
    
    일반적으로 연산 되는 두 값을 모두 숫자형으로 변환함.
    
    - `+` : 한쪽이라도 문자열이라면 문자열로 변환.
    - NaN은 어떤 값과 연산하더라도 NaN
- **관계 비교 연산**
    
    일반적으로 연산 되는 두 값을 모두 숫자형으로 변환함.
    
    비교가 불가능한 경우에도 false
    
- **같음 비교 연산**
    - `==` : 동등. 형변환 O.
    - `===` : 일치. 형변환 X.
    
    ```jsx
    console.log(1 === '1'); // false
    console.log(1 == '1'); // true
    ```
    

### 템플릿 문자열

특별한 형식을 가진 문자열.

코드를 조금 더 가독성 있게, 쉽게 작성할 수 있음.

```jsx
console.log('생년월일은 '+year+'년 '+month+'월 '+day+'일 입니다.');
console.log(`생년월일은 ${year}년 ${month}월 ${day}일 입니다.`);
```

### null과 undefined

- **null** : 의도적으로 값이 없다는 것을 표현할 때. 의도적으로 없음!
- **undefined** : 코드를 실행하면서 값이 없다는 것을 확인하는 값. 처음부터 없음!

```jsx
let codeit;
console.log(codeit); // undefined 지정된 값이 없음.

codeit = null;
console.log(codeit); // null
```

## 추상화

### 할당 연산자

오른쪽에 있는 피연산자를 왼쪽에 있는 피연산자에 할당함.

```jsx
let x = 5;
x = x-2; // x의 값을 2만큼 줄여줌.
```

**복합 할당 연산자**

```jsx
// 같은 코드
x = x + 1;
x += 1;
```

**증가, 감소 연산자**

```jsx
// 같은 코드
x = x + 1;
x += 1'
x ++;
```

### 함수의 실행 순서

```jsx
function square(x) {
	return x * x;
}

console.log('함수 호출 전');
console.log(square(5)); // 파라미터로 숫자 5 전달
console.log('함수 호출 후')'

---------------
함수 호출 전
25
함수 호출 
```

### return문 제대로 이해하기

**return문의 역할**

1. 결과 값을 돌려줌
2. 함수의 **실행을 중단**함. 
    
    return문을 통해 함수 호출부에 값을 전달하고 나면 함수가 중단됨.
    

```jsx
function square(x) {
	console.log('return 전');
	return x*x;
	console.log('return 후'); // 실행되지 않음. Dead Code.
};
```

return문을 작성하지 않은 경우 함수는 undefined 값을 반환함.

**return vs console.log()**

- return : 함수를 실행하고 어떤 값을 돌려줌.
- console.log() : 콘솔에 어떤 값을 출력해줌.

### 옵셔널 파라미터

파라미터가 있는데 함수를 호출할 때 아무런 값도 전달하지 않음 → **undefined.**

undefined가 아니라 다른 값이 전달되도록 파라미터에 **기본 값을 설정**하는 방법이 옵셔널 파라미터!

```jsx
function introduce(name, age, nationality='한국') {
	...
};
```

🚨 옵셔널 파라미터는 생성한 다음 가장 뒤쪽에서 선언해 줘야 함!

```jsx
function introduce(name, nationality='한국', age){
	...
};

introduce('코드잇', 4); // nationality에 4가 전달되고, age는 undefined가 됨.
```

### 변수의 scope

변수에는 유효한 범위가 있어서 범위를 벗어나면 오류.

```jsx
function myFunction() {
	let x = 3;
	console.log(x);
};

myFunction();
console.log(x); // 오류
```

- **블록문** : `{}`로 감싼 코드.
- **로컬 변수/지역 변수** : 블록문 내에서 선언된 변수. 블록문 안에서만 사용 가능.
- **글로벌 변수/전역 변수** : 블록문 밖에서 선언한 변수. 코드를 작성한 파일 전체에서 사용 가능.

블록문 내에서 변수를 사용하게 되면 먼저 로컬 변수를 확인하고, 없을 경우에는 전역 변수를 확인함. 로컬 변수의 우선순위가 높음!

### 상수

변하지 않고, 항상 일정한 값. `const` 로 선언할 수 있음.

1. 변수명은 대문자로 적고, 두 단어 이상일 때는 _로 연결함.
2. const로 선언된 값은 값을 변경할 수 없음.
3. const로 선언할 때 값을 할당하지 않으면 오류 발생.

```jsx
const PI = 3.14;

PI = 3; // 오류.

const PI; // 오류.

const MY_NUMBER = 5;
```

## 제어문

### if문

특별한 조건에 따라서 코드의 실행 여부를 결정하는 문법.

```jsx
if (조건부분) {
	동작부분
}
```

```jsx
if (조건부분) {
	동작부분1
} else {
	동작부분2
}
```

### else if문

두 가지 이상의 옵션이 필요한 경우, else문을 중첩 할 때 보다 else if문을 사용했을 때 훨씬 간결하고 가독성이 좋음.

```jsx
if (조건1) {
	동작1
} else if (조건2) {
	동작2
} else {
	동작3
}
```

### switch문

switch문은 조건과 일치하는 경우를 찾은 다음에도 break문을 만나기 전까지 그 아래 모든 동작을 수행함.

```jsx
switch (비교할 값) {
	case 조건1:
		동작부분;
		break; // break문을 빠져나옴.
	case 조건2:
		동작부분;
		break;
	default: // 생략 가능. else랑 비슷한 역할.
		동작부분;
}
```

### if문 vs switch문

- **if문** : **범위**를 만족하는 조건식을 만들 때.
- **switch문** : **특정 값**을 만족하는 조건식을 만들 때.

if문 ↔ switch문 서로 대체가 가능하다.

switch문 → if문에서, switch문은 값을 비교할 때 자료형을 엄격하게 구분하므로 if문의 조건문에서 `===`를 사용해 일치 비교를 해야 함.

### for 반복문

조건이 충족되지 않을 때까지 계속해서 동작을 반복하는 문법.

```jsx
for (초기화부분; 조건부분; 추가동작부분) {
	동작부분
}
```

- 추가 동작 부분을 꼭 채울 필요x
- 초기화 부분에서 생성한 변수는 for문의 로컬 변수.
- 초기화 부분도 반드시 채울 필요x. 세미콜론은 꼭 2개 써줘야함!

### while 반복문

조건이 충족되지 않을 때까지 계속해서 동작을 반복하는 문법.

```jsx
while (조건부분) {
	동작부분
}
```

**for문 vs while문**

- while문은 반복 횟수를 저장할 변수를 while문 밖에서 만들어줘야 한다.
- for문은 보통 조건 비교에 사용되는 값을 반복문 내부에서만 사용한다. 외부에서 사용할 수 없다.
- while문은 카운트 하는 동작을 동작부분 안에서 작성해야 한다.

⇒ for문이 대부분의 경우 가독성이 더 좋지만, 반복문 내부 변수를 반복문이 종료돼도 사용해야 할 때는 for문보다 while문을 사용하는 것이 좋다.

### break와 continue

- **brea**k : 반복문의 조건 부분과 상관 없이 반복문을 빠져나옴.
- **continue** : 반복문의 동작 부분을 한 번 건너뜀.

# 프로그래밍과 데이터

## 객체

### 객체와 프로퍼티

**객체(object)** : 여러가지 값을 한 번에 저장.

key와 value로 이루어져 있고, key-value 한 쌍을 속성(property)이라고 부른다.

```jsx
{
	key1: value1, // key-value 한 쌍 => 속성
	key2: value2
}
```

**Property Name 주의사항**

1. 첫번째 글자는 반드시 문자, _, $중 하나로 시작.
2. 띄어쓰기 금지.
3. 하이픈(-) 금지.

사용하려면 따옴표로 감싸줘야 함!

### 객체에서 데이터 접근하기

1. 점 표기법
    
    `객체이름.프로퍼티네임`
    
    🚨 따옴표를 생략할 수 없는 프로퍼티 네임으로는 접근할 수가 없음.
    
2. 대괄호 표기법
    
    `객체이름[’프로퍼티 네임’]`
    

객체 안의 객체는?

→ 프로퍼티 네임을 계속 연결해서 접근.

`객체이름.프로퍼티네임1.프로퍼티네임2`

존재하지 않는 property에 접근하면?

→ undefined가 출력됨.

### 객체 다루기

- 객체 프로퍼티 수정하기
    
    `객체이름.프로퍼티네임 = 할당할 내용` 
    
    `객체이름[‘프로퍼티네임’] = 할당할 내용`
    
- 객체 프로퍼티 추가하기
    
    `객체이름.프로퍼티네임 = 할당할 내용` 
    
    `객체이름[‘프로퍼티네임’] = 할당할 내용`
    
    존재하지 않는 프로퍼티에 새로운 값을 할당하면 프로퍼티가 추가됨.
    
- 객체 프로퍼티 삭제하기
    
    `delete 객체이름.프로퍼티네임`
    
    `delete 객체이름[‘프로퍼티네임’]`
    
    **in 연산자**
    
    `console.log(’프로퍼티네임’ in 객체이름)`  : 프로퍼티가 객체 안에 있는지 확인 가능 (조금 더 안전하게). boolean값을 리턴.
    

### 객체와 메소드

연관성이 있는 여러 함수를 묶을 때도 객체를 사용 ⇒ 객체의 메소드.

```jsx
let greetings = {
	sayHello: function(name) {
		console.log(`Hello ${name}!`);
	},
	sayHi: function(){
		console.log('Hi!');
};

greetings.sayHello('Codeit');
greetings['sayHello']('Codeit');
```

📌 Console.log도 Console이라는 객체의 log라는 메소드임.

**메소드를 사용하는 이유?**

- 다른 함수와의 이름 중복을 피할 수 있음
- 객체에 집중해서 함수의 동작 부분을 작성할 수 있음
- 어떤 객체의 고유한 동작으로 구분할 수 있음 → 의미 있는 코드로 활용.

🚨 파라미터로 다른 변수에 담긴 값을 가져올 때는 대괄호 표기법을 사용해 주어야 한다!

### for…in 반복문

객체 안의 프로퍼티를 가지고 반복적인 동작을 수행할 때 (하나씩 다뤄야 할 때) 사용.

객체의 프로퍼티 네임이 변수에 할당되고, 객체의 프로퍼티 개수 만큼 반복 동작.

```jsx
for (변수 in 객체) {
	동작부분
}
```

```jsx
for (let key in codeit) {
	console.log(key); // 프로퍼티 네임 출력
	console.log(codeit[key]); // 프로퍼티 value값 출력
}
```

**숫자형 프로퍼티 네임**

프로퍼티 네임에는 숫자형을 사용할 수 있음. 다만 실제로 사용될 때는 문자열로 형 변환이 됨.

```jsx
let myObject = {
  300: '정수',
  1.2: '소수',
};
```

**정수형 프로퍼티 네임**

객체는 정수형 **프로퍼티 네임을 오름차순으로 먼저 정렬**하고, 나머지 프로퍼티들은 추가한 순서대로 정렬함.

```jsx
let myObject = {
  '3': '정수3',
  name: 'codeit',
  '1': '정수1',
  birthDay: '2017.5.17',
  '2': '정수2',
};

for (let key in myObject) {
  console.log(key);
}

------------------
1
2
3
name
birthDay
```

### Date 객체

JS에서 날짜는 모두 Date 객체로 다룸.

```jsx
let myDate = new Date();
let myDate = new Date(1000); // 1970년 1월 1일 00시 00분 00초에서 1000밀리초 지난 시간
let myDate = new Date('2017-05-18');
let myDate = new Date(year, month, date, hours, minutes, seconds, ms);

myDate.getTime(); // 1970 1/1 0시 0분 0초에서 몇 밀리초 지났는지 계산
myDate.getMonth(); myDate.getDate(); 등등..
myDate.getDay(); // 요일 0~6을 반환
```

- 간단하게 시간 정보 표현
    
    ```jsx
    let myDate = new Date();
    
    console.log(myDate.toLocaleDateString()); // myDate가 가진 날짜에 대한 정보 (년. 월. 일)
    console.log(myDate.toLocaleTimeString()); // myDate가 가진 시간에 대한 정보 (시:분:초)
    console.log(myDate.toLocaleString()); // myDate가 가진 날짜와 시간에 대한 정보 (년. 월. 일 시:분:초)
    ```
    

- 범위를 벗어나면 자동으로 날짜 수정
    
    ```jsx
    let myDate = new Date(1988, 0, 32); // 1988년 1월 32일은 없습니다
    
    // 2월 1일로 자동고침 되는걸 확인할 수 있습니다.
    console.log(myDate) // Mon Feb 01 1988 00:00:0
    ```
    

- `Date.now()` : 메소드가 호출된 시점의 타임 스탬프를 반환
    
    ```jsx
    let myDate = new Date();
    
    console.log(Date.now() === myDate.getTime()); // true
    ```
    

- 객체의 형변환
    
    ```jsx
    let myDate = new Date(2017, 4, 18);
    
    console.log(typeof myDate); // object
    console.log(String(myDate)); // Thu May 18 2017 00:00:00 GMT+0900 (Korean Standard Time)
    console.log(Number(myDate)); // 1495033200000
    console.log(Boolean(myDate)); // true
    
    ```
    

- Date객체끼리 사칙연산
    
    ```jsx
    let myDate1 = new Date(2017, 4, 18);
    let myDate2 = new Date(2017, 4, 19);
    
    let timeDiff = myDate2 - myDate1;
    console.log(timeDiff); // 86400000 (ms)
    console.log(timeDiff / 1000); // 86400 (sec)
    console.log(timeDiff / 1000 / 60) // 1440 (min)
    console.log(timeDiff / 1000 / 60 / 60) // 24 (hour)
    console.log(timeDiff / 1000 / 60 / 60 / 24) // 1 (date)
    ```
    

- 날짜를 표현하는 문자열
    
    ```jsx
    let date1 = new Date('12/15/1999 05:25:30');
    let date2 = new Date('December 15, 1999 05:25:30');
    let date3 = new Date('Dec 15 1999 05:25:30');
    ```
    

## 배열

**순서**가 있는 값을 담을 때는 객체보다 배열이 적합.

```jsx
let 배열이름 = [
	'요소1',
	'요소2',
	'요소3'
];
```

**인덱스** : 요소의 순서를 알려주는 숫자. (객체의 프로퍼티 네임 역할)

```jsx
console.log(배열이름[index]);
```

배열은 js에서 만들어둔 특별한 **객체** 중 하나.

### **배열 프로퍼티**

- `배열.length` : 요소의 개수.
- `배열[존재하지 않는 index] = 값 할당` : index 요소를 추가함. index 순서를 뛰어넘으면서 추가할 시 그 앞 요소는 undefined가 됨.
- `배열[index] = 값 할당` : 해당 index의 값을 수정함.

### **배열 메소드**

- `배열.splice(index)` : 해당 index부터 그 이후의 요소들을 모두 삭제함.
- `배열.splice(index, num)` : 해당 index부터 num개의 요소를 삭제함.
- `배열.splice(index, num, item)` : 요소를 삭제하고 그 자리에 item을 추가함.

- `배열.shift()` : 배열의 첫번째 요소를 삭제함.
- `배열.pop()` : 배열의 마지막 요소를 삭제함.
- `배열.unshift(value`) : 배열의 첫 요소로 값 추가함.
- `배열.push(value)` : 배열의 마지막 요소로 값 추가함.

- `배열.indexOf(item)`
    - item이 배열에 포함되어 있는 경우 item 인덱스 리턴.
    - 포함되어 있지 않은 경우 -1 리턴.
    - 여러 번 포함되어 있으면 처음 발견된 인덱스 리턴.
- `배열.lastIndexOf(item)` : `indexOf`와 같은 역할을 하되 뒤에서부터 탐색.

- `배열.includes(item)` : 배열에 item이 있을 경우 true, 없을 경우 false 리턴.

- `배열.reverse()` : 배열 순서를 뒤집음.

### for…of 반복문

```jsx
for (변수 of 배열) {
	동작부분;
}
```

### 다차원 배열

배열 안에 배열이 들어간 구조.

```jsx
let twoDimenSional = [[1,2], [3,4]];

console.log(twoDimenSional[0][1]); // 2
```

값들의 **의미**가 중요하다 ⇒ 프로퍼티 활용

값들의 **순서, 위치**가 중요하다 ⇒ 다차원 배열 활용

## 자료형 심화

### 숫자 표기법

```jsx
let millionaire = 1000000000;
let myNumber = 1e9;
```

- `num1 e num2` : e왼쪽에 있는 수에 오른쪽에 있는 수 만큼 10의 거듭제곱을 곱함.
    - 아주 큰 수나 아주 작은 수를 표기하는 방식.
- `0xff` : 16진수 표현.
- `0o377` : 8진수 표현.
- `0b11111111` : 2진수 표현.

### 숫자형 메소드

JS에서 숫자도 객체임.

- `변수.toFixed(0~100)` : 소숫점 아래의 자릿수를 고정. 소숫점 아래 num자리까지 반올림해서 표시. 부족한 자릿수는 0으로 채움.
- `변수.toString(2~36)` : 숫자를 n진법으로 표현.
    
    `숫자..toString(2~36)`, `(숫자).toString(2~36)` : 숫자 뒤에 바로 메소드를 붙일 때는 `.`을 2개 사용하거나 `()`를 씀.
    

🚨 메소드로 수정된 값은 String 형임. 숫자로 쓰고 싶다면 Number 형변환 필요. `Number()` 대신 숫자 앞에 `+` 붙여서 형변환도 가능.

### Math 객체

- Math.abs(x) : x의 절댓값 리턴.
- Math.max(여러 수) : 최댓값 리턴.
- Math.min(여러 수) : 최솟값 리턴.
- Math.pow(x, y): x의 y승 리턴.
- Math.sqrt(x) : x의 제곱근 리턴.
- Math.round(x) : x의 반올림 리턴.
- Math.floor(x) : x의 버림 리턴.
- Math.ceil(x) : x의 올림 리턴.
- Math.random() : 0이상 1미만 값 랜덤 리턴.

### JS 계산의 오차

사람과 컴퓨터 사이에 숫자 다루는 방식이 달라 컴퓨터의 계산 값에 **오차**가 있음.

ex. 무한소수의 경우 JS가 표현할 수 있는 범위에서 반올림을 함.

**해결법**

1. `toFixed` 사용해서 필요한 자릿수에 맞춰 반올림 후 숫자로 형변환.
2. 필요한 소수 자리수 만큼 10의 거듭제곱을 곱하고, `Math.round` 사용해서 계산한 다음 다시 그만큼 10으로 나눠주기.

### 문자열

문자열도 객체처럼 다룰 수 있음.

**문자열 프로퍼티**

- `문자열.length` : 문자열 길이.
- `문자열.charAt(index)` : 문자열에서 index값 문자를 가져옴.
- `문자열.indexOf(c)` : 문자열에서 c의 index를 반환. 없으면 -1.
- `문자열.lastIndexOf(c)` : 문자열에서 c를 뒤부터 찾아 index를 반환. 없으면 -1.
- `문자열.toUpperCase()` : 대문자로 바꿔줌.
- `문자열.toLowerCase()` : 소문자로 바꿔줌.
- `문자열.trim()` : 양쪽의 공백을 제거함.
- `문자열.slice(start, end)` : start index부터 end index 바로 전까지 문자열을 리턴.
    - `문자열.slice(start)` : start index부터 끝까지 문자열 리턴.
    - `문자열.slice()` : 문자열 전체를 리턴.

### 배열 vs 문자열

배열의 type은 object, 문자열의 type은 string.

- **배열 : mutable(바뀔 수 있는) 자료형**
- **문자열 : immutable(바뀔 수 없는) 자료형**

문자열은 한 번 할당된 값을 수정할 수 없음.

### 기본형과 참조형

- **기본형** : Number, String, Boolean, Null, Undefined
    
    변수에 기본형 값을 할당하면 변수에 기본형 값 자체가 저장됨.
    
- **참조형** : Object (배열도)
    
    변수에 객체 값을 할당하면 객체 값이 어딘가에서 만들어지고, 변수에는 **객체 값의 주소가 저장**됨. 주소 값을 참조해서 객체에 접근.
    
    ```jsx
    let numbers1 = [1, 2, 3];
    let numbers2 = numbers1;
    
    numbers2.push(4);
    
    console.log(numbers1); // [1, 2, 3, 4]
    ```
    

**참조형 복사하기**

```jsx
let numbers1 = [1, 2, 3];
let numbers2 = numbers1.slice(); // 배열 복사

numbers2.push(4);

console.log(numbers1); // [1, 2, 3]
```

```jsx
let course1 = {
	...
}
let course2 = Object.assign({}, course1); // 객체 복사

let course2 = {};
for (let key in course1) {
	course2[key] = course1[key];
} // 객체 복사
```

🚨 배열, 객체가 중첩되어 있는 경우 복사할 때 또 주소값이 복사됨.

### const

- **`let`** : 재할당 가능.
- **`const`** : 재할당 불가능.

**const로 변수 만드는 것이 권장**됨.

변수도 **코드가 동작하는 순간에는 상수**로 쓰이기 때문.

1. 변하는 것이 많을 수록 코드는 일관성을 유지하기 어려움. 
2. 코드 양이 많아질 때 변수가 어떤 값을 가지고 있는지 알기 어려워짐. 
3. 값이 언제 바뀔 지 모르는 불안요소.

📌 const 키워드로 변수를 선언했다고 해도 object 프로퍼티 값은 바꿀 수 있음. 변수에 저장된 ‘주소’는 그대로니까.

### var

이제는 거의 쓰이지 않음.

- 중복 선언 허용 : 똑같은 이름으로 변수를 한번 더 선언하면 에러x, 기존의 변수를 덮어씀.
    
    → 길고 복잡한 코드를 작성할 때 실수를 할 가능성이 큼.
    
- scope 문제 : 지역 변수의 구분이 함수에만 있음.
    
    → 다른 `{}` 안에서 선언한 변수가 전역 변수의 역할을 하게 될 수도 있음.
    
- Hoisting : var변수는 선언되기 이전에도 변수에 접근이 가능함.
    
    → 코드의 흐름에 방해가 될 수 있음.