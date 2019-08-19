# Study_Day1

## 공부하기 앞서 개발환경 구축

- [크롬 설치](https://www.google.com/intl/ko/chrome/)
- [Visual Studio Code](https://code.visualstudio.com/)

- [Node.js 10.16.2 LTS](https://nodejs.org/ko/)

- [Vue.js dev tools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)

## Visual Studio Code Extension

- Vetur
- Night Owl
- Material Icon Theme
- Live Server
- ESLint
- Prettier
- Auto Close Tag
- Atom keymap



## Vue는 무엇인가?

- MVVM 패턴의 뷰모델(ViewModel) 레이어에 해당하는 화면(View)단 라이브러리

  ![MVVM 패턴](C:\Users\parkgiljune\Desktop\12333123.PNG)

- View
  - 브라우저에서 사람들에게 비춰지는 요소( ex : html )
  - html을 DOM이라는 것들을 이용하여 javascript로 조작을 할 수 있도록 구성되어 있음.
- ViewModel
  - View에서 특정 이벤트가 발생할 시, DOM Listeners로 중간에 청취하게 된다.
  - DOM Listeners
    - 청취한 이벤트들을 Model에서 Javascript에 있는 데이터를 바꿔주거나, Javascript로 구현한 특정로직을 수행된다.
  - Data Bindings
    -  Javascript에 데이터가 바뀌었을 때, Data Bindings를 이용해서 화면에 반영한다.