# ๐จ๐ฝโ๐ป6์ฃผ์ฐจ!

***

## 6.7 ์์น์ ๊ด๋ จ๋ ํ๋กํผํฐ 1

***

### 6.7 .1 flexbox

โ	ํน๋ณํ ๊ณ์ฐ์์ด ์ ๋ ฌ

* ๋ถ๋ชจ ์์(flex Container)

  prop

  > flex-direction
  >
  > โ	flex ์ปจํ์ด๋ ์์ item๋ค์ ๋ฐฉํฅ์ ์ ํจ
  >
  > * Flex-direction: row;
  >
  >   ๊ฐ๋ก๋ก ์ ๋ ฌ
  >
  > * Flex-direction: row-reverse;
  >
  >   ๊ฐ๋ก๋ก ๋ฐ๋๋ฐฉํฅ๋ถํฐ ์ ๋ ฌ
  >
  > * Flex-direction: column;
  >
  >   ์ธ๋ก๋ก ์ ๋ ฌ
  >
  > * flex-direction: column-reverse;
  >
  >   ์ธ๋ก๋ก ๋ฐ๋๋ฐฉํฅ๋ถํฐ ์ ๋ ฌ
  >
  > ```html
  > <style>
  >  #container{
  >     background-color: skyblue;
  >     display: flex;
  >     flex-direction: column-reverse;
  >     height: 100px;
  >       }
  > </style>
  > ```
  >
  > 
  >
  > flex-wrap
  >
  > โ	flex ์์ดํ์ flex ์ปจํ์ด๋๋ฅผ ๋ฒ์ด ๋ฌ์ ๋ ์ค์ ๋ฐ๊พธ๋ ์์ฑ
  >
  > * flex-wrap: nowrap;
  >
  >   ๊ทธ๋ฅ ๋น ์ ธ๋์ด
  >
  > * Flex-wrap: wrap;
  >
  >   ๋ค์ ์ค๋ก ๋ฐ๊พธ์ด ์ค
  >
  > ```html
  > <style>
  >  #container{
  >     background-color: skyblue;
  >     display: flex;
  >     flex-direction: column;
  >    	flex-wrap: wrap;
  >     height: 100px;
  >     width: 200px;
  >       }
  > </style>
  > ```
  >
  > justify-content
  >
  > โ	flex-direction ์ผ๋ก ์ ํด์ง ๋ฐฉํฅ์ ๊ธฐ์ค์ผ๋ก ์ํ์ผ๋ก item์ ์ ๋ ฌํ๋ ๋ฐฉ๋ฒ์ ์ ํจ
  >
  > * Justify-content: flex-start;
  >
  >   (๊ธฐ๋ณธ๊ฐ)
  >
  > * Justify-content: center;
  >
  >   ๊ฐ์ด๋ฐ์ ์์
  >
  > * Justify-content: flex-end;
  >
  >   ๋์์ ์์
  >
  > * Justify-content: space-around;
  >
  >   ์ฒซ ์ฌ๋ฐฑ ๋ถํฐ ๋ ์ฌ๋ฐฑ๊น์ง ์ผ์ ํ ๊ฐ๊ฒฉ
  >
  > * Justify-content: space-between;
  >
  >   ์์ ๊ฐ์ ์ฌ๋ฐฑ์ ์ผ์ ํ ๊ฐ๊ฒฉ
  >
  > ```html
  > <style>
  >  #container{
  >     background-color: skyblue;
  >     display: flex;
  >     flex-direction: column;
  >    	flex-wrap: wrap;
  >     height: 100px;
  >     width: 200px;
  >       }
  > </style> 
  > ```
  >
  > 
  >
  > align-items
  >
  > โ	flex-direction์ผ๋ก ์ ํด์ง ๋ฐฉํฅ์ ๊ธฐ์ค์ผ๋ก ์์ง์ผ๋ก item์ ์ ๋ ฌํ๋ ๋ฐฉ๋ฒ์ ์ ํจ
  >
  > * Align-items: stretch;
  >
  >   (๊ธฐ๋ณธ๊ฐ) ์์ดํ์ ๋๋ ค์ ๋ง์ถ์ด ์ค
  >
  > * Align-items: flex-start;
  >
  >   ์์ดํ์ ์์ง ์์ ๋ถ๋ถ๋ถํฐ ๋ง์ถ์ด ์ค
  >
  > * Align-items: flex-end;
  >
  >   ์์ดํ์ ์์ง ๋ ๋ถ๋ถ๋ถํฐ ๋ง์ถ์ด ์ค
  >
  > * Align-items: center;
  >
  >   ์์ดํ์ ์์ง ๊ฐ์ด๋ฐ ๋ถํฐ ๋ง์ถ์ด  ์ค
  >
  > (์์๋ ๋ชจ๋ ์ธ๋ก ์ ๋ ฌ ๊ธฐ์ค)
  >
  > ```html
  > <style>
  >  #container{    
  >    background-color: skyblue;
  >    display: flex;
  >    flex-direction: column;
  >    flex-wrap: wrap;
  >    height: 100px;
  >    width: 200px;
  >    align-items: center;
  >       }
  > </style> 
  > ```
  >
  > align-content
  >
  > โ	flex-direction์ผ๋ก ์ ํด์ง ๋ฐฉํฅ์ ๊ธฐ์ค์ผ๋ก ์์ง์ผ๋ก ์ฌ๋ฌ ์ค์ธ item์ ์ ๋ ฌํ๋ ๋ฐฉ๋ฒ์ ์ ํจ
  >
  > * align-content: stretch;
  >
  >   (๊ธฐ๋ณธ๊ฐ)์์ดํ์ ๋๋ ค์ ๋ง์ถ์ด ์ค
  >
  > * align-content: flex-start;
  >
  >   ์๋ถํฐ ์ ๋ ฌํจ
  >
  > * align-content: flex-end;
  >
  >   ์๋๋ถํฐ ์ ๋ ฌํจ
  >
  > * align-content: center;
  >
  >   ๊ฐ์ด๋ฐ๋ถํฐ ์ ๋ ฌํจ
  >
  > * Align-content: space-between;
  >
  >   ์ ์๋ ๋์ ๋ฐฐ์นํ๊ณ  ์ฌ์ด ์ฌ๋ฐฑ์ ์ผ์ ํ๊ฒ
  >
  > * Align-content: space-around;
  >
  >   ๋ชจ๋  ์ฌ๋ฐฑ์ ์ผ์ ํ ํ์ฌ ์ ๋ ฌ
  >
  > ```html
  > <style>
  >  #container{    
  >    background-color: skyblue;
  >    display: flex;
  >    flex-direction: column;
  >    flex-wrap: wrap;
  >    height: 100px;
  >    width: 200px;
  >    align-items: center;
  >    flex-wrap: wrap;
  >    align-content: space-between;
  >       }
  > </style> 
  > ```
  >
  > 

