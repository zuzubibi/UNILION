# 강좌의 목표와 진행방식
1. 목표
API란?<br>
API의 사용법은?<br>
2. 진행방식
개념->실습-> 서비스 만들기<br>
3. 결과물
마스크알리미
https://mask-nearby.com/<br>
4. 수강전 사전 지식
HTML, CSS, Javascript, Git, Github<br>
공부할 수 있는 곳 => ofcourse.kr<br>
5. 실습환경 및 다운로드 링크 안내
- VisualStudioCode : 코드를 작성하는 전용 메모장
- Postman : API를 테스트하는 도구
- python3 : python3의 정적 서버 기능만 사용, 꼭 Add Python 3.8 to
- chorme
- Git : 버전 관리 도구
- Github 계정 : 버전관리 도구로 저장한 내용들을 모아두는 클라우드
<br>

---------------
# 이론
## HTTP, JSON, API
1. HTTP
<tab>    : Hyper Text Transfer Protocol <br>
<tab>   -> 참조를 통해 한 문서에서 관련된 다른 문서들로 넘나들며 원하는 정보를 얻을 수 있게 해주는 텍스트 (Hyper Text)  ex. "유튜브"<br>
<tab>   -> 인터넷을 통해서 정보를 주고받을 때 지켜야하는 규칙 (Transfer Protocol) <br>
![](img/01.png)
![](img/02.png)

2. JSON
<tab>	: java Script Object Notation<br><br>	
<tab>	-> key : Value 형식<br>
<tab>	 "이름" : "허태정"<br>
<tab>	 " 몇 강" : 2<br>
<tab>	-> 데이터 교환<br>
<tab>	JSON 형식을 자주 사용!<br>
<tab>이전에는 XML이라는 형식도 사용했었다.<br>
![](img/03.png)<br>

데이터를 전송할 때, 문자열로 바꿔줘야한다.(직렬화)<br>
받은 데이터를 다시 원래대로 복구한다.(역직렬화)<br>

### JSON의 형식 예시
MDN JSON 문서: https://developer.mozilla.org/ko/docs/Learn/JavaScript/Objects/JSON
<br><br>

같은 페이지의 Superhero data : https://mdn.github.io/learning-area/javascript/oojs/json/supereroes.json.
<br><br>

### 직렬화 과정
```
$ JSON.stringify(super_hero); : 스트링화한다.
$ let serialized; : 직렬화한다.
$ JSON.parse(serialized);
```
3. API
<tab>	: Application Programmming Interface
<br><br>
<tab>	-> Application :우리가 사용하는 다양한 서비스들<br>
<tab>	->Programming Interface : 서비스들이 제공해주는 데이터들에 접근하고<br>
<tab><tab><tab><tab>		 사용할 수 있도록 도와주는 도구!<br>
<tab>"TV의 리모컨 같은 존재!"<br>

4. REST API

	1) API의 종류<br>
		a. SOAP : Simple Object Access Protocol  - XML을 잘 주고받게 해주는 프로토콜의 일종 
		b. REST : Representational State Transfer - 아키텍쳐이다
		c. GraphQL : Graph Query Language - API서버를 만들 떄, REST의 한계를 보완해준다.
	<br>	
        
	2) REST<br>
     - REST는 하나의 아키텍쳐 
      소프트웨어 아키텍처: 소프트웨어를 설계하는 지침과 원칙<br>
	물론 꼭 전부 다 지ㅕ야 하는 법이 아니기 떄문에 완전히 restful한 API는 많지 않다.<br><br>
	
	3) REST의 구성요소<br>
	```
    자원) GET/likelion/member/8th/list
		PATCH/likelion/member/8th/이수빈

	행위) GET/likelion/member/8th/list
		PATCH/likelion/member/8th/이수빈

	표현) 
    {
        "members" : ["김멋사", … , "허멋사"]
    }

    ```

-----------

# REST API 실습, OPEN API
## JSONPlaceholder
- Fake online REST API를 제공해주는 사이트
- REST API를 테스트, 프로토타이핑 가능
- 사이트 주소 : https://jsonplaceholder.typicode.com/

* URL 알아보기
1. 구성 
- 프로토콜 : http, https, file 등
- 호스트 주소 : www.naver.com, www.google.com
- 파일경로 : /home, /index.html
- Query parameter : ?id=1&postId = 1 (검색, 필터링, 데이터 교환 시 사용)
** URL을 따로 정리한 블로그 : https://zuzubibi99.tistory.com/17 <br>

## Postman 실습
![](img/04.png)<br>
![](img/05.png)<br>
![](img/06.png)<br>
comments를 넣는 그대로 요청을 받아들이기 때문에 아래에서 comments가 생긴 것을 볼 수 있다.<br>
만약 posts에서 제공하지 않는 field를 넣게 되면 error가 나서 문제(404)가 발생할 수도 있다. <br><br>

![](img/07.png)<br>
아이디가 1인 post를 가져오기를 실행한 모습이다.<br><br>

![](img/08.png)<br>
1번 포스트를 수정하기 위한 작업이다.<br>
"id"가 작동하지 않는다는 것을 알았으니 지워주자<br><br>

![](img/09.png) <br>
PATH는 수정한 것을 input했을 때 print값엔 원본의 값이 수정이 되지 않은 부분은 그대로이고 수정한 부분이 업데이트되는 것이다.<br><br>

![](img/10.png)<br>
PUT은 수정한 것을 input했을 때 print값엔 원본과 상관없이 PUT에서 받은 것만이 넘어온다. 그리고 id는 컴퓨터가 알아서 만들어 주고 있다.

<!-- ## OPEN API
## 공적마스크 API 살펴보기 -->