# CSS  
- Cascading Style Sheets  
- ★[CSS] : 선언, 선언블록  
- 요소  

  > 선택자 (Selector)  

  > 속성 (Property)  
    >> 지정할 스타일의 속성명  
    >> `속성: 값;`  
    >> 세미 콜론으로 구분  
    >> `font-size`, `font-family`, `color`, `background-color`,  

  > 값 (Value)  
    >> 속성과 쌍을 이룸  
    
- - - 

### HTML에 CSS적용시키기  
1. Link style  
  > HTML외부의 CSS파일 불러옴  
  > 가장 일반적  
  ```python
    <head>
      <link rel="stylesheet" href="test.css">
    </head>
  
    <body>
      <p>1. Link style</p>
      <h1>KSAhh입니다.</h1>
    </body>
  ```

2. Embedding style  
  > HTML의 <head>에 <style>를 이용하여 CSS작성  
  ```python
    <head>
        <style>
          h1 {
              color: green;
          }
        </style>
    </head>

    <body>
      <h1>KSAhh입니다.</h1>
    </body>
  ```

3. Inline style  
  > HTML요소에 직접 style 속성(attributes)을 이용하여 CSS 작성  
  ```python
    <body>
      <h1 style="color : red;">Inline style</h1>
    </body>
  ```

- - -

#### 단순 선택자 (selector)  

|Type|Class|Id|Universal|Attribute|
|:----:|:---:|:-:|:-------:|:---------:|
|<style="color:red">`tag {}`</span>|`.class{}` |`#id {}`|`*{color:red;}`|`tag[target="_blank"]{}`|

<span style="color:red">1. 타입 (Type)</span>  
  > 해당 태그의 모든 요소에 적용  
  > `p {color: red;}`  
  > 
  ```python
    <head>
        <style>
          p {color: red;}
          h2 {color: blue;}
    </style>
    </head>
  ```  

2. 클래스 (Class)  
  > 비슷한 특징을 갖는 요소 지정  
  > 여러번 사용 가능  
  > `.contents{font-size: 24px}`  
  > 
  ```python
    <head>
        <style>
            .contents {
            font-size: 24px;
            }
        </style>
    </head>

    <body>
        <p class="contents">첫 번째 단락</p>
        <p class="contents">두 번째 단락</p>
        <p class="contents">세 번째 단락</p>
    </body>
  ```  
  
3. 아이디 (Id)  
  > IDentification  
  > Id당 하나의 style  
  > `#lesson {background-color: yellow:}`  
  > 
  ```python
    <head>
      <style>
        #lesson { background-color: yellow; }
      </style>
    </head>
    
    <body>
      <h2 id="lesson">lesson9</h2>
    </body>
  ```  
  
4. 전체 (Universal)  
  > 모든 요소에 적용  
  > 속도 저하될 수 있음 / 권장하지 않음  
  > `*{color:red;}`  

5. 속성 (Attribute)  
  > 특정 속성 가지는 모든 요소에 적용  
  > `선택자[속성명="속성값"]` / `a[target="_blank"]{color:red;}`  
  > 
  ```python
    <head>
        <style>
            a[target="_blank"] {
            color: burlywood;
            }
        </style>
    </head>

    <body>
        <a href="https://www.google.com/" target="_self">구글 현재창</a><br>
        <a href="https://www.google.com/" target="_blank">구글 새 창</a><br>
        <a href="https://www.google.com/" target="_self">구글 현재창</a><br>
        <a href="https://www.google.com/" target="_self">구글 현재창</a><br>

    </body>
  ```  
  
  - - - 
