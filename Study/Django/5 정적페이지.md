### 정적파일 (Static File)  
- static 
- 미리 서버에 저장된 파일  
- 서버에 저장된 그대로를 서비스해주는 파일   
- CSS, JS, image 등  
- 순서  
1. static 폴더 만들기 / App내에 Static폴더 만들기  
2. 어디에 있고, 어디로 모을지 알려주기 / 프로젝트 폴더 내 setting.py  
3. static파일 한 곳에 모으기 / `$ python manage.py collectstatic`  
4. 선언 후 static 파일 사용  

### 동적파일 (Dynamic File)  
- media  
- 서버의 데이터들이 가공된 다음, 서비스되는 파일  
- 상황에 따라 데이터가 달라짐  


- - -  

### 이미지 띄우기 - static  
```python
  1. app내에 static 폴더 생성
  2. 사진을 폴더에 static 넣기
  3. 프로젝트 폴더내 setting.py
      STATICFILES_DIRS = [
          os.path.join(BASE_DIR, '앱이름', 'static')     # static파일 들어있는 경로
      ]
      STATIC_ROOT = os.path.join(BASE_DIR, 'static')    # static파일 모을 위치
  4. $ python manage.py collectstatic                   # 가장 상위폴더 내에 static폴더 생성됨
  
  5. html파일
      {% load staticfiles %}                            # 최상단에 작성 / static파일 불러옴
      <img src="{% static '이미지이름.jpg' %}">          # 이미지 첨부 / pdf는 `img`가 아닌 `a`
```  
> ⭐️`NameError: name 'os' is not defined` : 오류발생하면 `import os` 적기  

### 이미지 띄우기 - media
```python
  1. 프로젝트 폴더 내 settings.py
      MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
      MEDIA_URL = '/media/'
  2. 프로젝트 폴더 내 urls.py                              # 이미지 불러올 준비단계. 이해하지말기
      from django.conf import settings
      from django.conf.urls.static import static
      urlpatterns = [
      ]+ static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
      
      또는
      
      urlpatterns += static(settings.MEDIA_URL,document_root=settings.MEDIA_ROOT)
  3. 앱 내 models.py
      class Portfolio(models.Model):                      # Class명은 항상 대문자로 시작하게
        title = models.CharField(max_length=255)
        image = models.ImageField(upload_to='images/')    # 업로드된 이미지를 images폴더에 넣기
        description = models.CharField(max_length=500)

      def __str__(self):
        return self.title
  4. $ python manage.py makemigrations
  5. $ python manage.py migration
  6. $ pip install Pillow                                 # 설치 안 된경우
  
  7. app내 admin.py
      from .models import 클래스                           # models.py 클래스
      admin.site.register(클래스)                          # models.py 클래스
  8. /admin페이지에 들어가서 클래스가 잘 생성됐는지 확인
  ```  
> [참고](https://docs.djangoproject.com/ko/2.1/topics/db/models/)  
> ⭐️`no such table` : 오류발생하면 `$ python manage.py migrate`  
> 요약
1. setting.py에 media설정하기  
2. url 수정  
3. model 만들기  
