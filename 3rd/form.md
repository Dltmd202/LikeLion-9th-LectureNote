# 👨🏽‍💻3주차!

***

## 3.6 폼 태그

***

### 3.6.1 form 태그

> * 폼에 포함되는 다양한 입력 양식 태그 들을 감싸준다
>
> * **action**
>
>   > 데이터를 보낼 url을 지정
>
> * **method**
>
>   > 보내는 방식을 지정
>   >
>   > 웹 브라우저에서 서버로 데이터를 보내는 방식
>   >
>   > * **get**(엽서)
>   >
>   >   > 데이터의 url 끝에 붙여 눈에 보이게 보냄
>   >   >
>   >   > 데이터 **조회** 만을 목적으로 할 때 주로 쓰임
>   >
>   > * **post**(편지)
>   >
>   >   > 메세지의 바디에 데이터를 숨겨 보냄
>   >   >
>   >   > 서버에 있는 데이터를 쓰거나 **수정, 삭제**를 위해 쓰임





***

### 3.6.2 input 태그

> 사용자에게 입력을 받기 위해 사용되는 태그, 빈 태그
>
> * 속성
>
>   >* Type(속성)
>   >
>   >  > <input>태그 종류를 결정
>   >
>   >* Name(속성)
>   >
>   >  > <input>태그 중 같은 타입과 구분되는 이름을 결정
>   >
>   >* placeholder
>   >
>   >  > <input>태그에 아무 값도 입력 되지 않았을 때 나타나는 텍스트
>
>   input 태그의 type 과 name을 key-value로 식별
>
> * label  태그
>
>   >해당 라벨을 입력시 <input> 태그 활성화
>   >
>   >* 속성
>   >
>   >  > * for
>   >  >
>   >  >   > input 태그의 아이디와 통일한다
>
> * div 태그
>
>   > 태그들을 구분하기 위해서 사용₩

```html
<form action="my-app" method="get">
  <div>
      <label for="userId">아이디 : </label>
  <input id = "userId" type="text" name="id" placeholder="아이디를 입력하세요">
  </div>
  <div>
      <label for="userPw">비밀번호 : </label>
  <input id = "userPw" type="password" name="password" placeholder="비밀번호를 입력하세요">
  </div>
</form>
```

<form action="my-app" method="get">
  <div>
      <label for="userId">아이디 : </label>
  <input id = "userId" type="text" name="id" placeholder="아이디를 입력하세요">
  </div>
  <div>
      <label for="userPw">비밀번호 : </label>
  <input id = "userPw" type="password" name="password" placeholder="비밀번호를 입력하세요">
  </div>
</form



***

### 3.6.3 select 태그

> 여러 개의 선택지를 제시하고 싶을 때 사용
>
> * 속성
>
>   >* **name**
>   >
>   >  >input의 name 과 같은 기능
>
> * option 태그
>
>   >* 속성
>   >
>   >  >* **value**
>   >  >
>   >  >  > Input 태그에서 입력되는 값과 동일
>
> *  select의 **name**과 **option**의 value가 key-value 형성

```html
<form action="my-app" method="get">
  <div>
    <label for="gender">성별 : </label>
    <select name="gender" id="gender">
      <option value="male">남성</option>
      <option value="female">여</option>
    </select>
  </div>
</form>
```

<form action="my-app" method="get">
  <div>
    <label for="gender">성별 : </label>
    <select name="gender" id="gender">
      <option value="male">남성</option>
      <option value="female">여</option>
    </select>
  </div>
</form>



***

### 3.6.3 textarea 태그

> 한 번에 많은 글을 입력받을 때 사용
>
> * 속성
>
>   >* cols rows
>   >
>   >  > 구역의 크기 설정

```html
<form action="my-app" method="get">
  <div>
    <label for="introduce">소개 : </label>
		<textarea name="introduce" id="introduce" cols="10" rows="10" placeholder="자기소개를 입력하세요"></textarea>
  </div>
</form>
```

<form action="my-app" method="get">
  <div>
    <label for="introduce">소개 : </label>
		<textarea name="introduce" id="introduce" cols="10" rows="10" placeholder="자기소개를 입력하세요"></textarea>
  </div>
</form>



***

### 3.6.4 button 태그

> <input>태그의 버튼타입과 동일하게 버튼을 생성
>
> * Html 태그를 품을 수 있어 활용이 용이하다

```html
<button type="submit">제출</button>
<button type="re">초기화</button>
```

<button type="submit">제출</button>

<button type="re">초기화</button>

