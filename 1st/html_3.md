# 👨🏽‍💻1주차!

***

## 1.5 HTML - 3

***

### 1.5.1 form 태그

***

* form

  > 전송대상(action)

* input

  > 입력타입(type)
  >
  > 별칭(name)

* textarea

  > 행(Cols)
  >
  > 열(Rows)

```html
<form action="전송 대상">
  아이디: <input type="text" name ="id">
  비밀번호: <input type="password" name ="pw">
  <input type="submit">
</form>

<textarea cols="30" rows="20"></textarea>
```



### 1.5.2 img 태그

****

* img

  > 소스경로(src)
  >
  > 크기(height, width)

```html
<img src="./img/hello.img" width=200>
```



### 1.5.3 select 태그

***

* select

* option

  > 선택값(value)

```html
<select>
  <option value="goodday">좋은날</option>
  <option value="badday">싫은날</option>
</select>
```



###  1.5.4 ordered list 태그

***

* ol
* li

```html
<ol>
  <li>유년기</li>
  <li>질풍노도의 시기</li>
</ol>
```



### 1.5.5 a 태그

***

* a

  > 경로(href)

```html
<a href ="index.html">index</a>
```