# 👨🏽‍💻1주차!

***

## 1.6 Bootstrap

***

### 1.6.1 부트스트랩이란??

* *css/JavaScript* 기반 웹 프레임워크
* 오픈소스
* 반응형 웹 지원
* 브라우저와 호환

***

### 1.6.2 부트스트랩 사용준비

* 부트스트랩에 접속한다
* CDN을 가져온다
* jquery 가져오기
* 개발자모드에서 확인하기

***

### 1.6.3 부트스랩 사용하기 예시(CSS)

* container

```html
<!-- 여백만들기 -->
<div class="container">
  
</div>
```



* button

```html
<!-- 버튼꾸미기 -->
<button type="button" class="btn btn-primary">
  제출
</button>
```

***

### 1.6.4 부트스트랩 사용하기 예시(component)

* navbar

![스크린샷 2021-04-01 오전 12.56.33](/Users/mac/Library/Application Support/typora-user-images/스크린샷 2021-04-01 오전 12.56.33.png)

```html
<!-- 네비게이션 바 -->
<ul class="nav nav-tabs">
  <li role="presentation" class="active"><a href="#">Home</a></li>
  <li role="presentation"><a href="#">Profile</a></li>
  <li role="presentation"><a href="#">Messages</a></li>
</ul>
```



* prograss bar

![스크린샷 2021-04-01 오전 12.59.38](/Users/mac/Library/Application Support/typora-user-images/스크린샷 2021-04-01 오전 12.59.38.png)

```html
<div class="progress">
  <div class="progress-bar progress-bar-success progress-bar-striped" role="progressbar" aria-valuenow="40" aria-valuemin="0" aria-valuemax="100" style="width: 40%">
    <span class="sr-only">40% Complete (success)</span>
  </div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-info progress-bar-striped" role="progressbar" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">
    <span class="sr-only">20% Complete</span>
  </div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-warning progress-bar-striped" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" style="width: 60%">
    <span class="sr-only">60% Complete (warning)</span>
  </div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-danger progress-bar-striped" role="progressbar" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100" style="width: 80%">
    <span class="sr-only">80% Complete (danger)</span>
  </div>
</div>
```

