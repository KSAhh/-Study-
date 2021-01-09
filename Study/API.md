### 기타  
- URL : Uniform Resource Locator  
  - 구성
    > 프로토콜 : http / https / file / ...  
    
    > 호스트주소 : www.naver.com / www.google.com / ...    
    
    > 파일경로 : /home / /index.html /... / 서버에 있는 파일, resource의 경로  
  
    > Query parameter : 형식 ?id=1&postId=1 / ... / 검색, 필터링, 데이터 교환시 사용  

- - -  

## HTTP (Hyper Text Transfer Protocol)  
- Hyper Text : 관련된 문서와 오가며 정보 얻게 해주는 text  
- Transfer Protocol : 인터넷에서 정보 주고받을 때 지켜야 할 규칙  
- 구성 : 요청(Request) ↔ 응답(Response)  

- 요청(request) 메소드  
  `Get`  
    >  읽기 URL에 표시된 resource 가져옴  
    
  `POST`  
    > 수정 body에 정보를 담아 서버에 입력  
  
  `PUT`  
    > 수정  
    > (전체) 수정 URL에 표시된 resource와 바꿔 치기  
  
  `PATCH`  
    > 수정  
    > (일부) 수정 URL에 표시된 일부만 수정  
    > PUT과 다름  
  
  `DELETE`  
    > 삭제 URL에 표시된 특정 resource 삭제  
    
- - -  


## API (Application Programming Interface)  
- Application : 서비스, 응용프로그램  
- Programming Interface : 서비스들이 데이터에 접근하도록 돕는 도구 / ex)리모컨  
- 종류 : SOAP(Simple Object Access Protocol), REST(REpresentational State Transfer), GraphQL(Graph Query Language) / SOAP 어렵다고 함  

- Rest
  > 소프트웨어 architecture / 설계의 지침, 원칙  
  > 모두 지켜야할 필요 x  
  > 구성요소 : 자원, 행위, 표현
  ```python
  GET/likelion/member/8th/list
  PATCH/likelion/member/8th/홍길동
  
  자원
  /likelion/member/8th/list
  /likelion/member/8th/홍길동
  
  행위
  GET
  PATCH
  ```
  ```python
  표현
  {
      "members":["김멋사",...,"하멋사"]
  }
  ```  
