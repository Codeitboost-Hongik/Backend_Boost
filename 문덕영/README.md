# 2주차 - 자바스크립트 기초 및 UNIX 명령어

**CLI vs GUI**

**CLI** : Command Line Interface. 터미널과 같은 검은 화면에서 커맨드 라인을 다루는 인터페이스

**GUI** : Graphical User Interface. 사용자가 마우스 등을 활용해 화면에서 작업을 진행하는 인터페이스

**Unix란?**

Unix는 Windows와 같은 운영 체제. 웹 사이트 배포 시 Unix 명령어가 많이 사용되므로, 개발자는 Unix 명령어를 알 필요가 있다. Unix 명령어를 작성하기 위한 터미널 (CLI)로는 주로 우분투를 사용하며, 우분투의 기본 shell은 bash.

**주요 Unix 명령어:**

- `pwd`: 현재 디렉토리 (working directory)의 경로를 출력
- `cd path`: path (해당 디렉토리)로 이동
- `cd ..`: 이전 디렉토리로 이동
- `ls`: 디렉토리의 목록을 확인
- `mkdir`: 디렉토리를 생성
- `touch`: 파일을 생성
- `vim`: 파일을 편집하고 싶을 때 사용. 다양한 모드 (i모드, v모드 등)를 활용하여 편집
- `cat`: 파일들의 내용을 출력
- `rm`: 파일/디렉토리를 삭제

이 명령어들은 옵션과 파라미터에 따라 세부적인 기능을 수행할 수 있다.

### 자바스크립트 기초 (내가 헷갈렸던 내용 위주 정리)

```jsx
거듭제곱 **이 곱셈 * 보다 우선순위가 높다.
문자열에서 "" 안에 " 같은 기호를 넣고 싶으면 " 앞에 \ 역슬래시를 추가
백틱 ` 을 바깥 따옴표들 대신에 사용하여 내부에 역슬래시 없이 "를 추가 가능
=== : 값의 일치, !== : 값의 불일치(일치 비교는 자동 형변환이 일어나지 않는다.)
typeof 1과 typeof 1.0 모두 num이라는 type임(정수와 소수를 구분하지 않음) - 사칙 연산자보다 우선순위가 높음
typeof 연산자의 리턴값은 문자열이다.
빈 문자나, 0, NaN을 boolean으로 형 변환하면 falsy 반환
4 + '2' 는 문자열 42가 된다. (자바스크립트의 자동 형변환 규칙)
'two' >= 1 => two가 NaN으로 변환 되어 false 반환
true와 false는 사칙연산에서 실행 시 숫자로 형이 변환된다.
console.log(`내 이름은 ${name}입니다.`) - 백틱을 활용

값을 지정하지 않으면 => undefined / 의도적으로 값을 지정하지 않은 것 => null
null == undefined : true / null === undefined : false
함수 내에 return문이 존재하고 함수 호출 이후 해당 return문을 지나면 뒤에 다른 코드가 있더라도 함수의 실행이 종료됨

console.log()와 return문의 차이 => 콘솔에 어떤 것을 출력하는 것, return은 출력이 아닌 반환만 하는 것, console.log(아무 값 반환 없다) : undefined
scope : 범위, 영역
함수 내 블록 안에 선언된 변수 : local 변수 ---> 함수 안에서만 유효한 변수
블록 밖에서 선언한 global 변수는 함수 내에서 사용 가능
상수 선언 - const (명명 규칙 : 대문자, 단어 구분은 _로)

if문은 등호 세 개로 값 비교하고 siwtch문은 자료형을 엄격하게 구분하여 비교한다는 것을 참고하자.
for문 안에 continue가 작동하면 이후 동작 없이 추가동작으로 바로 이동. while에서는 continue가 실행되면 while문으로 이동.
즉, continue는 건너띄고 싶을 때 사용
```

```jsx
// 숫자 표기법
let myNumber = 1e9  // 지수 표기법 -> 1 곱하기 10의 9승
let hex = 0xFF

// 숫자형 메소드
num.toFixed(값) // 숫자 값 자릿수 조정 메소드 => 결과는 문자열로 반환됨
num.toString(값) // 파라미터의 진법으로 숫자 변환

