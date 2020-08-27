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
