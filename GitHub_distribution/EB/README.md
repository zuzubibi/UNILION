# AWS EB 배포 - 1
## Elastic Beanstalk 이란?
Elastic Beanstalk은 직역하면 유연한 콩나무라는 뜻으로 한 번 심으면 자라나듯이, 서비스를 배포하면 자동으로 순차적으로 필요한 요소들을 연결을 해주고 만약 서버의 크기를 확충해야할 때 자동으로 확충할 수 있도록 해준다.<br>
=> 웹 앱과 서비스를 배포, 관리 및 증감을 손쉽게 할 수 있도록 하는 서비스<br<br>
![](img/1.png)<br>

## 기본 로컬 설정
필수 구성 요소
- Python 3.6
- pip 
- virutalenv
- awsebcli
- django 2.2.1 version

## Django Application 설정
1. Requirements.txt 생성
배포를 하기 위한 준비단계!<br>

```
$ pip freeze --> 깔아야할 것들(패키지들)을 주문서처럼 정렬해서 알려주는 것
$ pip freeze > requirements.txt   --> 깔아야하 것들을 requirements.txt파일을 하나 만들어서 적어준다.
```
왜 이걸 만드냐면 배포를 할 때 서버 컴퓨터에 프로젝트가 올라갈텐데 필요한 패키지들을 깔려야하는 것이 있다.<br> 
그렇기에 깔아야한다고 알려주는 안내가 필요하기때문이다.<br>

2. ebextensions 설정
프로젝트내에 .ebextensions 라는 폴더를 만들고 django.config를 만들어 준다.<br>
django.config 안에 넣어 줄 코드는 검색엔진에 aws eb django라고 치면 상단의 AWS 공식 홈페이지로 들어가면 볼 수 있다.<br>
내가 만든 .ebextentions에 코드를 적어두었으니 그걸 참고해도 좋다.<br>

3. EB 환경 및 앱 생성
 - 1. EB 애플리케이션 생성
 - 2. EB 환경 생성
 - 3. 생성된 환경에 애플리케이션 배포
    ```
    $ eb init -p (appname)    //이때 새롭게 elasticbeanstalk이 생성된다.
    $ eb init
    $ eb create (application_name)   //환경설정
    $ eb status    //실행하면 나오는 cname이 url이라고 생각하렴, cname을 myapp > setting > Allowed_hosts에 추가.
    $ eb deploy    //배포가 된당😙
    $ eb open     // browser에서 잘 뜨는 것을 확인 가능하다
    ```
4. 애플리케이션 업데이트
 - 1. 사이트 설정 수정
    <tab> AWS 공식사이트 참고하기<br>
    <tab>myapp > setting> TIME_ZONE = 'Asia/seoul'로 수정<br>
 - 2. 사이트 관리자 생성
    ```
    $ source myvenv/scripts/activate
    $ python manage.py migrate
    $ python manage.py createsuperuser
    ```
 - 3. 데이터베이스 마이그레이션 구성 파일 추가
    <tab> .ebextensions에 새롭게 db-migrate.config 추가<br>
    <tab> 안에 AWS 공식사이트에서 참고한 코드 추가(코드는 파일로 들어가보면 있습니다~)<br>
    ```
    $ eb deploy  //배포하기
    $ eb open 
    ```