Math.abs(값) // 절댓값
Math.max(o, o, o, o) // 최댓값 반환 / Math.pow(2, 3) => 2의 3승
Math.round(값) // 값을 반올림 / Math.random() - 0~1 사이 랜덤

// 문자열 심화
let myName = "코드잇"

console.log(myName[2]) // 문자 반환

// 요소 탐색
console.log(myName.indexOf('드'))  // 앞부터 -> 결과 : 1(인덱스 1)
console.log(myName.lastIndexOf('코')) // 뒤부터 -> 결과 : 2

// 대소문자 변환
console.log(myName.toUpperCase())

string.trim()    // 양 끝 공백 제거

// 부분 문자열 접근
string.slice(시작, 끝)    // 시작 인데스부터 끝 인덱스 직전까지의 문자열을 리턴
string.slice()   // 문자열 전체를 가져온다.

/*
배열과 문자열의 차이
배열은 값을 수정할 수 있지만, 문자열은 수정하려면 새로 선언해야만 한다.
*/
```

```jsx
// 배열 - 자료형은 object
let array = [
  'a',
  'b',
  'c',
]

console.log(array[0])   // 인덱싱
console.log(array.length)
array.splice(시작 인덱스, 삭제할 개수, (추가할 값 입력 가능))
array.shift()   // 배열의 첫 요소 삭제
array.pop()     // 배열의 마지막 요소 삭제
array.unshift('값')   // 배열의 첫 요소로 값을 추가
array.push('값')  // 배열의 마지막 요소로 값을 추가

/*
splice, shift, pop, unshift, push 말고도 배열에는 다양한 메소드들이 있다.

배열에서 특정 값 찾기 (indexOf / lastIndexOf)

배열에서 특정 값을 찾으려면 indexOf 메소드를 사용
array.indexOf(item)을 하면 array 배열에 item이 포함되어 있는지 확인할 수 있다.
만약 포함되어 있다면, item이 있는 인덱스가 리턴
포함되어 있지 않다면, -1이 리턴
여러 번 포함되어 있으면, 처음 발견된 인덱스가 리턴

lastIndexOf : 탐색을 뒤에서 부터 시작

array.includes(item)을 하게되면 array배열에 item이 있을 경우 true를, 없을 경우 false를 리턴

reverse라는 메소드를 활용하면, 배열의 순서를 뒤집는다.

// for..of문으로 배열 요소에 접근
for (let element of array){
  console.log(element)
}

// 객체
객체{   // 객체는 참조형(주소값이 할당 된다)
  키(property name):값(property value)
}

let codeit = {
  name: "코드잇",
  'email':"@codeit.com",
  bestCourse: {
    title: "자바스크립트 초급",
    language: 'JavaScript'
  }
}

console.log(codeit.name)
console.log(codeit['email'])

// 메소드 - 객체의 고유한 동작
let greetings = {
  sayHello: function() {
    console.log("hello")
  },
  sayName: function(name) {
    console.log(`hello ${name}`)
  }
}

greetings.sayHello()
greetings.sayName(Simon)

// for..in문으로 객체를 다룸
for (let key in codeit){
  console.log(key)
  console.log(codeit[key])
}

// 자바스크립트가 미리 가지고 있는 내장 객체 - Date
// new Date('YYYY-MM-DD') or Date(YYYY, MM, DD, HH, ..) -> 주의 : M가 0이면 1월임
let myDate = new Date();

console.log(myDate.getTime());

-----------------------------------------------------------------------------------------
// 각 요소의 의미가 중요 - 객체, 의미 중요안하고 순서가 중요 - 다차원 배열
// 다차원 배열 - 배열 안에 배열
let ex = [[1,2], [3,4]]
console.log(ex[0])  // [1,2] 출력
console.log(ex[0][1])   // 2 출력

// 배열 복사
// array1 = array2.slice()

// 객체 복사
/*
let obj2 = {}

for (let key in obj1){
  obj2[key] = obj1[key]
}
return obj2
*/
```
