# π¨π½βπ»6μ£Όμ°¨!

***

## 6.2 μ νμ

***

### 6.2.1 μ νμ κΈ°μ΄

β	μ€νμΌμ μ μ©νκ³ μ νλ HTML μμλ₯Ό μ ννλ μ­ν

```css
h1, p{
  color: red;
}
```

β	μ¬λ¬ κ°μ μ νμλ₯Ό μ΄μ©νμ¬ μ€νμΌμ ν λ²μ μ§μ  κ°λ₯

***

### 6.2.2 λ¨μ μ νμ

* νμ μ νμ(Type Selector)

  ν΄λΉ νκ·Έλ₯Ό κ°μ§λ λͺ¨λ  μμμ μ€νμΌμ μ μ©

```html
<style>
  p {color : red;}
  h1 {color : blue;}
</style>
```

* μμ΄λ μ νμ(Id Selector)

  Idλ‘ μ€νμΌ μ μ© ν΄λΉ Id νλμ μ μ©

  * μμ΄λ

    HTML λ¬Έμ λ΄μμ λμΌν μμ΄λλ μ‘΄μ¬ν  μ μμ λ€λ₯Έ μμμ κ΅¬λΆλλ μ μ λ§λ€μ΄μ€

```html
<stlye>
	#snow {background: yellow;}
</stlye>
```

* ν΄λμ€ μ νμ

  ν΄λμ€ μ΄λ¦μΌλ‘ μ€νμΌμ μ μ© κ°μ ν΄λμ€ μ΄λ¦μ΄λ©΄ λͺ¨λ μ μ©

  * ν΄λμ€

    λΉμ·ν νΉμ§μ κ°λ μμλ₯Ό μ§μ νμ¬ λ¬Άμ μ μμ μ¬λ¬ λ² μ¬μ©μ΄ κ°λ₯

```html
<style>
  .contents{fontsize: 24px;}
</style>
```

* μ μ²΄ μ νμ

  λͺ¨λ  μμμ μ€νμΌμ μ μ© λͺ¨λ  μμμ μ μ©νκΈ° λλ¬Έμ μλ μ ν κ°λ₯μ± μμ

```html
<style>
  * {color: red;}
</style>
```

* μμ± μ νμ

  νΉμ  μμ±μ μμ νλ λͺ¨λ  μμμ μ€νμΌμ μ μ©

```html
<style>
  a[target="_blank"] {color: red;}
</style>
```

* pseudo ν΄λμ€

  μμμ νΉλ³ν μνλ₯Ό μ§μ ν  λ μ

  - link

    λ°©λ¬Ένμ§ μμ λ§ν¬μΌ κ²½μ°

  - visited

    λ°©λ¬Έν λ§ν¬μ κ²½μ°

  - hover

    μμμ λ§μ°μ€κ° μ¬λΌμ μμ κ²½μ°

```html
<style>
  a:link {color: yellow;}
  a:visited {color: green;}
  a:hover {background: green;}
</style>
```



***

### 6.3.3 λ³΅ν© μ νμ

* μμ μ νμ

  μ νμAμ λͺ¨λ  μμ μ€ μ νμBμ μΌμΉνλ μμ μ ν

```html
<style>
  article > p {color : red;}
</style>
```

* νμ μ νμ

  μ νμAμ λͺ¨λ  νμ μ€ μ νμBμ μΌμΉνλ μμ μ ν

```html
<style>
  article p {color : blue;}
</style>
```



