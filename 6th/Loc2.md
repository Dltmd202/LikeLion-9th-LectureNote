# 👨🏽‍💻6주차!

***

## 6.7 위치와 관련된 프로퍼티 1

***

### 6.7 .1 flexbox

​	특별한 계산없이 정렬

* 부모 요소(flex Container)

  prop

  > flex-direction
  >
  > ​	flex 컨테이너 안의 item들의 방향을 정함
  >
  > * Flex-direction: row;
  >
  >   가로로 정렬
  >
  > * Flex-direction: row-reverse;
  >
  >   가로로 반대방향부터 정렬
  >
  > * Flex-direction: column;
  >
  >   세로로 정렬
  >
  > * flex-direction: column-reverse;
  >
  >   세로로 반대방향부터 정렬
  >
  > ```html
  > <style>
  >  #container{
  >     background-color: skyblue;
  >     display: flex;
  >     flex-direction: column-reverse;
  >     height: 100px;
  >       }
  > </style>
  > ```
  >
  > 
  >
  > flex-wrap
  >
  > ​	flex 아이템의 flex 컨테이너를 벗어 났을 때 줄을 바꾸는 속성
  >
  > * flex-wrap: nowrap;
  >
  >   그냥 빠져나옴
  >
  > * Flex-wrap: wrap;
  >
  >   다음 줄로 바꾸어 줌
  >
  > ```html
  > <style>
  >  #container{
  >     background-color: skyblue;
  >     display: flex;
  >     flex-direction: column;
  >    	flex-wrap: wrap;
  >     height: 100px;
  >     width: 200px;
  >       }
  > </style>
  > ```
  >
  > justify-content
  >
  > ​	flex-direction 으로 정해진 방향을 기준으로 수평으로 item을 정렬하는 방법을 정함
  >
  > * Justify-content: flex-start;
  >
  >   (기본값)
  >
  > * Justify-content: center;
  >
  >   가운데서 시작
  >
  > * Justify-content: flex-end;
  >
  >   끝에서 시작
  >
  > * Justify-content: space-around;
  >
  >   첫 여백 부터 끝 여백까지 일정한 간격
  >
  > * Justify-content: space-between;
  >
  >   요소 간의 여백의 일정한 간격
  >
  > ```html
  > <style>
  >  #container{
  >     background-color: skyblue;
  >     display: flex;
  >     flex-direction: column;
  >    	flex-wrap: wrap;
  >     height: 100px;
  >     width: 200px;
  >       }
  > </style> 
  > ```
  >
  > 
  >
  > align-items
  >
  > ​	flex-direction으로 정해진 방향을 기준으로 수직으로 item을 정렬하는 방법을 정함
  >
  > * Align-items: stretch;
  >
  >   (기본값) 아이템을 늘려서 맞추어 줌
  >
  > * Align-items: flex-start;
  >
  >   아이템을 수직 시작 부분부터 맞추어 줌
  >
  > * Align-items: flex-end;
  >
  >   아이템을 수직 끝 부분부터 맞추어 줌
  >
  > * Align-items: center;
  >
  >   아이템을 수직 가운데 부터 맞추어  줌
  >
  > (예시는 모두 세로 정렬 기준)
  >
  > ```html
  > <style>
  >  #container{    
  >    background-color: skyblue;
  >    display: flex;
  >    flex-direction: column;
  >    flex-wrap: wrap;
  >    height: 100px;
  >    width: 200px;
  >    align-items: center;
  >       }
  > </style> 
  > ```
  >
  > align-content
  >
  > ​	flex-direction으로 정해진 방향을 기준으로 수직으로 여러 줄인 item을 정렬하는 방법을 정함
  >
  > * align-content: stretch;
  >
  >   (기본값)아이템을 늘려서 맞추어 줌
  >
  > * align-content: flex-start;
  >
  >   위부터 정렬함
  >
  > * align-content: flex-end;
  >
  >   아래부터 정렬함
  >
  > * align-content: center;
  >
  >   가운데부터 정렬함
  >
  > * Align-content: space-between;
  >
  >   위 아래 끝에 배치하고 사이 여백을 일정하게
  >
  > * Align-content: space-around;
  >
  >   모든 여백을 일정히 하여 정렬
  >
  > ```html
  > <style>
  >  #container{    
  >    background-color: skyblue;
  >    display: flex;
  >    flex-direction: column;
  >    flex-wrap: wrap;
  >    height: 100px;
  >    width: 200px;
  >    align-items: center;
  >    flex-wrap: wrap;
  >    align-content: space-between;
  >       }
  > </style> 
  > ```
  >
  > 

* 자식 요소(flex item)

  prop

  > flex-grow
  >
  > * flex 아이템의 확장과 관련된 속성, 기본 0
  > * 0일 경우 flex 컨테이너가 커져도 같이 커지지 않음
  > * 각 아이템 간의 비율
  >
  > ```html
  > <style>
  >   #one{
  >     flex-grow: 1;
  >   }
  > </style> 
  > ```
  >
  > flex-shrink
  >
  > * flex 아이템의 축소와 관련된 속성, 기본 1
  > * 0일 경우 flex 컨테이너가 작아져도 같이 작아지지 않음
  >
  > ```html
  > <style>
  >   #one{
  >     flex-shrink: 1;
  >   }
  > </style> 
  > ```
  >
  > flex-basis
  >
  > * flex 아이템의 기본 크기를 결정함, 기본 auto
  > *  수치는 단위를 꼭 필요로 함
  >
  > ```html
  > <style>
  >   #one{
  >     flex-auto: 10px;
  >   }
  > </style> 
  > ```
  >
  > Flex
  >
  > * flex-grow, flex-shrink,flex-basis의 축약형
  > * 1(On) / 0(Off)
  > * 순서로 값을 지정해 준다.
  >
  > ```html
  > <style>
  >   #one{
  >     flex: 1 0 auto;
  >   }
  > </style> 
  > ```
  >
  > 

