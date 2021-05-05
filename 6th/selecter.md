# 👨🏽‍💻6주차!

***

## 6.2 선택자

***

### 6.2.1 선택자 기초

​	스타일을 적용하고자 하는 HTML 요소를 선택하는 역활

```css
h1, p{
  color: red;
}
```

​	여러 개의 선택자를 이용하여 스타일을 한 번에 지정 가능

***

### 6.2.2 단순 선택자

* 타입 선택자(Type Selector)

  해당 태그를 가지는 모든 요소에 스타일을 적용

```html
<style>
  p {color : red;}
  h1 {color : blue;}
</style>
```

* 아이디 선택자(Id Selector)

  Id로 스타일 적용 해당 Id 하나에 적용

  * 아이디

    HTML 문서 내에서 동일한 아이디는 존재할 수 없음 다른 요소와 구분되는 점을 만들어줌

```html
<stlye>
	#snow {background: yellow;}
</stlye>
```

* 클래스 선택자

  클래스 이름으로 스타일을 적용 같은 클래스 이름이면 모두 적용

  * 클래스

    비슷한 특징을 갖는 요소를 지정하여 묶을 수 있음 여러 번 사용이 가능

```html
<style>
  .contents{fontsize: 24px;}
</style>
```

* 전체 선택자

  모든 요소에 스타일을 적용 모든 요소에 적용하기 때문에 속도 저하 가능성 있음

```html
<style>
  * {color: red;}
</style>
```

* 속성 선택자

  특정 속성을 소유하는 모든 요소에 스타일을 적용

```html
<style>
  a[target="_blank"] {color: red;}
</style>
```

* pseudo 클래스

  요소의 특별한 상태를 지정할 때 씀

  - link

    방문하지 않은 링크일 경우

  - visited

    방문한 링크의 경우

  - hover

    요소에 마우스가 올라와 있을 경우

```html
<style>
  a:link {color: yellow;}
  a:visited {color: green;}
  a:hover {background: green;}
</style>
```



***

### 6.3.3 복합 선택자

* 자식 선택자

  선택자A의 모든 자식 중 선택자B와 일치하는 요소 선택

```html
<style>
  article > p {color : red;}
</style>
```

* 후손 선택자

  선택자A의 모든 후손 중 선택자B와 일치하는 요소 선택

```html
<style>
  article p {color : blue;}
</style>
```



