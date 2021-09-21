# prepare_frontend_interview

## JavaScript

<b>프론트엔드 기술 면접을 위한 핸드북 만들기</b>

면접의 인터뷰어 분들이 JS의 수 많은 개념들을 순서대로 질문을 하지는 않습니다.

하지만 자바스크립트의 연관되어 있는 개념들을 순서대로 나열하고 핸드북 형식으로 보다 보면,

모르는 개념을 파악하고 한눈에 보는 것에 있어서 도움이 되지 않을까 싶어 제작하게 되었습니다.

목차는 모던 자바스크립트 deep dive를 기준으로 제작하였고 자세한 정리 내용은

[링크](https://github.com/junh0328/upgrade_javascript) 클릭 시에 해당 레포지토리에서 볼 수 있습니다.

질문에 대한 3-5줄 정도의 짧은 길이로 핵심 키워드를 체크하고 헷갈리는 용어들을 반복적으로 보게 됨으로써, 핵심 키워드를 기억할 수 있도록 만드는 것이 목표입니다!

## 목차

- [프로그래밍 🔥](#프로그래밍)
- [자바스크립트란 🔥](#자바스크립트란)
- [변수 🔥](#변수)
- [데이터 타입 🔥](#데이터-타입)
- [타입변환과 단축 평가 🔥](#타입변환과-단축-평가)
- 객체 리터럴
- 원시 값과 객체 비교
- 함수
- 스코프
- 전역 변수의 문제점
- let, const 키워드와 블록 레벨 스코프
- 생성자 함수에 의한 객체 생성
- 함수와 일급 객체
- 프로토타입
- strict mode
- 빌트인 객체
- this
- 실행 컨텍스트
- 클로저
- 클래스
- ES6 함수의 추가 기능
- 배열
- Number
- Math
- Date
- RegExp
- String
- Symbol
- 이터러블
- 스프레드(...) 문법
- 디스트럭처링 할당(구조 분해 할당)
- 브라우저 렌더링 과정
- DOM
- 이벤트
- 타이머
- 비동기 프로그래밍
- Ajax
- REST API
- Promise
- 제너레이터와 async/await
- 에러처리
- 모듈

## 프로그래밍

### 프로그래밍이란 뭐라고 생각하나요?

프로그래밍이란 컴퓨터에게 실행을 요구하는 일종의 커뮤니케이션이다.해결해야 할 문제(요구사항)를 명확히 이해한 후 적절한 문제 해결 방안을 정의할 필요가 있다.0과 1밖에 알지 못하는 기계가 실행할 수 있을 정도로 정확하고 상세하게 요구를 설명하는 작업이며, 그 결과물이 바로 코드다.

<br/>

### 컴파일러는 뭐고 인터프리터는 뭔가요?

우리가 코드를 통해 내린 명령을 수행할 주체는 컴퓨터이다. 따라서 사람이 이해할 수 있는 자연어가 아니라 컴퓨터가 이해할 수 있는 언어, 즉 기계어로 명령을 전달해야 한다.

기계어는 우리가 사용하는 언어와는 너무나도 체계가 다르기 때문에 사람이 기계어로 직접 명령을 전달하는 것은 매우 어렵다. 기계어로 직접 명령을 전달하는 것을 대신할 가장 유용한 대안은 사람이 애해할 수 있는 약속된 구문으로 구성된 프로그래밍 언어를 사용해 프로그램을 작성한 후, 그것을 컴퓨터가 이해할 수 있는 기계어로 변환하는 일종의 번역기를 이용하는 것이다.

이 일종의 번역기를 컴파일러(compiler) 혹은 인터프리터(interpreter)라고 한다.

```
compile:변환하다
interpret:해석하다
```

<br/>

## 자바스크립트란

### 자바스크립트의 특징은 뭐가 있나요?

자바스크립트는 HTML, CSS와 함께 웹을 구성하는 요소 중 하나로 웹 브라우저에서 동작하는 유일한 프로그래밍 언어다.

자바스크립트는 개발자가 별도의 컴파일 작업을 수행하지 않는 **인터프리터 언어이다.** **인터프리터는 소스코드를 즉시 실행하고** **컴파일러는 빠르게 동작하는 머신 코드를 생성하고 최적화한다.** 이를 통해 컴파일 단계에서 추가적인 시간이 필요함에도 더욱 빠르게 코드를 실행할 수 있다.

자바스크립트는 **런타임에 컴파일되며 실행 파일이 생성되지 않고 인터프리터의 도움 없이 실행할 수 없기 때문에 컴파일러 언어라고 할 수는 없다.**

<br/>

## 변수

### 변수란 무엇인가요?

변수는 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름을 말한다.

<br/>

### 식별자는 무엇인가요?

변수의 이름을 식별자(identifier)라고도 한다. 식별자는 어떤 값을 구별해서 식별할 수 있는 고유한 이름을 말한다. **식별자는 값이 아니라 메모리 주소를 기억하고 있다.**

또한 식별자라는 용어는 변수 이름에만 국한해서 사용하지 않는다. 예를 들어, 변수, 함수, 클래스 등의 이름은 모두 식별자다. 식별자인 변수 이름으로는 메모리 상에 존재하는 변수 값을 식별할 수 있고, 함수 이름으로는 메모리 상에 존재하는 함수를 식별할 수 있다. **즉, 메모리 상에 존재하는 어떤 값을 식별할 수 있는 이름은 모두 식별자라고 부른다.**

<br/>

### 변수 선언은 어떤 것을 의미하나요?

```js
var score;
```

변수 선언이란 **변수를 생성하는 것**을 말한다. 좀 더 자세히 말하면 **값을 저장하기 위한 메모리 공간을 확보하고 변수 이름과 확보된 메모리 공간의 주소를 연결해서 값을 저장할 수 있게 준비하는 것이다.** 변수를 사용하려면 반드시 선언이 필요하다. 변수를 선언할 때는 var, let, const 키워드를 사용한다.

### var 키워드는 어떤 것을 의미하나요?

var 키워드는 뒤에 오는 변수 이름을 새로운 변수를 선언할 것을 지시하는 키워드이다. 키워드는 자바스크립트 코드를 해석하고 실행하는 자바스크립트 엔진이 수행할 동작을 규정한 일종의 명령어이다. 자바스크립트 엔진은 키워드를 만나면 자신이 수행해야 할 약속된 동작을 수행한다. 예를 들어, var 키워드를 만나면 자바스크립트 엔진은 뒤에 오는 변수 이름으로 새로운 변수를 선언한다.

변수를 선언한 이후, 아직 변수에 값을 할당하지 않았다. 따라서 변수 선언에 의해 확보된 메모리 공간은 비어 있을 것으로 생각할 수 있으나 확보된 메모리 공간에는 자바스크립트 엔진에 의해 undefined라는 값이 암묵적으로 할당되어 초기화된다. 이것이 자바스크립트의 독특한 특징이다.

<br/>

### 호이스팅이 뭔가요?

```js
console.log(score); // undefined;

var score; // 변수 선언문
```

js 엔진은 변수 선언(을 포함한 모든 선언문)이 소스코드의 어디에 있든 상관없이 다른 코드보다 먼저 실행한다. 런타임 이전에 실행 컨텍스트에 의해 소스코드 평가 과정에서 스코프에 등록되고 이를 마치 코드의 제일 위에 있는 것처럼 변수가 어디에 위치하던지와 상관없이 어디서든지 변수를 참조할 수 있는 것처럼 만드는 특징을 변수 호이스팅이라고 합니다.

**사실 변수 선언뿐 아니라 var, let, const, function, function\*, class 키워드를 사용해서 선언하는 모든 식별자(변수, 함수, 클래스 등)는 호이스팅된다. 모든 선언문은 런타임 이전 단계에서 먼저 실행되기 때문이다.**

<br/>

### var 키워드와 let, const 키워드의 차이점은 어떤 것이 있고 왜 생겼나요?

var 키워드를 사용한 변수 선언은 선언 단계와 초기화 단계가 동시에 진행된다. var score;는 선언 단계를 통해 실행 컨텍스트에 변수 이름 score를 등록하고, 초기화 단계를 통해 score 변수에 암묵적으로 undefined를 할당해 초기화한다.

<br/>

### 식별자 네이밍 규칙은 어떤 것들이 있나요?

식별자는 특수문자를 제외한 문자, 숫자, 언더스코어(\_), 달러 기호($)를 포함할 수 있다.

단 식별자는 특수문자를 제외한 문자, 언더스코어(\_), 달러 기호로 시작해야 한다. 숫자로 시작하는 것은 허용하지 않는다.

<br/>

### 네이밍 컨벤션은 어떤 것들이 있나요?

```js
// 카멜 케이스 (camelCase)
var firstName;

// 스네이크 케이스 (snake_case)
var first_name;

// 파스칼 케이스 (PascalCase)
var FirstName;

// 헝가리언 케이스 (typeHungarianCase)
var strFirstName; // type + identifier
var $elem = document.getElementById("myId"); // DOM 노드
var observable$ = fromEvent(document, "click"); // RxJS 옵저버블
```

<br/>

### 리터럴이 뭔가요?

리터럴(literal)은 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법(=notation) 을 말합니다.

```
<!-- 숫자 리터럴 3 -->
3
```

위 예제의 3은 단순한 아라비아 숫자가 아니라 숫자 리터럴이다. 사람이 이해할 수 있는 아라비아 숫자를 사용해 숫자 리터럴 3을 코드에 기술하면 자바스크립트 엔진은 이를 평가해 숫자 값 3을 생성한다. 자바스크립트 엔진은 코드가 실행되는 시점인 런타임에 리터럴을 평가해 값을 생성한다.

<br/>

## 데이터 타입

### 데이터 타입에는 어떤 것들이 있나요?

|   구분    |     데이터 타입     |                        설명                         |
| :-------: | :-----------------: | :-------------------------------------------------: |
| 원시 타입 |  숫자(number)타입   | 숫자, 정수와 실수 구분 없이 하나의 숫자 타입만 존재 |
| 원시 타입 | 문자열(string)타입  |                       문자열                        |
| 원시 타입 | 불리언(boolean)타입 |            논리적 참(true)과 거짓(false)            |
| 원시 타입 |    undefined타입    |  var 키워드로 선언된 변수에 암묵적으로 할당되는 값  |
| 원시 타입 |      null 타입      |  값이 없다는 것을 의도적으로 명시할 때 사용하는 값  |
| 원시 타입 |  심벌(symbol) 타입  |              ES6에서 추가된 7번째 타입              |
| 객체 타입 |                     |                 객체, 함수, 배열 등                 |

<br/>

### 심벌 타입은 뭐죠?

심벌은 ES6에서 추가된 7번째 타입으로, 변경 불가능한 원시 타입의 값이다. 심벌 값은 다른 값과 중복되지 않는 유일무이한 값이다. 따라서 주로 이름이 충동할 위험이 없는 객체의 유일한 프로퍼티 키를 만들기 위해 사용한다.

```js
// 위, 아래, 왼쪽, 오른쪽을 나타내는 상수를 정의한다.
// 중복될 가능성이 없는 심벌 값으로 상수 값을 생성한다.
const Direction = {
  UP: Symbol("up"),
  DOWN: Symbol("down"),
  LEFT: Symbol("left"),
  RIGHT: Symbol("right"),
};

const myDirection = Direction.UP;

if (myDirection === Direction.UP) {
  console.log("You are going UP.");
}
```

<br/>

### 데이터 타입은 왜 필요할까요?

1. 값을 저장할 때 확보해야 하는 메모리 공간의 크기를 결정하기 위해
2. 값을 참조할 때 한 번에 읽어 들여야 할 메모리 공간의 크기를 결정하기 위해
3. 메모리에서 읽어 들인 2진수를 어떻게 해석할지 결정하기 위해

<br/>

### 정적 타이핑이 뭔가요?

C나 자바 같은 정적 타입언어는 변수를 선언할 때 변수에 할당할 수 있는 값의 종류, 즉 데이터 타입을 사전에 선언해야 한다. 이를 명시적 타입 선언이라 한다. 다음은 C에서 정수 타입의 변수를 선언하는 예이다.

```
// c 변수에는 1바이트 정수 타입의 값(-128 ~ 127)만을 할당할 수 있다.
char c;

// num 변수에는 4바이트 정수 타입의 값(-2,124,483,648 ~ 2,124,483,647)만을 할당할 수 있다.
int num;
```

정적 타입 언어는 변수의 타입을 변경할 수 없으며, 변수에 선언한 타입에 맞는 값만 할당할 수 있다. 정적 타입 언어는 컴파일 시점에서 타입 체크를 수행한다. 만약 타입 체크를 통과하지 못했다면 에러를 발생시키고 프로그램의 실행 자체를 막는다. 대표적인 정적 타입 언어로 C, C++, 자바, 코틀린, 고, 러스트 등이 있다.

<br/>

### 동적 타이핑이 뭔가요?

자바스크립트는 정적 타입 언어와 다르게 변수를 선언할 때 타입을 선언하지 않는다. 다만 var, let, const 키워들 사용해 변수를 선언할 뿐이다.

```js
var foo;
console.log(typeof foo); // undefined

foo = 3;
console.log(typeof foo); // number

foo = null;
console.log(typeof foo); // object

foo = Symbol(); // 심벌
console.log(typeof foo); // symbol

foo = {}; // 객체
console.log(typeof foo); // object

foo = []; // 배열
console.log(typeof foo); // object

foo = function () {}; // 함수
console.log(typeof foo); // function
```

자바스크립트의 변수는 선언이 아닌 할당에 의해 타입이 결정 **(타입 추론)**된다. 그리고 **재할당에 의해 변수의 타입은 언제든지 동적으로 변할 수 있다.** 이러한 특징을 동적 타이핑이라고 하며, 자바스크립트를 정적 타입 언어와 구별하기 위해 동적 타입 언어라고 한다. 대표적인 동적 타입 언어로는 자바스크립트, 파이썬, PHP 등이 있다.

## 타입변환과 단축 평가

<br/>

### 명시적 타입 변환이 뭔가요?

자바스크립트의 모든 값은 타입이 있다. 값의 타입은 개발자의 의도에 따라 다른 타입으로 변환할 수 있다. 개발자가 의도적으로 값의 타입을 변환하는 것을 **명시적 타입 변환 또는 타입 캐스팅**이라 한다.

```js
var x = 10;

// 숫자를 문자열로 타입 캐스팅한다.
var str = x.toString();
console.log(typeof str, str); // string 10

// x 변수의 값이 변경된 것은 아니다.
console.log(typeof x, x); // number 10
```

<br/>

### 명시적 타입 변환 함수를 예를 들어볼 수 있나요?

문자열이 아닌 값을 문자열 타입으로 변환하는 방법

1. String 생성자 함수를 new 연산자 없이 호출하는 방법
2. Object.prototype.toString 메서드를 사용하는 방법
3. 문자열 연결 연산자를 이용하는 방법

```js
// 1. String 생성자 함수를 new 연산자 없이 호출하는 방법
String(1); // -> "1"

// 2. Object.prototype.toString 메서드를 사용하는 방법
(1).toString(); // -> "1"

// 3. 문자열 연결 연산자를 이용하는 방법
1 + ""; // -> "1"
```

숫자 타입이 아닌 값을 숫자 타입으로 변환하는 방법

1. Number 생성자 함수를 new 연산자 없이 호출하는 방법
2. parseInt, parseFloat 함수를 사용하는 방법(문자열만 변환 가능)
3. `+` 단항 산술 연산자를 이용하는 방법
4. `*` 산술 연산자를 이용하는 방법

```js
// 1. Number 생성자 함수를 new 연산자 없이 호출하는 방법
Number("0"); // -> 0

// 2. parseInt, parseFloat 함수를 사용하는 방법(문자열만 변환 가능)
parseInt("0"); // -> 0

// 3. + 단항 산술 연산자를 이용하는 방법
+"0"; // -> 0

// 4. * 산술 연산자를 이용하는 방법
"0" * 1; // -> 0
```

불리언 타입이 아닌 값을 불리언 타입으로 변환하는 방법

1. Boolean 생성자 함수를 new 연산자 없이 호출하는 방법
2. ! 부정 논리 연산자를 두번 사용하는 방법

```js
// 1. Boolean 생성자 함수를 new 연산자 없이 호출하는 방법
// 문자열 타입 => 불리언 타입
Boolean("x"); // -> true
Boolean(""); // -> false
Boolean("false"); // -> true
// 숫자 타입 => 불리언 타입
Boolean(0); // -> false
Boolean(1); // -> true
Boolean(NaN); // -> false
Boolean(Infinity); // -> true
// null 타입 => 불리언 타입
Boolean(null); // -> false
// undefined 타입 => 불리언 타입
Boolean(undefined); // -> false
// 객체 타입 => 불리언 타입
Boolean({}); // -> true
Boolean([]); // -> true

// 2. ! 부정 논리 연산자를 두번 사용하는 방법
// 문자열 타입 => 불리언 타입
!!"x"; // -> true
!!""; // -> false
!!"false"; // -> true
// 숫자 타입 => 불리언 타입
!!0; // -> false
!!1; // -> true
!!NaN; // -> false
!!Infinity; // -> true
// null 타입 => 불리언 타입
!!null; // -> false
// undefined 타입 => 불리언 타입
!!undefined; // -> false
// 객체 타입 => 불리언 타입
!!{}; // -> true
!![]; // -> true
```

<br/>

### 암묵적 타입 변환이 뭔가요?

개발자의 의도와는 상관없이 표션식을 평가하는 도중에 자바스크립트 엔진에 의해 암묵적으로 타입이 자동 변환되기도 한다. 이를 **암묵적 타입 변환 또는 강제 타입 변환**이라 한다.

```js
var x = 10;

// 문자열 연결 연산자 ( + )는 숫자 타입 x의 값을 바탕으로 새로운 문자열을 생성한다.
var str = x + "";
console.log(typeof str, str); // string 10

// x 변수의 값이 변경된 것은 아니다.
console.log(typeof x, x); // number 10
```

<br/>

### truthy / falsy 한 값이 뭔가요?

자바스크립트 엔진은 불리언 타입이 아닌 값을 Truthy 값(참으로 평가되는 값) 또는 Falsy 값(거짓으로 평가되는 값)으로 구분한다. 즉, 제어문의 조건식과 같이 불리언 값으로 평가되어야 할 문맥에서 Truthy값은 true로, Falsy값은 false로 암묵적 타입 변환된다.

아래 값들은 false로 평가되는 Falsy 값이다.

```js
false
undefined
null
0, -0
NaN
' '(빈 문자열)
```

Falsy값에 ! 연산자를 붙이면, 모두 Truthy 값으로 평가되어 실행 가능해진다.

```js
// 아래의 조건문은 모두 코드 블록을 실행한다.
if (!false) console.log(false + " is falsy value");
if (!undefined) console.log(undefined + " is falsy value");
if (!null) console.log(null + " is falsy value");
if (!0) console.log(0 + " is falsy value");
if (!NaN) console.log(NaN + " is falsy value");
if (!"") console.log("" + " is falsy value");
```

## 객체 리터럴

## 원시 값과 객체 비교

## 함수

## 스코프

## 전역 변수의 문제점

## let, const 키워드와 블록 레벨 스코프

## 생성자 함수에 의한 객체 생성

## 함수와 일급 객체

## 프로토타입

## strict mode

## 빌트인 객체

## this

## 실행 컨텍스트

## 클로저

## 클래스

## ES6 함수의 추가 기능

## 배열

## Number

## Math

## Date

## RegExp

## String

## Symbol

## 이터러블

## 스프레드(...) 문법

## 디스트럭처링 할당(구조 분해 할당)

## 브라우저 렌더링 과정

## DOM

## 이벤트

## 타이머

## 비동기 프로그래밍

## Ajax

## REST API

## Promise

## 제너레이터와 async/await

## 에러처리

## 모듈