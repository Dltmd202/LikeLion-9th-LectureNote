# 👨🏽‍💻6주차!

***

## 6.6 위치와 관련된 프로퍼티 1

***

### 6.6.1 display

​	요소가 보여지는 방식을 지정

​	요로에 따라 각자 다른 디스플레이값을 가짐(block, inline)

* display: block

  새로운 줄에서 시작

  width 100%

  Div / h / p / header / section

  Width, height, margin, padding 가능

* Display: inline;

  요소의 컨텐츠 크기만큼만 할당

  Width, height, margin-top, margin-bottom 불가능

* Display: line-block;

  inline의 속성을 기반으로 함

  width, height, margin-top, margin-botton 가능

* Display: none;

  브라우저에 출력이 되지 않도록 함

***

### 6.6.2 position

* postion: static;

  기본값, 좌표 프로퍼티를 쓸 수 없음

* Postion: relative;

  상대 위치, 기본 위치를 기준으로 좌표를 사용함

* Postion: absolute;

  부모나 조상 중 relative, absolute, fixed 가 선언된 곳을 기준으로 좌표 프로퍼티 적용

* Postion: fixed;

  fixed는 보이는 화면을 기준으로 좌표 프로퍼티를 이용하여 위치를 고정

* Z-index: 1;

  우선순위를 상대적으로 비교하여 위로 보내준다.