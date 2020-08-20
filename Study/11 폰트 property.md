### `font-family`  
- `font-family: 'Cute Font', Arial, cursive;`  
  - 여러 단어인 경우 따옴표  
  - 여러개 지정해서 차례로 적용 / 마지막은 일반글꼴  
    - 일반폰트 : `serif`, `sans-serif`, `cursive`, `fantasy`, `monospace`
    
- [웹 폰트](https://fonts.google.com)  
 - 링크 통해 원하는 폰트 불러오기  
 - ##### 사용법  
 ```
    1. 웹 폰트 사이트 접속                       2. 원하는 폰트 선택                    3. Pairings 탭
    4. Embed 탭                                  5. import 밑의 코드 복사               6. <head> 밑에 붙여넣기
    7. 다시 사이트로 가서 CSS 밑의 코드 복사      8. <style> 밑에 붙여넣기
 ```
   
 - - -  
   
 ### `font-style`  
- `normal` : 기본체  
- `italic` : 이탈릭체  
- `oblique` : 기울여짐  
   
 - - -  
  
### `font-weight`  
- 100 ~ 900 / 굵기
- `bold` : 700  
- `normal` : 400  
- 디자인 되어있지 않으면, 400이하에서 작동 안 함  
  
\* 같은 의미 다른 표시  
```python
    <style>
        #main {
            font-style: oblique;                        # 스타일
            font-weight: 900;                           # 굵기
            font-size: 35px;                            # 크기
            font-family: 'Noto Sans KR', sans-serif;    # 폰트            
        }
    </style>
```  

```python
    <style>
        #main {
            font : oblique 900 35px 'Noto Sans KR', sans-serif;   # 스타일 굵기 크기 폰트
        }
    </style>
```  
  
- - -  
- - -  
  
\* 텍스트 정렬 속성  


### `text-align`  
- 웹페이지(x) 부모요소(x) 본인요소(o)를 기준으로 정렬  
- `left`, `center`, `right`  
```python
  <head>
      <style>
          h1 {text-align: center;}
          h3 {text-align: left;}
          p {text-align: right;}
      </style>
  </head>
  <body>
     <!-- 정렬 -->
     <div id="index">
        <h1>중앙</h1>
        <h3>왼쪽</h3>
        <p>오른쪽</p>
     </div>
  </body>
```  
  
### `line-height`  
- 문장 사이 간격 조정  
- line간의 높이(X) / line의 높이 / ★[Line-height]  
- `개발자 도구 → conputed`에서 pixel확인 가능  
- `line-height : 2;` <==> font-size 2배  
  `line-height: 24px;`  
  
- - -  
  
### `letter-spacing`  
- 글자 사이 간격 조정  
- `letter-spacing: 10px;`  

### `text-indent`  
- 들여쓰기  
- `text-indent: 15px;`  
