# π¨π½βπ»6μ£Όμ°¨!

***

## 6.5 λ°μ€ λͺ¨λΈ 

***

### 6.5.1 λ°μ€ λͺ¨λΈ κ°λ

β	HTMLμ λͺ¨λ  μμλ μμννλ₯Ό κ°μ§λ€.

* λ΄μ©(Content)

  Box-sizing: content-box;

  β	width(h) = content size

  Box-sizing: border-box;

  β	width(h) = content size + border size

  

* λ§μ§(Margin)

  λ§μ§ μμ

  β	ν° λ§μ§ κ°λ§μ μ μ©ν¨

* __κ²½κ³μ (Border)__

  μ’λ₯

  * dashed
  * double
  * dotted
  * Solid

  μμ

  1. μ μ²΄
  2. μν / μ’μ°
  3. μ / μ’μ°/ ν
  4. μ / μ° / ν / μ°

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

* ν¨λ©(padding )

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