* ์์ ์์(flex item)

  prop

  > flex-grow
  >
  > * flex ์์ดํ์ ํ์ฅ๊ณผ ๊ด๋ จ๋ ์์ฑ, ๊ธฐ๋ณธ 0
  > * 0์ผ ๊ฒฝ์ฐ flex ์ปจํ์ด๋๊ฐ ์ปค์ ธ๋ ๊ฐ์ด ์ปค์ง์ง ์์
  > * ๊ฐ ์์ดํ ๊ฐ์ ๋น์จ
  >
  > ```html
  > <style>
  >   #one{
  >     flex-grow: 1;
  >   }
  > </style> 
  > ```
  >
  > flex-shrink
  >
  > * flex ์์ดํ์ ์ถ์์ ๊ด๋ จ๋ ์์ฑ, ๊ธฐ๋ณธ 1
  > * 0์ผ ๊ฒฝ์ฐ flex ์ปจํ์ด๋๊ฐ ์์์ ธ๋ ๊ฐ์ด ์์์ง์ง ์์
  >
  > ```html
  > <style>
  >   #one{
  >     flex-shrink: 1;
  >   }
  > </style> 
  > ```
  >
  > flex-basis
  >
  > * flex ์์ดํ์ ๊ธฐ๋ณธ ํฌ๊ธฐ๋ฅผ ๊ฒฐ์ ํจ, ๊ธฐ๋ณธ auto
  > *  ์์น๋ ๋จ์๋ฅผ ๊ผญ ํ์๋ก ํจ
  >
  > ```html
  > <style>
  >   #one{
  >     flex-auto: 10px;
  >   }
  > </style> 
  > ```
  >
  > Flex
  >
  > * flex-grow, flex-shrink,flex-basis์ ์ถ์ฝํ
  > * 1(On) / 0(Off)
  > * ์์๋ก ๊ฐ์ ์ง์ ํด ์ค๋ค.
  >
  > ```html
  > <style>
  >   #one{
  >     flex: 1 0 auto;
  >   }
  > </style> 
  > ```
  >
  > 

