# π¨π½βπ»3μ£Όμ°¨!

***

## 3.5 νμ΄λΈκ³Ό λ¦¬μ€νΈ

***

### 3.5.1 νμ΄λΈμ κ΅¬μ±

> **ν**λ₯Ό μ΄μ©νμ¬ **κΉλν** λ°μ΄ν° μ λ¦¬
>
> | ν   | νλ | μ΄λ¦   |
> | ---- | ---- | ------ |
> | λ¨   | 3    | μΉν   |
> | μ¬   | 3    | κ³½λν |
>
> * table
>
>   > ν μ μ²΄λ₯Ό κ°μΈλ νκ·Έ
>
> * tr
>
>   > νμμ νμ κ΅¬λΆνλ νκ·Έ
>
> * th
>
>   > νμ ν λ΄λΆμμ μ λͺ© μμ λ΄λ νκ·Έ
>
> * td
>
>   > νμ ν λ΄λΆμ λ°μ΄ν° μμ λ΄λ νκ·Έ

* κ°λ‘ νμ΄λΈ

```html
<table>
  <tr>
    <th>μ±λ³</th>
    <th>νλ</th>
    <th>μ΄λ¦</th>
  </tr>
  <tr>
    <td>λ¨</td>
    <td>3</td>
    <td>μ΄μΉν</td>
  </tr>
    <tr>
    <td>μ¬</td>
    <td>3</td>
    <td>κ³½λν</td>
  </tr>
</table>
```



<table>
  <tr>
    <th>μ±λ³</th>
    <th>νλ</th>
    <th>μ΄λ¦</th>
  </tr>
  <tr>
    <td>λ¨</td>
    <td>3</td>
    <td>μ΄μΉν</td>
  </tr>
    <tr>
    <td>μ¬</td>
    <td>3</td>
    <td>κ³½λν</td>
  </tr>
</table>



* μΈλ‘ νμ΄λΈ

```html
<table>
  <tr>
    <th>μ±λ³</th>
    <td>λ¨</td>
    <td>μ¬</td>
  </tr>
  <tr>
    <th>νλ</th>
    <td>3</td>
    <td>3</td>
  </tr>
    <tr>
    <th>μ΄λ¦</th>
    <td>μΉν</td>
    <td>κ³½λν</td>
  </tr>
</table>
```

<table>
  <tr>
    <th>μ±λ³</th>
    <td>λ¨</td>
    <td>μ¬</td>
  </tr>
  <tr>
    <th>νλ</th>
    <td>3</td>
    <td>3</td>
  </tr>
    <tr>
    <th>μ΄λ¦</th>
    <td>μΉν</td>
    <td>κ³½λν</td>
  </tr>
</table>





* **rowspan / colspan**

  ```html
  <table>
    <tr>
      <th>νλ</th>
      <td colspan="2">3</td>
    </tr>
  </table>
  ```

<table>
  <tr>
    <th>νλ</th>
    <td colspan="2">3</td>
  </tr>
</table>

> "μ«μ" λ§νΌ μμ΄ νμ μ μ 
>
> "μ«μ" λ§νΌ μμ΄ μ΄μ μ μ 



****

### 3.5.2 λͺ©λ‘

> λͺ©λ‘ = μμ μλ λͺ©λ‘ + μμ μλ λͺ©λ‘
>
> * **μμ μλ** λͺ©λ‘(ordered list)
>
>   >```html
>   ><h3>To-do list</h3>
>   ><ol>
>   >  <li>κ³Όμ </li>
>   >  <li>μνκ³΅λΆ</li>
>   >	<li>μκ³ μΆλ€...</li>
>   ></ol>
>   >```
>   >
>   ><h3>To-do list</h3>
>   ><ol>
>   >  <li>κ³Όμ </li>
>   >  <li>μνκ³΅λΆ</li>
>   >	<li>μκ³ μΆλ€...</li>
>   ></ol>
>
>   
>
> * **μμ μλ** λͺ©λ‘(unordered list)
>
>   >```html
>   ><h3>μ₯λ³΄κΈ° λͺ©λ‘</h3>
>   ><ul>
>   >  <li>μ ν μμΉπ</li>
>   >  <li>M1 μ¬κ³  μΆλ€</li>
>   ></ul>
>   >```
>   >
>   ><h3>μ₯λ³΄κΈ° λͺ©λ‘</h3>
>   ><ul>
>   >  <li>μ ν μμΉπ</li>
>   >  <li>M1 μ¬κ³  μΆλ€</li>
>   ></ul>
>
>   
>
> * λ¦¬μ€νΈμ **νΌν©**
>
>   >```html
>   ><h3>μν λλκ³  ν  κ² λ€</h3>
>   ><ol>
>   >  <li>μ¬μ§μ°μΌλ¬ λκ°κΈ°</li>
>   >  <li>μκΈ°</li>
>   >  <li>μ₯λ³΄κΈ°</li>
>   >  <ul>
>   >    <li>μ ν μμΉ</li>
>   >    <li>λ§₯λΆ</li>
>   >  </ul>
>   ></ol>
>   >```
>   >
>   ><h3>μν λλκ³  ν  κ² λ€</h3>
>   ><ol>
>   >  <li>μ¬μ§μ°μΌλ¬ λκ°κΈ°</li>
>   >  <li>μκΈ°</li>
>   >  <li>μ₯λ³΄κΈ°</li>
>   >  <ul>
>   >    <li>μ ν μμΉ</li>
>   >    <li>λ§₯λΆ</li>
>   >  </ul>
>   ></ol>
>
> * λͺ©λ‘κ³Ό κ΄λ ¨μλ **μμ±**
>
>   >* μμκ° μλ λ¦¬μ€νΈ **(ol)**
>   >
>   >  >* start
>   >  >
>   >  >  > μ«μκ° μμνλ μκ°μ μ ν¨
>   >  >
>   >  >* type
>   >  >
>   >  >  > μμλ₯Ό μμνλ νμ
>   >  >
>   >  >* reversed
>   >  >
>   >  >  > μμλ₯Ό λ°λλ‘ μμ
>   >
>   >* μμκ° μλ λ¦¬μ€νΈ(ul)
>   >
>   >  >* reversed
>   >  >
>   >  >  > μμλ₯Ό λ°λλ‘ μμ
>   >  >
>   >  >* Value
>   >  >
>   >  >  > μμ΄νμ λ²νΈλ₯Ό μ§μ 







