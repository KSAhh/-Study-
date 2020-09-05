# Model  
- DB뒤적뒤적  
- Django와 별개  
- 여러개 (O)  

### 쿼리셋 (queryset)  
- 전달받은 객체목록 / list  
### 메소드 (method)  
- 쿼리셋들을 처리하는 방법  
- `.all()` : 모든것  
- `.count()`: data개수  
- `.first()` : 첫 번째 객체  
- `.last()` : 마지막 객체  


### migration  
- makemigrations : 파이썬 코드를 DB가 알아들을수 있게 번역  
- migrate : DB에 그 내용을 적용하라  

- - -  

##### 기타
- 프로젝트 폴더 내 settings.py  
```python
  DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',       # default는 sqlite
        'NAME': BASE_DIR / 'db.sqlite3',
     }
  }
```

<br>

### Model 사용하기  
- django 공식 documentation 참고   
```python
  1. app폴더 내 models.py
      class Blog(models.Model):                                # "Class" : 이런 데이터를 처리할 것임을 알림
          title = models.CharField(max_length=200)             # 최대 length가 200인 문자열
          pub_date = models.DateTimeField('date published')    # 날짜와 시간
          body = models.TextField()                            # 긴 문자열
  2. $ python manage.py makemigrations                         # migration 만듬. DB에게 알림 / "migrations"폴더 생성됨  
  3. $ python manage.py migrate                                # 데이터베이스에 적용  
```  
> `title`, `pub_date`, `body` : 모델의 속성  
> `CharField` : Charictor Field / 짧은 문자열  
> `TextField` : CharField보다 긴 문자열  
- 사용자가 적은 title이 뜨길 원하는 경우, app폴더 내 models.py에 추가  
  ```python
  class Blog(models.Model):  
        def __str__(self):
            return self.title
  ```

<br>

### Admin 사용하기  
```python
  1. admin 계정 생성  
    $ python manage.py createsuperuser -> ....
  2. admin에 추가한 model 알리기  
  3. 생성한 model을 django에 알리기. app내 admin.py 파일 
      from .models import 앱이름                                # . : 같은 폴더위치에 있는 models파일 / 앱이름에 해당하는 클래스를 가져오기   
      admin.site.register(앱이름)                               # admin 사이트에 앱이름에 해당하는 클래스를 등록
```  

<br> 

### data 출력  
- model → view → template  
```python
  1. app 내 views.py  
    from .models import Blog
    
    def home(request):
        blogs = 앱명.objects        # 앱 내의 객체를 blogs에 담음 / blogs는 template에 사용할 이름 
        return render(request, 'home.html', {'blogs': blogs})
   2. html
    {{ blogs }}                     # 출력: Blog.Blog.objects
    {{ blogs.all }}                 # 출력: <QuerySet [<Blog: 타이틀>]>
    
    {% for blog in blogs.all %}     # 모든 객체가 담김
      <div class="container">
          <h1>{{ blog.title }}</h1>
          <p>{{ blog.pub_date }}</p>
          <p>{{ blog.body }}</p>
      </div>
    {% endfor %}
```  
> `앱명.objects` : admin의 data  
> `blogs` : 쿼리셋 (queryset). template에 동일한 이름 사용해야 함  
> 
