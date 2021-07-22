---
date: 21.07.19
title: git & gihub
---

#TIL

1. git
2. github
3. cli command
4. vim command
5. mark down

---
## GIT

> VCS (Version Control System)

- 빠른 속도, 단순한 구조
- 분산형 저장소 지원
- 비선형적 개발 가능 (수천개의 브랜치)

### git objects

- Blob : 파일 하나의 내용에 대한 정보
- Tree : 해당 Blob의 기록들 (메타데이터)
- Commit : 모음, 의미 있는 변동사항들의 덩어리

### git file status

---

**깃으로 추적하는 4가지 파일의 상태**

> `추적안됨`, `수정함`, `수정없음`, `스테이지됨`

- `$git add`는 `수정함`과 `추적안됨` 파일을 스테이지로 업로드 할 수 있는데

    `add`하면 `스테이지됨` 파일상태가 된다.

- `$git commit` 을 하면 `수정없음` 상태로 돌아가 다시 파일을 수정할 수 있음.

깃은 변경사항의 모음이 아닌 **모든 전체의 모음**이다.

그럼에도 용량이 무겁지 않은 이유는 변경되지 않은 파일은 변경되지 않음만을 표시해 저장하기에 같은 파일이 두 번이상 저장되지 않기 때문이다.

한번 스테이지에 올라간 파일들은 *수정되지 않아 `add`를 하지 않아도* 계속 *스테이지에 존재* 하기 때문에 커밋을 전체의 묶음으로 볼 수 있다. 

기록해야 하는 변경사항 두개가 있을 때 `add` 를 사용해서 특별한 것만 stage에 올리고 `commit` 을 찍어 *두번으로 나눠줄 수 있다.* 

**빈 디렉토리**


원래 git은 빈 디렉토리를 Tracking 하지 않는다. 

그렇기에 폴더안에 어떠한 파일이라도 존재하고 그 파일이 

커밋이 되어야 remote repo에 올릴 수 있다.

---

### git process

> 작업해서 메모한 뒤 넘긴다.

*오프라인 (local)*

1. working directory : 코딩 및 작업 단계
2. staging area : git에 올라갈 파일들을 설정
3. local repo : commit으로 기록을 남김

    → 인터넷에 연결되어 있지 않아도 개발자가 언제 무엇을 했는지 기록을 저장해 둔다.


*온라인 (remote)*

1. remote repo :  github에 업로드 한다.

---

### github

> git ≠ github

git을 이용한 클라우드 서비스

**라이센스**

- MIT : 자유로운 수정 재배포 가능
- Apache : 수정배포 가능하나 원작자 표기
- GNU GPL 라이센스가 전염

    → 이 라이센스가 들어간 코드를 사용하면 *무조건 GPL 라이센스*를 사용해야 함

---

### 커밋 컨벤션

> commit write in english....

- 제목은 *50자 이내*로

    모든 내용을 한 눈에 파악할 수 있게 핵심적인 구나 절의 형태로

