# 👨🏽‍💻6주차!

***

## 6.5 박스 모델 

***

### 6.5.1 박스 모델 개념

​	HTML의 모든 요소는 상자형태를 가진다.

* 내용(Content)

  Box-sizing: content-box;

  ​	width(h) = content size

  Box-sizing: border-box;

  ​	width(h) = content size + border size

  

* 마진(Margin)

  마진 상쇄

  ​	큰 마진 값만을 적용함

* __경계선(Border)__

  종류

  * dashed
  * double
  * dotted
  * Solid

  순서

  1. 전체
  2. 상하 / 좌우
  3. 상 / 좌우/ 하
  4. 상 / 우 / 하 / 우

```html
<style>
  #inner{
    border-style: dashed solid dotted double;
    border-color: red, blue, yellow, green;
    boder-width: 6px 8px, 10px, 12px;
    border: 4px solid lemonchiffon;
    
    border-radius: 12px;
    border-radius: 30px 20px 10px 0 / 0 10px 20px 30px;
    box-sizing: content-box;
    box-sizing: border-box;
  }
</style>
```

* 패딩(padding )

```html
<style>
  #inner{
    width: 200px;
    height: 100px;
    background-color: pink;
    margin: 20px;
    padding: 20px;
  }
</style>
```

