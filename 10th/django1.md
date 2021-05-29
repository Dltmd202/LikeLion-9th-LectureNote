# 👨🏽‍💻10주차!

***

## 10.2 Django 실습[1]

***

### 10.2.1 에러 조심

* 오타!
* 저장 안함

***

### 10.2.2 웹사이트 구동 순서

1. 사용자가 서버에 요청
2. 서버는 view는 model에게 요청한 필요한 데이터를 받음
3. view는 받은 데이터를 적절하게 처리해서 template으로 넘김
4. template은 받은 정보를 사용자에게 보여줌

***

### 10.2.3 실습

* 가상환경 설정

* App 생성

  ```bash
  python3 manage.py startapp [App이름]
  ```

  ```python
  #[프로젝트 이름]/settings.py
  INSTALED_APPS = [
    '~',
    '~',
    '~',
    '[App이름].apps.FirstappConfig'
  ]
  ```

* Templates 구성

  1. App폴더에 Templates 폴더를 만든다.

  

  2. html 파일을 만든다.

  ```html
  <div>
    <h1>
     	사용자의 이름을 입력해주세요
    </h1>
    <!----- hello는 hello함수의 name--->
    <form action='hello'>
      <label for="nameInput">이름: </label>
      <input id="nameInput" name="name">
      <input type="submit" value="제출">
    </form>
  </div>
  ```

  ```html
  <div>
    <h1>반갑습니다. {{ username }}</h1>
  </div>
  ```

  

  3. View 코드를 만든다

  ```python
  from django.shortcuts import render
  
  def welcome(request):
    return render(
    	request,
      "welcome.html"
    )
  
  def hello(request):
    username = request.GET('name')
    return render(
    	request,
      'hello.html',{
        'userName' : username 
      }
    )
  ```

  

  4.Model 코드를 만든다

  * 데이터베이스를 사용하지 않으니 수정하지 않음

  

  5.urls 코드를 만든다

  ```python
  from django.urls import path
  
  urlpatterns = [
    path('admin/', admin.site.urls),
    # 다른 html에서 name을 사용가능
    # Url은 무조건 달라야 함
    path('', views.welcome, name='welcome')
    path('hello/', views.hello, name='hello')
  ]
  ```

  

  