- 제목과 내용 사이는 *한칸 줄바꿈 공간*을 두기.
- *prefix*를 사용하여 *커밋의 용도*를 작성해 둔다.
    - *PREFIX*

        **feat** (features) - 기능이 추가 되었을 때
        **docs** (documentations) - [README.md](http://readme.md) 같은 텍스트 작업
        **conf** (configurations) 
        **test** (test) - 테스트를 돌린 결과물
        **fix** (bug-fix) - 디버그를 하거나 이슈가 해결되었을 때
        **refactor** (refactoring) - 문법적인 개선점을 주었을 때 (5줄의 실행을 1줄로 줄이거나)

        **ci** (Continuous Integration) 
        **build** (Build) - 배포 전 마무리 단계
        **perf** (Performance) - 성능개선

---

## git commit

### 기본 설정

$git config — list  목록들을 확인할 수 있음

$git config —global user.email {http://user.email} "{이메일}"

$git config —global user.name {http://user.name} "{이름}"

$git config —global core.editor "vim"

$git config —global core.pager "cat"

---

local과 remote의 repo 이름은 *통일* 시킨다.

### create repo

1. **git init** 

    > `$git init` → `$ git remote add origin {url}`

    ▶ `$git init` 명령어로 현재 폴더에 local repo를 생성한다.

    ---

    한 폴더에 하나의 local repo만 유지해야 한다.

    상위 폴더 안에 들어 있는 하위 폴더에 repo를 생성하면 상위 폴더 repo에 종속된다.

    - repo가 생성되었는지 *확인*하는 방법
        1. `$git status` 수정된 파일이 있는 지 확인하는 명령어

            `$git status -uall` 수정된 파일이 어떤 파일인지 풀어서 설명

        2. `ls -a` 

            .git 파일이 존재하면 repo가 생성된 것이다.

    ▶ `$git remote add origin {url}` 명령어로 remote repo와 연결해 준다.

    ---

    origin이라는 이름의 링크를 연결해 준다라는 뜻이다.

    origin은 `clone` 사용 시 자동으로 생성되는 이름이다.

1. **git clone**

    > `$git clone {remote repo's url}`

    `git clone`으로 remote repo를 복사한다면 repo의 이름으로 폴더가 생성된다.

    현재 폴대에 풀기 위해서는 `$git clone {remote repo url} .`  

    *(현재 폴더가 빈폴더일 때만 가능합니다.)*

    자동으로 origin이라는 이름의 원격저장소가 등록되게 됩니다.

---

### branch name

> github의 branch default 설정은 `main` 이다.

local repo와 remote repo의 branch 이름을 통일 시켜야 한다.

`$git branch`  현재 브랜치의 이름을 확인하는 명령어

`$git branch -M name` 현재 브랜치의 이름을 바꾸는 명령어

---

### commit

*[offline]*

1. `stage` 에 수정 된 파일 올리기

    `$git add file-name` 

    `$git add .` 전체파일 선택 

    커밋 분기점을 자르기 어려워질 수 있으니 조심히 사용할 것

2. `stage` 의 파일의 커밋 메세지 작성하기

    `$git commit`→ vim이 뜬다.

3. `commit` 확인하기

    `$git log` 커밋된 목록과 내용을 확인 할 수 있는 명령어

> 커밋은 의미있는 수정을 분기로 작성하는 것이 좋다.



*[online]*

1. `$ git push -u origin {branch-name}`

    `-u` 는 local과 remote의 repo를 연동시키는 명령어로 

    해당 브랜치로 `push` 하는 *처음 한번만* 하면 된다.

    `$git push origin main`

> `push` 는 최소 기능 단위로 올리는 것이 좋다.

---

## code review

### branch

> 메인 브렌치에서 만들어진 분기점  🌌평행 우주같은 느낌

- 여러 사람이 개발하기에 좋다.

### merge

> 새로운 코드가 작석된 compare(최신 브랜치)를 base(기존 브랜치)와 합친다.

- `$git merge (compare)` 합집합

### review → pull request

1. 브랜치 생성 

    ---

    `$git branch` 현재 브랜치 위치 확인

    `$git branch {create branch}`  새로운 브랜치 생성

    `$git switch {branch}` 브랜치 이동

→ 새로운 브랜치에서 커밋을 작성 후 push

1. pull request 

    ---

    - 리뷰어 설정하기

        ---

        repo의 setting → manage access → 리뷰어 추가

    - pull reguest 제출
    - review 해결 후 승인 요청
    - 스스로 혹은 리뷰어의 merge

        ---

        merge가 된 remote repo의 업데이트 상태를 local repo에 적용하기

        1. `$git fetch origin main`
        2. `$git merge FETCH_HEAD`  ← 이 부분 이해 필요

            ---

        == `$git pull` 

        pull은 위의 두 명령어를 합친 것과 같은 기능을 한다.
