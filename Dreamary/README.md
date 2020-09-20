# 수업 목표
## Framework & Django 개념 이해
1. Django란? <br> 
<tab> * python으로 작성된 오픈 소스 웹 어플리케이션 프레임워크<br>
<tab> * 인스타, 핀터레스트는 Django 기반으로 만들어진 서비스 이다.<br><br>

2. Django 특징 <br>
<tab> Python 기반, MVT 패턴, admin 기능 제공, 간편한 URL Parsing<br><br>

3. Framework란?<br>
<tab> * 기본적으로 필요한 기능을 갖춰, 원하는 기능 구현에 집중하도록 도와주는 개발 환경<br><br>


## MTV 패턴 파악
### MTV 패턴이란? 
![](img/01.png)<br>
URLconf : URL경로에 맞춰 view와 template에 연결<br>
Template : 사용자에게 보여지는 화면<br>
View : 웹 요청을 받고, 전달받은 데이터를 처리해서 가공<br>
Model : 데이터베이스에 저장되는 데이터<br><br>

## 사전 준비
- Git Bash/ Github 계정
- Visual Studio Code
- Extension - Beutify : html파일 자동 정리 기능, control+shift+p 누르고 beautify file하면 자동으로 이쁘게 만들어주는 플러그인  

# 실습 및 이론
## 가상환경 & PIP 이해
1. 가상환경이란?
![](./img/01.png)
자신이 원하는 Python 환경 구축을 위해 필요한 모듈만 담아 놓는 바구니
<br>

2. PIP란?
Python으로 작성된 패키지 소프트웨어를 관리하는 패키지 관리 시스템<br>

3. VS Code 단축키 모음
```
# Ctrl + Shift + `    // 터미널 생성
# Ctrl + D            // 현재 커서 위치의 코드 복사
# Alt + 위 또는 아래 커서    //현재 커서 위치의 코드 이동
```
<br>

4. 가상환경 명령어 모음
```
$ python -m venv <가상환경 이름>

윈도우 |
$ source <가상환경 이름> / Scripts/ activate

Linux, Mac |
$ source <가상환경 이름>/bin/activate

$ deactivate  //가상환경 끄기
```
<br>

5. Django 명령어 모음
```
$ pip install django    //Django 패키지 설치

$ django-admin startproject <프로젝트명> .  //Django 프로젝트 생성  // 마지막에 .(온점)을 붙이면 새로운 폴더가 생기지 않습니다

$ python manage.py startapp <App 이름>   //Django App 생성

$ python manage.py runserver   //Django 로컬 서버 시작
```
6. gitignore란?
- 각각의 컴퓨터마다 구동을 위해 임시로 만들어지는 파일들이 있는데 굳이 올려도 되는 파일들을 따로 지정해주는 것을 말한다. <br>
- 사용법 : gitignore 파일을 하나 만들고 gitignore.io에서 vscode, python, django를 입력후 나온 gitignore파일에 결과들을 복붙해준다.<br>

## Django 프로젝트 생성 & 구조 파악

## Local Server에서 페이지 출력
