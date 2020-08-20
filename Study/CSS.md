# CSS  
- Cascading Style Sheets  
- ★[CSS] : 선언, 선언블록  
- 요소  

  > 선택자 (Selector)  

  > 속성 (Property)  
    >> 지정할 스타일의 속성명  
    >> `속성: 값;`  
    >> 세미 콜론으로 구분  
    >> `font-size`, `font-family`, `color`  

  > 값 (Value)  
    >> 속성과 쌍을 이룸  
    
- - - 

### HTML에 CSS적용시키기  
1. Link style  
  - HTML외부의 CSS파일 불러옴  
  - 가장 일반적  
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
  - HTML의 <head>에 <style>를 이용하여 CSS작성  
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
  - HTML요소에 직접 style 속성(attributes)을 이용하여 CSS 작성  
  ```python
    <body>
      <h1 style="color : red;">Inline style</h1>
    </body>
  ```
