# ๐จ๐ฝโ๐ป10์ฃผ์ฐจ!

***

## 10.2 Django ์ค์ต[1]

***

### 10.2.1 ์๋ฌ ์กฐ์ฌ

* ์คํ!
* ์ ์ฅ ์ํจ

***

### 10.2.2 ์น์ฌ์ดํธ ๊ตฌ๋ ์์

1. ์ฌ์ฉ์๊ฐ ์๋ฒ์ ์์ฒญ
2. ์๋ฒ๋ view๋ model์๊ฒ ์์ฒญํ ํ์ํ ๋ฐ์ดํฐ๋ฅผ ๋ฐ์
3. view๋ ๋ฐ์ ๋ฐ์ดํฐ๋ฅผ ์ ์ ํ๊ฒ ์ฒ๋ฆฌํด์ template์ผ๋ก ๋๊น
4. template์ ๋ฐ์ ์ ๋ณด๋ฅผ ์ฌ์ฉ์์๊ฒ ๋ณด์ฌ์ค

***

### 10.2.3 ์ค์ต

* ๊ฐ์ํ๊ฒฝ ์ค์ 

* App ์์ฑ

  ```bash
  python3 manage.py startapp [App์ด๋ฆ]
  ```

  ```python
  #[ํ๋ก์ ํธ ์ด๋ฆ]/settings.py
  INSTALED_APPS = [
    '~',
    '~',
    '~',
    '[App์ด๋ฆ].apps.FirstappConfig'
  ]
  ```

* Templates ๊ตฌ์ฑ

  1. Appํด๋์ Templates ํด๋๋ฅผ ๋ง๋ ๋ค.

  

  2. html ํ์ผ์ ๋ง๋ ๋ค.

  ```html
  <div>
    <h1>
     	์ฌ์ฉ์์ ์ด๋ฆ์ ์๋ ฅํด์ฃผ์ธ์
    </h1>
    <!----- hello๋ helloํจ์์ name--->
    <form action='hello'>
      <label for="nameInput">์ด๋ฆ: </label>
      <input id="nameInput" name="name">
      <input type="submit" value="์ ์ถ">
    </form>
  </div>
  ```

  ```html
  <div>
    <h1>๋ฐ๊ฐ์ต๋๋ค. {{ username }}</h1>
  </div>
  ```

  

  3. View ์ฝ๋๋ฅผ ๋ง๋ ๋ค

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

  

  4.Model ์ฝ๋๋ฅผ ๋ง๋ ๋ค

  * ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ฅผ ์ฌ์ฉํ์ง ์์ผ๋ ์์ ํ์ง ์์

  

  5.urls ์ฝ๋๋ฅผ ๋ง๋ ๋ค

  ```python
  from django.urls import path
  
  urlpatterns = [
    path('admin/', admin.site.urls),
    # ๋ค๋ฅธ html์์ name์ ์ฌ์ฉ๊ฐ๋ฅ
    # Url์ ๋ฌด์กฐ๊ฑด ๋ฌ๋ผ์ผ ํจ
    path('', views.welcome, name='welcome')
    path('hello/', views.hello, name='hello')
  ]
  ```

  

  