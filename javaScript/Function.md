# 자바스크립트
자바스크립트를 무작정 공부해 정확한 개념들을 놓치고 지나간것이 아닌가 문득

생각이 들어서 다시 복습하는 기분으로 문서들을 참조하면서 쓴 글입니다.
## 1. 함수
> 함수는 다른 코드에서 또는 자신에 의해 호출되거나 함수 레퍼런스를 저장한 변수에 의해 호출될 수 있는  코드조각이다. 함수가 호출될 때 함수의 입력으로 인수 가 전달되고 함수는 선택적으로 출력값을 반환할 수 있다.  또한 JavaScript에서 함수는 객체가 될 수도 있다.<br> 출처:https://developer.mozilla.org/ko/docs/Glossary/Function

### 1.1 함수 선언식
***

1. 익명 함수 선언방법
<pre>
  function () {

  }

  // ECMAScript 2015 arrow function
  () => {

  }
</pre>

2. 이름있는 함수 선언방법
<pre>
  function foo() {
    실행 값
  }

  // ECMAScript 2015 arrow function
  const foo = () => {

  }
  
</pre>

### 1.2 함수 표현식
***

유연한 자바스크립트 언어의 특징을 활용한 선언 방식

<pre>
  var test = function () {
    return "A function expression"
  };

  test(); // "A function expression"
</pre>

함수 선언식과 표현식의 차이점

**함수 선언식은 호이스팅에 영향을 받지만, 함수 표현식은 호이스팅에 영향을 받지 않는다**

> 함수 선언식은 코드의 위치와 관계없이 자바스크립트 **호이스팅**에 따라 브라우저가 자바스크립트를 해석할떄 맨 위로 끌어 올린다

예를 들어 아래의 코드를 보자

<pre>
  // 실행 전
  test();
  foo();

  function test() {
    return "Tested";
  }

  var foo = function () {
    return "foo";
  }
</pre>

<pre>
  // 실행 시
  function test() {
    return "Tested";
  }

  var foo;

  test(); "Tested"
  foo(); // Uncaught TypeError: foo is not a function

  foo = function () {
    return "foo";
  }
</pre>

> 호이스팅을 제대로 모르더라도 함수와 변수를 가급적 코드 상단부에서 선언하면,<br> 호이스팅으로 인한 스코프 꼬임 현상은 방지할 수 있다.
