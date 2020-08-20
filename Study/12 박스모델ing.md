### 💧 어렵당  

- - -

*\ html요소 : `태그+컨텐츠`  
  - ex) `<h1>수노입니다.</h1>` : "\<h1>" 태그, "수노입니다." 콘텐츠  
    
- - -  
  
# Box Model  
- ★[Box Model]
- 요소  
  - `content`  
  - `Boder` : content를 감싸는 경계선. 테두리  
  - `Padding` : 여백 / content와 border 사이  
  - `margin` : 여백 / border 밖  
- 개발자 탭 → styles → box model 확인  
 
\* 사이즈를 정해놓은 상태에서 content가 증가하면 box model을 튀어나옴  
> `overflow: hidden;`, `overflow: scroll;`을 통해 숨길 수 있음  

- - -  

### `border`  
- 시계방향 / 위 오른쪽 아래 왼쪽  
- property : `border-style`, `border-width`, `border-color`, `border-width`, ...  

  1. `border-style`   
  - ★ [border-style]  
  - `border-style: dashed solid dotted double;`  
    - `dashed` : -----  
    - `solid` : 두꺼운 직선  
    - `dotted` : .....  
    - `double` :얇은 두 줄  
  
  - 같은 의미 다른 표현
  ```python
        #inner {
            /* border 방법1 */
            border-width: 6px 8px 10px 12px;
            border-style: dashed solid dotted double;
            border-color: red blue yellow green;

            /* border 방법2 */
            border: 4px solid lemonchiffon;            # width style color
        }
  ```  
  
  2. `border-radius`  
  - ★ [border-radius]
  - 경계선 둥글게  
  - `border-radius: 12px;` : 반지름 길이  
  - 나누기(/)로 한 방에 여러개 적용
  
  .
  .
  .
  .
