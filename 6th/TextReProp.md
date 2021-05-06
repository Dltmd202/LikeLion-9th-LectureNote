# 👨🏽‍💻6주차!

***

## 6.4 텍스트와 관련된 프로퍼티

***

### 6.4.1 폰트와 관련된 프로퍼티

* font-size

* font-family

  폰트의 종류를 지정

  폰트를 여러개를 지정하여 순차적으로 적용됨

  ```html
  <style>
  	font-family: ... , ... ;
  </style>
  ```

* font-style

  ```html
  <style>
  	font-style: normal;
    						italic
    						oblique
  </style>
  ```

* font-weight

  ```html
  <style>
  	font-weight: Bold;
    							100
    							200
    							...
  </style>
  ```

***

### 6.4.2 텍스트 정렬과 관련된 속성

* Text-align

```html
<style>
  h1 {
    text-align: center;
    line-height: 2;
    letter-spacing: 5px;
    text-indent: 15px;
  }
  
</style>
```

*  자기 자신을 기준으로 정렬함
* Line 간의 거리를 2로 설정한다.
* 자간을 5px로 한다.
* 들여쓰기를 15px한다.