### 작업환경 설치(윈도우)  
1. python 설치  
    ```
    "python.org" 접속 → "Python 3.8.3" 클릭 → 'Add Python 3.8 to PATH' 체크 → install → Next...
    ```  
2. Visual Studio Code  
    ```
    "vscode" 검색 → "Visual Studio Code - Code Editing. Redeifined" 클릭 → "Downloads for Windows" 클릭 
    ```  
3. Git Bash  
    ```
    "git bash" 검색 → "Git for Windows" 접속 → "Download" 클릭 → Next... → 'Use Visual Studio Code as Git's default editor' 설정 → Next...
    ```  
    
- - -  

### FramWork
- fram: 틀 / work: 일하다  
- 짜여진 환경에서 개발하도록 돕는것  
- 반복 작업을 표준화해서 묶어 놓은 개발환경 
- 정해진 방식으로 코드 짜도록 강요(O) / 필요할 때 가져다 씀(X) 
- ex) Django(웹 만들기 위함)  

### 라이브러리  
- 반복 작업을 줄여주는 역할  
- 정해진 방식으로 코드 짜도록 강요(X) / 필요할 때 가져다 씀(O)  

##### Django  
- python기반  
- 웹 어플리케이션 프레임워크    
- MVT패턴 (티키타카)  
- admin기능 제공  
- 쉬운 URL파싱 기능  

### Python 개념  
- 처리역할 (!= HTML)  
- 데이터분석, 머신러닝, 딥러닝에 응용  
- 템플릿 언어를 써야 HTML에 적용할 수 있음  

- 템플릿 언어 / HTML안에 쓰는 Django제공 언어  
   : `{{}}` : 템플릿 변수, `{%%}` : 템플릿 태그  
   : ex)
   ```python
   html파일 내
        {% for word, count in dic %}
            {{word}} : {{count}}
            <br>
        {% endfor %}
   ```  
   
- list
    - 변수들을 묶는 자료형  
    - ['90','86','98'] 형태
    -
      ```python
        a = ['90','86','98']
        print(a[0])        → 90
        print(a[3])        → error
      ```  
- dictionary  
    - 대응 되는 데이터 표현  
    - key:value
    - ex) 이름:KSAhh, 나이:OO, 학과:ㅁㅋ  
- 반복문  
   ```python
    for 반복제어변수 in 반복대상 :           ex) for scroe in [96,98,100,87]
      반복실행 할 내용                            print(score)
                                              결과: 96 98 100 87
   ```  
   ```python
    for i in range[5];
      sum += i
   ```
   > `range(x,y)` : x이상 y미만의 수 리스트를 반환  
   > `'range(x)` : 0~x미만의 수 리스트를 반환  

- - -  

# 실습

### gitignore  
    ```
    1. vscode에서 ".gitignore"파일 생성
    2. gitignore (gitignore.io 또는 https://www.toptal.com/developers/gitignore) 접속
    3. "VisualStudioCode", "Django", "Python" 입력 후 검색
    4. Ctrl + A
    5. 복사
    6. 프로젝트 폴더 밑(manage.py가 있는 위치)에 ".gitignore"파일 생성 후 붙여넣기
    7. 14번째 줄 media 밑에 "venv" 입력            # "venv"폴더를 안 올린다는 의미
    ```
> Github에 올리지 않아도 되는 파일(Cash 등)을 올리지 않고 저장해주는 역할  

<br>

### github에 업로드  
```python
1. $ git init                                               # git 배포  
2. $ git status                                             # 상태확인. 어떠한 파일을 수정했는지 확인 (빨간색 파일)  
3. $ git add .                                              # git에 .을 추가한다. / "."은 모든 것을 의미  
4. $ git status                                             # 빨간색 파일이 초록색 파일로 바뀜  
5. $ git commit -m "설명"                                    # 설명 작성  
6. $ git config --global user.email "ID@EAMIL"              # commit이 안되는 경우, github이메일 정보 입력  
7. $ git config --global user.name "깃허브이름"              # github와 동일해야 함
8. 다시 commit하기  
9. $ git remote add origin 깃허브 레포지토리 링크             # github 저장소와 연동  
10. $ git push -u origin master`                            # master branch에 업로드  
```

### 함수  
- text_split  
    ```python
    views.py파일
        def count(request):
            text_split = text.split()
    ```  
    > 띄어쓰기 단위로 문자가 끊겨서 저장됨  
    ```python
    views.py파일
        text_split = text.split(' ')  # 배열로 저장 (LIST)
        print(text_split[5])  # LIST중 5번째 데이터 출력
    ```  

- - -  

[Word Counter](wordcount1234.herokuapp.com)  
- views.py 파일  
    ```python
    def count(request):
    text = request.GET['fulltext']
    text_split = text.split(' ')

    word_dic = {}                   # 비어있는 word dictionary 생성
    for word in text_split:
        if word in word_dic.keys(): # word가 word_dic.keys()값에 있으면
            word_dic[word] += 1     # 단어 개수에 하나 추가
        else:
            word_dic[word] =1       # keys값에 없으면 word_dic[]에 1을 넣음. 즉 생성
    ```  
