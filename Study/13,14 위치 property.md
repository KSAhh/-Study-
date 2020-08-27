## `display`  
- 보여지는 방식  
- style에 사용  

##### `display: block;`    
- 새로운 줄에서 시작  
- 기본 : width 100%
- ex) `<div>`, `<h1~h6>`, `<p>`, `<header>`, `<section>`  
- 사용가능 property : `width`, `height`, `margin`, `padding`  

##### `display: inline;`  
- 새로운 줄에서 시작X  
- 필요한 만큼의 너비 차지  
- ex) `<a>`, `<span>`, `<img>`  
- 사용불가 property : `width`, `height`, `margin-top`, `margin-bottom`  

##### `display: inline-block;`  
- property 모두 사용 가능  

##### `diplay: none;`  
  - 출력X  

- - -  
- - -  

## `position`  

##### `position: static;`  
- 기본값  
- 좌표 프로퍼티 쓸 수X  

##### `position: relative;`  
- 기본위치 기준으로 좌표사용  

##### `position: absolute;`  
- 부모 or 조상에 relative, absolute, fixed가 선언된 곳을 기준으로 좌표사용  
- inline-block처럼 작용 : block요소라도 inline처럼 width가 줄어듦. width지정도 가능  

##### `position: fixed;`  
- 보이는 화면을 기준으로 좌표 프로퍼티를 이용하여 위치 고정  
- 스크롤할 때 따라다님  

#### `position: z-index;`  
- 숫자 클수록 앞으로  

- - -  
- - -  

## flexbox  
> 크기가 불분명한 요소에게도 효율적으로 배열  
> 가로 혹은 세로의 정해진 방향으로 배치  
> [flexbox]  

#### flex container  
  - 부모 요소  
  - `display: flex;` 추가  
  - 속성  
    - `flex-direction`  
      > container를 기준으로 item 방향 결정  
      > `row`:왼오(기본값)  
        `row-reverse`:오왼  
        `column`:위아래  
        `column-reverse`:아래위  
      > [flex-direction]  
    - `flex-wrap`  
      > flex를 벗어났을때 줄 바꾸기  
      > `wrap`:줄 바꿈, `nowrap`:줄 안바꿈
    - direction, wrap 한꺼번에 표시
       ```python
         flex-flow: row wrap;
       ```
       
    - `justify-content`  
      > flex-direction에서 정해진 방향을 기준으로 수평으로 item 정렬 / 즉 동일한 방향  
      > [justify-content][justify-content2]  
      > `flex-start`:왼쪽끝(기본값)  
        `center`:중앙  
        `flex-end`:오른쪽끝  
        `space-around`:시작과 끝을 기준으로 동일간격으로 배치  
        `space-between`:시작과 끝에 아이템을 두고, 남은 간격을 동일한 간격으로  
      
    - `align-items`  
      > flex-direction에서 정해진 방향을 기준으로 수직으로 item 정렬 / 즉 수직방향  
      > `stretch`:아이템을 늘려서 맞춤(기본값), `flex-start`, `flex-end`, `center`,  
        `baseline`:글꼴의 기준선에 정렬  
    - `align-content`  
      > ~ 수직으로 여러줄인 item 정렬  
      > `stretch`:(기본값), `flex-start`, `flex-end`, `center`, `space-between`, `space-around`  
    
#### flex item  
  - 자식 요소  
  - 속성  
    - `flex-grow`  
      > item의 확장  
      > 단위 없는 숫자(기본 0)  
      > [flex-grow]
        >> 0: container 커져도 item은 안 커짐  
        >> 1: continer커지면 item도 커짐  
        >> 여러개 : 큰 숫자가 많은 공간 차지  
        
    - `flex-shrink`  
      > 축소  
      > 기본값 1 / 숫자 클수록 많이 축소  
      > [flex-shrink]  
        >> 0: 컨테이너 크기 작아져도 item크기 그대로  
        
    - `flex-basis`  
      > 기본 크기 결정  
      > `auto`:(기본값)  
      > 단위 반드시  
      
    - `flex`  
      > 위 속성을 한번에 설정  
      > 1:on / 0:off
      ```python
        flex: 1 0 auto;           <!-- flex-grow > flex-shrink > flex-basis 순-->
      ```
    
