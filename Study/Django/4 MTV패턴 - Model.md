# Model  
- DB뒤적뒤적  
- Django와 별개  
- 여러개 (O)  

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

<br>

### Admin 사용하기  
```python
  1. admin 계정 생성  
    `$ python manage.py createsuperuser` -> ....
  2. admin에 추가한 modle 알리기  
    
```
