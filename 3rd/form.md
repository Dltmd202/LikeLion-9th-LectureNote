# π¨π½βπ»3μ£Όμ°¨!

***

## 3.6 νΌ νκ·Έ

***

### 3.6.1 form νκ·Έ

> * νΌμ ν¬ν¨λλ λ€μν μλ ₯ μμ νκ·Έ λ€μ κ°μΈμ€λ€
>
> * **action**
>
>   > λ°μ΄ν°λ₯Ό λ³΄λΌ urlμ μ§μ 
>
> * **method**
>
>   > λ³΄λ΄λ λ°©μμ μ§μ 
>   >
>   > μΉ λΈλΌμ°μ μμ μλ²λ‘ λ°μ΄ν°λ₯Ό λ³΄λ΄λ λ°©μ
>   >
>   > * **get**(μ½μ)
>   >
>   >   > λ°μ΄ν°μ url λμ λΆμ¬ λμ λ³΄μ΄κ² λ³΄λ
>   >   >
>   >   > λ°μ΄ν° **μ‘°ν** λ§μ λͺ©μ μΌλ‘ ν  λ μ£Όλ‘ μ°μ
>   >
>   > * **post**(νΈμ§)
>   >
>   >   > λ©μΈμ§μ λ°λμ λ°μ΄ν°λ₯Ό μ¨κ²¨ λ³΄λ
>   >   >
>   >   > μλ²μ μλ λ°μ΄ν°λ₯Ό μ°κ±°λ **μμ , μ­μ **λ₯Ό μν΄ μ°μ





***

### 3.6.2 input νκ·Έ

> μ¬μ©μμκ² μλ ₯μ λ°κΈ° μν΄ μ¬μ©λλ νκ·Έ, λΉ νκ·Έ
>
> * μμ±
>
>   >* Type(μμ±)
>   >
>   >  > <input>νκ·Έ μ’λ₯λ₯Ό κ²°μ 
>   >
>   >* Name(μμ±)
>   >
>   >  > <input>νκ·Έ μ€ κ°μ νμκ³Ό κ΅¬λΆλλ μ΄λ¦μ κ²°μ 
>   >
>   >* placeholder
>   >
>   >  > <input>νκ·Έμ μλ¬΄ κ°λ μλ ₯ λμ§ μμμ λ λνλλ νμ€νΈ
>
>   input νκ·Έμ type κ³Ό nameμ key-valueλ‘ μλ³
>
> * label  νκ·Έ
>
>   >ν΄λΉ λΌλ²¨μ μλ ₯μ <input> νκ·Έ νμ±ν
>   >
>   >* μμ±
>   >
>   >  > * for
>   >  >
>   >  >   > input νκ·Έμ μμ΄λμ ν΅μΌνλ€
>
> * div νκ·Έ
>
>   > νκ·Έλ€μ κ΅¬λΆνκΈ° μν΄μ μ¬μ©β©

```html
<form action="my-app" method="get">
  <div>
      <label for="userId">μμ΄λ : </label>
  <input id = "userId" type="text" name="id" placeholder="μμ΄λλ₯Ό μλ ₯νμΈμ">
  </div>
  <div>
      <label for="userPw">λΉλ°λ²νΈ : </label>
  <input id = "userPw" type="password" name="password" placeholder="λΉλ°λ²νΈλ₯Ό μλ ₯νμΈμ">
  </div>
</form>
```

<form action="my-app" method="get">
  <div>
      <label for="userId">μμ΄λ : </label>
  <input id = "userId" type="text" name="id" placeholder="μμ΄λλ₯Ό μλ ₯νμΈμ">
  </div>
  <div>
      <label for="userPw">λΉλ°λ²νΈ : </label>
  <input id = "userPw" type="password" name="password" placeholder="λΉλ°λ²νΈλ₯Ό μλ ₯νμΈμ">
  </div>
</form



***

### 3.6.3 select νκ·Έ

> μ¬λ¬ κ°μ μ νμ§λ₯Ό μ μνκ³  μΆμ λ μ¬μ©
>
> * μμ±
>
>   >* **name**
>   >
>   >  >inputμ name κ³Ό κ°μ κΈ°λ₯
>
> * option νκ·Έ
>
>   >* μμ±
>   >
>   >  >* **value**
>   >  >
>   >  >  > Input νκ·Έμμ μλ ₯λλ κ°κ³Ό λμΌ
>
> *  selectμ **name**κ³Ό **option**μ valueκ° key-value νμ±

```html
<form action="my-app" method="get">
  <div>
    <label for="gender">μ±λ³ : </label>
    <select name="gender" id="gender">
      <option value="male">λ¨μ±</option>
      <option value="female">μ¬</option>
    </select>
  </div>
</form>
```

<form action="my-app" method="get">
  <div>
    <label for="gender">μ±λ³ : </label>
    <select name="gender" id="gender">
      <option value="male">λ¨μ±</option>
      <option value="female">μ¬</option>
    </select>
  </div>
</form>



***

### 3.6.3 textarea νκ·Έ

> ν λ²μ λ§μ κΈμ μλ ₯λ°μ λ μ¬μ©
>
> * μμ±
>
>   >* cols rows
>   >
>   >  > κ΅¬μ­μ ν¬κΈ° μ€μ 

```html
<form action="my-app" method="get">
  <div>
    <label for="introduce">μκ° : </label>
		<textarea name="introduce" id="introduce" cols="10" rows="10" placeholder="μκΈ°μκ°λ₯Ό μλ ₯νμΈμ"></textarea>
  </div>
</form>
```

<form action="my-app" method="get">
  <div>
    <label for="introduce">μκ° : </label>
		<textarea name="introduce" id="introduce" cols="10" rows="10" placeholder="μκΈ°μκ°λ₯Ό μλ ₯νμΈμ"></textarea>
  </div>
</form>



***

### 3.6.4 button νκ·Έ

> <input>νκ·Έμ λ²νΌνμκ³Ό λμΌνκ² λ²νΌμ μμ±
>
> * Html νκ·Έλ₯Ό νμ μ μμ΄ νμ©μ΄ μ©μ΄νλ€

```html
<button type="submit">μ μΆ</button>
<button type="re">μ΄κΈ°ν</button>
```

<button type="submit">μ μΆ</button>

<button type="re">μ΄κΈ°ν</button>

