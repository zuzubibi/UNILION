# LikeLion github session

## git
1. create Git Repository
2. git init
3. git remote add origin (repo_address)
4. git add .   
5. git commit -m ("info")
6. git push origin master / force = git push -f origin master

* git banch (branchname) : 새로운 브런치 생성<br>
* git checkout (branchname) : 해당 브런치로 이동<br>
* git pull origin (branch) : 원격 저장소의 특정 브랜치에서 변경사항 pull<br>
* git clone http://원격 저장소 주소.git : 원격 저장소에 있는 파일 전체 복사 (pull할 때 사용)<br>
* git status : git 저장소의 상태 확인<br>
<br>

## git add.와 git commit을 동시에하는 방법 

```
$ git commit -am ("info")  
```

## git pull명령 후 non-fast-forward 문제 해결방법
### 현상
github에서 저장소 생성 후 저장소 주소를 remote에 입력(git remote add origin https://github…..)했고, 로컬에서도 정상적으로 초기화(git init)했는데도 git pull 또는 git merge 명령이 동작하지 않고 git push origin master시 [rejected] master -> master (non-fast-forward) 에러가 발생하는 경우

### 원인
깃허브에 생성된 원격 저장소와 로컬에 생성된 저장소 간 공통분모가 없는 상태에서 병합하려는 시도로 인해 발생.<br>기본적으로 관련 없는 두 저장소를 병합하는 것은 안되도록 설정되어 있음.

### 해결방법
아래와 같이 git pull 시에 –allow-unrelated-histories 옵션 추가하여 관련 없었던 두 저장소를 병합하도록 허용<br>
```
$ git pull origin master --allow-unrelated-histories
```
----------------------------------------------------------------------
<br>

## GitHub을 이용한 협업

1. 원격 저장소 생성
2. 팀원을  Collaborator로 추가
3. 초기 프로젝트 push
4. 팀원들의 로컬에 프로젝트 pull
5. 팀원 각자의 브랜치를 생성하여 작업
6. Master와 merge 하기 전 Pull request
7. Pull request 확인 후 Master와 merge
<br>

## Fork를 이용한 협업

1. 작업하고 싶은 Repositroy fork 해오기
```
바탕화면에 새로 생성한 파일 fork

$ cd for
$ git clone ('git-address')
```
<br>

2. 자신의 로컬에서 작업
```
$ ls      // 내용 확인 (Spoon-Knife폴더가 있다고 가정하자)
$ code .  // visual code로 들어갈 수 있음 (수정작업을 하면 됨)
$ cd Spoon-Knife
$ git status 
$ git add.
$ git commit -m "id change"
```
<br>

3. 변경사항을 자신의 브랜치에 push
```
$ git checkout -b subeen     // 브랜치를 새로 만들기 + 브랜치 전환
$ git push origin subeen

```
<br>

4. 원본 레포지토리 소유자에게 Pull request 요청
5. 소유자가 Pull request를 승인하여 merge하면 자동으로 Collaborator 추가

