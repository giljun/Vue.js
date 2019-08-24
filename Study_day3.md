# Study_Day3

## 인스턴스 소개

- 기본 형태

  ```javascript
  var vm = new Vue({
      // app이라고 하는 이름을 가진 인스턴스를 생성한다.
  	el: "#app",
  })
  ```




## 생성자 함수

- 기본 형태

  ```javascript
  // 개발자 도구 - F12
  // 필요할때마다 가져다가 사용할 수 있다.
  function Vue() {
      this.logText = function(){
          console.log('hello');
      }
  }
  
  var vm = new Vue();
  
  vm.logText();
  // 이런 식으로 뷰 인스턴스 안에는 속성과 API와 같은 기능들이 있어서 가져다가 사용할 수 있다.
  ```



## 인스턴스 옵션 속성

- 기본 형태

  ```javascript
  new Vue({
  	el: ,
      template: ,
      data: ,
      methods: ,
      created: ,
      watch: ,
  });
  
  // 이런 식의 구성보다는
  var options = {
  	el: ,
      template: ,
      data: ,
      methods: ,
      created: ,
      watch: ,
  }
  var vm = new Vue(option);
  
  // 객체 리터럴
  // 이런 식으로 {...} 생성잔 안에 전달 인자로 객체 그자체를 넣어준다.
  // 가독성을 고려해서, 객체를 통째로 넣어준다.
  // 속성을 추가할 때, 마지막에 ,를 찍고 다음으로 구현한다.
  new Vue({
  	el: ,
      template: ,
      data: ,
      methods: ,
      created: ,
      watch: ,
  });
  ```

  