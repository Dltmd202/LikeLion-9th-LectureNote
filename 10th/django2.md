# 👨🏽‍💻10주차!

***

## 10.3 Django 실습[2]

***

### 10.3.1 앱 제작 순서

1. App을 생성
2. Teplates 제작
3. View 제작
4. URL 연결

***

### 10.3.2 test 코드

```python
#로직 구현
text = '''123123
123123
123'''

textlist = text.split()

wordDict = {}

for word in textlsit
	if word in wordDict:
   	wordDict[word] += 1
   else
  	wordDict[word] = 0
```

***

### 10.3.3 세팅

1. 가상환경 세팅
2. 장고 설치

```bash
pip install django
```

3. 앱 생성

```bash
python manage.py startapp [App]
```

4. Setting 

```python
INSTALED_APPS = [
  '~',
  '~',
  '~',
  '[App이름].apps.FirstappConfig'
]
```

5. html 파일

```html
<div>
  <h1>
    wordCount
  </h1>
  <form action="result">
    <textarea name="section" cols="60" rows="30"></textarea>
    <input type="submit" value="제출">
  </form>
</div>
```

6. view

```python
def hone(request):
  return render(
  	request,
    '~.html'
  )

def result(request):
  sentense = request.GET('sentense')
  wordlist = sentense.split()
  wordDict = {}
  
  for word in wordList:
    if word in wordDict:
      wordDict[word] += 1
     else:
      wordDict[word] = 1
	return render(
  	request,
    "result.html",{
      "fulltext": sentense,
      "count": len(wordlist),
      "wordDict":wordDict.items
    }
  )
```

7.urls

```python
import firstapp import views as first
import wordcount import views as second

urlpatterns = [
  path('hello/',first.hello, name="hello" ),
  path('wc/', wc.home, name='wc'),
  path('wc/result/', wc.result, name="result")
]
```

8. Templates(html)

```html
<div>
  <h2>
    입력한 텍스트 전문
  </h2>
  <div>
    {{fulltext}}
  </div>
  <h3>
    당신이 입력한 텍스트는 {(count)}개의 단어
  </h3>
  <div>
    {% for word, totalCount in wordCount %}
    {(word)} : {(totalCount)}
    {% endfor %}
  </div>
</div>
```

