# π¨π½βπ»10μ£Όμ°¨!

## 10.3 Django μ€μ΅[2]

### 10.3.1 μ± μ μ μμ

1. Appμ μμ±
2. Teplates μ μ
3. View μ μ
4. URL μ°κ²°

### 10.3.2 test μ½λ

```python
#λ‘μ§ κ΅¬ν
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

### 10.3.3 μΈν

1. κ°μνκ²½ μΈν
2. μ₯κ³  μ€μΉ

```bash
pip install django
```

3. μ± μμ±

```bash
python manage.py startapp [App]
```

4. Setting 

```python
INSTALED_APPS = [
  '~',
  '~',
  '~',
  '[Appμ΄λ¦].apps.FirstappConfig'
]
```

5. html νμΌ

```html
<div>
  <h1>
    wordCount
  </h1>
  <form action="result">
    <textarea name="section" cols="60" rows="30"></textarea>
    <input type="submit" value="μ μΆ">
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
    μλ ₯ν νμ€νΈ μ λ¬Έ
  </h2>
  <div>
    {{fulltext}}
  </div>
  <h3>
    λΉμ μ΄ μλ ₯ν νμ€νΈλ {(count)}κ°μ λ¨μ΄
  </h3>
  <div>
    {% for word, totalCount in wordCount %}
    {(word)} : {(totalCount)}
    {% endfor %}
  </div>
</div>
```

