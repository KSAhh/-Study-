
### PK  
- Primary Key  
- 데이터 구분자 / 모델에서 찍어낸 수많은 객체들을 구분 / 이름표  

### path-converter  
- 여러 객체 다루는 계층적 url이 필요할 경우 / url계층적 디자인  
- 형식: `<type:name>`  

- - -  
- - -  

# 실습

### error 띄우기 - html끼리 연결하면서 data공유하기  
- 과정  
1. PK : n번째 블로그 객체 / 게시글 id  
2. path Converter : 사이트/blog/객체번호(n)  
3. get_object_or_404 : object 가져오고, 없으면 404 에러 띄우는 함수  
```python
    1. 프로젝트 폴더 내 urls.py
        urlpatterns = [
            path('blog/<int:blog_id>', Blog.views.detail, name="detail"),               # <int:blog_id> : 각 게시물의 id값이 들어갈 공간 / path-converter
        ]

    2. app내 views.py
       from django.shortcuts import render, get_object_or_404
       from .models import Blog
       def detail(request, blog_id):
           blog_detail = get_object_or_404(Blog, pk=blog_id)                       # get_object_or_404(Class, PK="")
           return render(request, 'detail.html', {'blog': blog_detail})
    3. home.html
        {% for blog in blogs.all %}
        <div class="container">
            <h1>{{ blog.title }}</h1>
            <p>{{ blog.pub_date }}</p>
            <p>{{ blog.summary }}<a href="{% url 'detail' blog.id%}">...more</a></p>    # href내용 중요. detail과 연결하면서 blog.id객체 넘겨줌 
        </div>
        {% endfor %}
```  

  
- - -  

### 기타  

```python
  1. app폴더 내 models.py
    class Blog(models.Model):
        def summary(self):              # 자기자신의 객체 중,
            return self.body[:100]      # body를 100자로 제한하여 return
  2. app폴더 내 html
     {% for blog in blogs.all %}
      <div class="container">
      <p>{{ blog.summary }}</p>
      </div>
      {% endfor %}
```  
