### path-converter  
- 여러 객체 다루는 계층적 url이 필요할 경우  
- 형식: `<type:name>`  

### html끼리 연결하면서 data 공유하기  
- 프로젝트 폴더 내 urls.py 
```python
    urlpatterns = [
        path('blog/<int:blog_id>', Blog.views.detail, name="detail"),
    ]
```  
> `'<int:blog_id>` : 각 게시물의 id값이 들어갈 공간 / path-converter  
  
- - -  
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
