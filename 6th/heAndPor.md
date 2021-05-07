# 👨🏽‍💻6주차!

***

## 6.8 상속과 우선순위

***

### 6.8.1 상속

* CSS 프로퍼티는 자식에게 상속이 된다.
* 모든 CSS 프로퍼티가 상속되는 것은 아니다.
* bgcolor, width, height 등은 상속되지 않음
* Margin: inherit; 와 같이 상속시킬 수 있다.

***

### 6.8.2 우선순위

Cascading(CSS 적용 우선순위)

* 중요도

  1. head 태그의 style 
  2. head의 style의 @import
  3. link태그의 css
  4. link태그의 css @import
  5. 브라우저 디폴트 스타일시트

* 명시도

  1. !important
  2. 인라인 스타일
  3. 아이디 선택자
  4. 클래스, 속성, 가상클래스 선택자
  5. 태그 선택자
  6. 전체 선택자
  7. 상속

* 선언순서

  나중에 선언된 스타일 우선 적용

  