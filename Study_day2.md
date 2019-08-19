# Study_Day2

## 즉시 실행 함수(Immediately-invoked function expression)

- 기본 형태

  ```javascript
  (function () {
      // statements
  })()
  ```

- 함수 표현의 경우, 함수를 정의하고 변수에 함수를 저장하고 실행하는 과정을 거칩니다.

  ```javascript
  var x = function squre(y){
  	return y * y;
  };
  ```

- 그러나, 즉시 실행 함수는 함수를 정의하고 바로 실행하여 이러한 과정을 거치지 않는 특징이 있다.

- 함수를 정의하자마자 바로 호출하는 것을 즉시 실행 함수라고 이해하면 편할 것 같다.

- 사용법

  ```javascript
  // 기명 즉시 실행 함수
  (function squre(x){
      console.log(x*x);
  })(2);
  
  (function squre(x){
      console.log(x*x);
  }(2));
  
  // 익명 즉시 실행 함수
  (function (x){
      console.log(x*x);
  })(2);
  
  (function (x){
      console.log(x*x);
  }(2));
  
  // 변수에 즉시 실행 함수 저장
  // 즉시 실행 함수도 함수이기 때문에, 변수에 즉시 실행 함수 저장이 가능합니다.
  // 재호출이 가능
  (mySquare = function(x){
      console.log(x*x);
  })(2);
  mySquare(3);
  
  // 변수에 즉시 실행 함수의 리턴값 저장도 가능합니다.
  var mySquare = (function (x){
  	return x*x;
  })(2);
  console.log(mySquare)
  ```

- 즉시 실행 함수를 사용하는 이유

  - 초기화
    - 한 번의 실행만 필요로 하는 초기화 코드 부분에 많이 사용됩니다.
    - 변수를 전역으로 선언하는 것을 피하기 위함.
    - 전역에 변수를 추가하지 않아도 되기 때문에 코드 충돌없이 구현 할 수 있다.
    - 플러그인이나 라이브러리 등을 만들 때 많이 사용됩니다.
  - 라이브러리 전역 변수의 충돌
    - jQuery나 Prototype 라이브러리는 동일한 $라는 전역 변수를 사용합니다.
    - 만약, 두 개의 라이브러리를 같이 사용한다면 $ 변수 충돌이 생기게 됩니다.
    - 즉시 실행 함수를 사용하여 $ 전역 변수의 충돌을 피할 수 있습니다.
    - 즉시 실행 함수 안에서 $는 전역변수가 아닌 jQuery object의 지역 변수가 되어, Prototype 라이브러리의 $와 충돌 없이 사용할 수 있습니다.