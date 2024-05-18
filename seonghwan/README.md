# Git

- **명령어**
    - **git init** : 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리(=working directory)로 설정하고 그 안에 레포지토리(.git 디렉토리) 생성
    - **git config** **user.name 'codeit'** : 현재 사용자의 아이디를 'codeit'으로 설정(커밋할 때 필요한 정보)
    - **git config user.email 'teacher@codeit.kr'** : 현재 사용자의 이메일 주소를 'teacher@codeit.kr'로 설정(커밋할 때 필요한 정보)
    - **git add [파일 이름]** : 수정사항이 있는 특정 파일을 staging area에 올리기
    - **git add [디렉토리명]** : 해당 디렉토리 내에서 수정사항이 있는 모든 파일들을 staging area에 올리기
    - **git add .** : working directory 내의 수정사항이 있는 모든 파일들을 staging area에 올리기
    - **git reset [파일 이름]** : staging area에 올렸던 파일 다시 내리기
    - **git status** : Git이 현재 인식하고 있는 프로젝트 관련 내용들 출력(문제 상황이 발생했을 때 현재 상태를 파악하기 위해 활용하면 좋음)
    - **git commit -m "커밋 메시지"** : 현재 staging area에 있는 것들 커밋으로 남기기
    - **git help [커맨드 이름]** : 사용법이 궁금한 Git 커맨드의 공식 메뉴얼 내용 출력
    - **git push -u origin master** : 로컬 레포지토리의 내용을 처음으로 리모트 레포지토리에 올릴 때 사용
    - **git push** : 로컬 레포지토리의 내용을 리모트 레포지토리에 보내기
    - **git pull** : 리모트 레포지토리의 내용을 로컬 레포지토리로 가져오기
    
    <aside>
    💡 **git push**와 **git pull**은 그 작업 단위가 브랜치이다. (**git push -all** 커맨드로 모든 브랜치의 내용을 전송할 수 있다.)
    
    </aside>
    
    - **git clone [프로젝트의 GitHub 상 주소]** : GitHub에 있는 프로젝트를 내 컴퓨터로 가져오기
    
    <aside>
    💡 **git reset [옵션] [커밋아이디]** :
    
    1. HEAD가 과거의 특정 커밋을 가리키도록 한다.
        - HEAD^ : 바로 이전 커밋
        - HEAD~[n] : n단계 전 커밋
    2. staging area를 과거의 특정 커밋의 내용과 똑같게 만든다.
    3. working directory를 과거의 특정 커밋의 내용과 똑같게 만든다.
    - **—soft** : 1단계만 수행
    - **—mixed** : 1, 2단계 수행
    - **—hard** : 1, 2, 3단계 수행
    </aside>
    
    - **git log** : 커밋 히스토리를 출력
    - **git log --pretty=[옵션]** : --pretty 옵션을 사용하면 커밋 히스토리를 다양한 방식으로 출력할 수 있다.
    - **git show [커밋 아이디 / 태그이름]** : 특정 커밋에서 어떤 변경사항이 있었는지 확인
    - **git commit --amend** : 최신 커밋을 다시 수정해서 새로운 커밋으로 만듦
    - **git config alias.[별명] [커맨드]** : 길이가 긴 커맨드에 별명을 붙여서 이후에 별명으로 해당 커맨드를 실행할 수 있도록 설정
    - **git diff [커밋 A의 아이디] [커밋 B의 아이디]** : 두 커밋 간의 차이 비교
    - **git branch [새 브랜치 이름]**: 새로운 브랜치를 생성
    - **git checkout -b [새 브랜치 이름]**: 새로운 브랜치를 생성하고 그 브랜치로 바로 이동
    - **git branch -d [기존 브랜치 이름]**: 브랜치 삭제
    - **git checkout [기존 브랜치 이름]**: 그 브랜치로 이동
    - **git merge [기존 브랜치 이름]**: 현재 브랜치에 다른 브랜치를 머지
    - **git merge --abort**: 머지를 하다가 conflict가 발생했을 때, 일단은 머지 작업을 취소하고 이전 상태로 돌아감
    - **git fetch**: 로컬 레포지토리에서 현재 HEAD가 가리키는 브랜치의 upstream 브랜치로부터 최신 커밋들을 가져옴(가져오기만 한다는 점에서, 가져와서 merge까지 하는 git pull과는 차이가 있음)
    - **git blame**: 특정 파일의 내용 한줄한줄이 어떤 커밋에 의해 생긴 것인지 출력
    - **git revert**: 특정 커밋에서 이루어진 작업을 되돌리는(취소하는) 커밋을 새로 생성
    - **git reflog** : HEAD가 그동안 가리켜왔던 커밋들의 기록을 출력
    - **git log --all --graph** : 모든 브랜치의 커밋 히스토리를, 커밋 간의 관계가 잘 드러나도록 그래프 형식으로 출력
    - g**it rebase [브랜치 이름]** : A, B 브랜치가 있는 상태에서 지금 HEAD가 A 브랜치를 가리킬 때, g**it rebase B**를 실행하면 A, B 브랜치가 분기하는 시작점이 된 공통 커밋 이후로부터 존재하는 A 브랜치 상의 커밋들이 그대로 B 브랜치의 최신 커밋 이후로 이어붙여짐(git merge와 같은 효과를 가지지만 커밋 히스토리가 한 줄로 깔끔하게 된다는 차이점이 있음)
    - **git stash** : 현재 작업 내용을 스택 영역에 저장
    - **git stash apply [커밋 아이디]** : 스택 영역에 저장된 가장 최근의(혹은 특정) 작업 내용을 working directory에 적용
    - **git stash drop [커밋 아이디]** : 스택 영역에 저장된 가장 최근의(혹은 특정) 작업 내용을 스택에서 삭제
    - **git stash pop [커밋 아이디]** : 스택 영역에 저장된 가장 최근의(혹은 특정) 작업 내용을 working directory에 적용하면서 스택에서 삭제
    - **git cherry-pick [커밋 아이디]** : 특정 커밋의 내용을 현재 커밋에 반영
- **Repository (.git 디렉토리)**
프로젝트 디렉토리의 각 버전이 담기는 저장
    - **로컬 레포지토리**
    내 PC의 레포지토리
    - **원격 레포지토리 / 리모트 레포지토리**
    깃허브의 레포지토리
    1. 안정성
    2. 협업 가능
        
        <aside>
        💡 Git에서는 최초의 리모트 레포지토리의 이름을 origin으로 설정하는 것이 관례이다.
        ex) **git remote add origin https://github.com/seonghwan20/Math_Box.git**
        
        </aside>
        
- **commit (커밋)**
staging area의 현 상태를 그대로 하나의 버전으로 남기는 작업 또는 그 결과물
    - **커밋 아이디 / 커밋 해시**
    커밋을 구분하기 위한 방법
    - **커밋메세지 작성 가이드라인**
        1. 커밋 메세지의 제목(title)과 상세 설명(body) 사이에는 한 줄을 비운다.
        2. 커밋 메세지의 제목 뒤에 온점(.) 은 붙이지 않는다.
        3. 커밋 메세지의 제목의 첫 번째 알파벳은 대문자로 작성한다.
        4. 커밋 메세지의 제목은 명령조로 작성한다.
        5. 커밋의 상세 내용에는 커밋의 이유와 문제, 해결책의 효과 등을 적으면 좋다.
        6. 최대한 친절하게 작성한다.
    - **커밋할 때 알아야 할 가이드라인**
        1. 하나의 커밋에는 하나의 이슈를 해결한 내용만 남기도록 한다.
        2. 현재 프로젝트 디렉토리의 상태가 그 내부의 전체 코드를 실행했을 때 에러가 발생하지 않는 상태인 경우에만 커밋한다.

<aside>
💡 1. 처음으로 커밋을 하기 전 사용자의 이름과 이메일 주소를 설정
2. 커밋 메세지 남기기 (옵션 -m)
3. 커밋할 파일을 git add로 지정해주기

</aside>

- **tag (태그)**
보통 프로젝트에서 주요 버전의 시작점이 되는 커밋에 태그를 단다.
    - **git tag [태그이름] [커밋아이디]** : 해당 커밋에 태그 설정
    - **git tag -d [태그이름]** : 해당 태그 제거
    - **git tag** : 현재 프로젝트 디렉토리의 모든 태그 조회
- **Head**
보통 최근에 한 커밋을 가리키는 포인터. Head가가리키는 커밋에 따라 working directory가 구성된다. (사실은 branch를 가리킨다.)
- **Detached HEAD** : 브랜치를 통해서 커밋을 가리키는 것이 아니라 직접 커밋을 가리키고 있는 상태의 HEAD. **git checkout [커밋아이디]** 로 설정 가능 (과거의 특정 커밋에서 새로운 브랜치를 만들 때 사용)

<aside>
💡 **git reset** vs **git checkout**

| git reset | git checkout |
| --- | --- |
| HEAD가 가리키던 브랜치가 다른 커밋을 가리키도록 한다 | HEAD 자체가 다른 커밋이나 브랜치를 가리키도록 한다 |
| HEAD도 결국 간접적으로 다른 커밋을 가리키게되는 효과가 생긴다 | 브랜치를 통하지 않고, 커밋을 직접적으로 가리키는 HEAD를 Detached HEAD라고 한다 |
</aside>

## Git의 작업 영역

1. **working directory (working tree)**
작업을 하는 디렉토리
2. **staging area (index)**
git add로 지정한 파일들이 존재하는 영역
3. **repository**
working directory의 변경 이력들이 저장되어있는 영역

## Git의 상태(status)

- **Untracked 상태**
추적되고 있지 않은 상태. 파일이 Git에 의해서 그 변동사항이 전혀 추적되고 있지 않은 상태 (파일을 새로 생성하면 이 상태이다.)
- **Tracked 상태**
파일이 Git에 의해 그 변동사항이 추적되고 있는 상태
- **Staged 상태**
파일의 내용이 수정되고나서, staging area에 올라와있는 상태
- **Unmodified 상태**
현재 파일의 내용이 최신 커밋의 모습과 같은 상태
- **Modified 상태**
최신 커밋의 모습과 비교했을 때 조금이라도 바뀐 내용이 있는 상태

## Branch

: 하나의 코드 관리 흐름, 커밋을 가리키는 포인터

### Tracking connection

: 로컬 레포지토리의 한 브랜치가 리모트 레포지토리의 한 브랜치와 연결된 상태

- —set-upstream 옵션으로 설정할 수 있으며 보통은 약자 -u로 사용한다.
ex) git push -u origin main
- 로컬 레포지토리의 branch A와 리모트 레포지토리의 브랜치 B가 tracking connection이 맺어진 경우, B 를 A의 upstream branch라고 한다.

<aside>
💡 tracking connetion이 없을 때는 **git push origin main(로컬):main(리모트)**을 입력하여 git push할 수 있다.

</aside>

### merge

: HEAD가 가리키던 커밋에 다른 브랜치가 가리키던 커밋을 합쳐서 새로운 커밋을 만드는 작업

- **merge commit** : merge를 통해서 생겨난 커밋
- **Fast-forward merge** : 커밋 히스토리에서 같은 line 상에 있는 브랜치를 merge하는 것
- **3-way merge** : 커밋 히스토리 상에서 분리된 2개의 line에 각각 존재하는 두 브랜치를 merge하는 것
    1. 두 갈래로 갈라지기 전 공통 조상이 되는 커밋
    2. 한 브랜치가 가리키는 커밋
    3. 다른 브랜치가 가리키는 커밋
    
    이렇게 3가지 커밋을 고려해서 merge한다. 
    
    **3-way merge 방식**
    
    - base(두 브랜치의 공통 부모 커밋)에서 변화가 발생한 것을 우선 채택한다.
    - 두 브랜치에서 모두 변화가 있을 경우 conflict가 발생한다.

### conflict

: branch들을 merge할때 발생하는 충돌

- **하나의 파일에서 conflict 가 발생했을 때**
    1. conflict가 발생한 파일을 연다.
    2. merge의 결과가 되었으면 하는 모습대로 코드를 수정한다.
    3. 커밋한다.
- **파일 여러개에서 conflict가 발생했을 때**
    1. 파일 하나씩 conflict를 해결하고 **git add [파일 이름]** 커맨드로 하나씩 staging area에 올리거나 모든 파일들의 conflict를 다 해결하고, **git add .** 커맨드로 한번에 staging area에 올린다.
    2. 커밋한다.

<aside>
💡 merge자체를 취소하려면 **git merge —abort** 입력

</aside>

### fetch

- 리모트 레포지토리에서 가져온 브랜치의 내용을 merge하기 전에 점검해야할 필요가 있을 때 사용
- 리모트 레포지토리에 있는 브랜치의 내용과 내가 작성한 코드를 비교해서 잘못된 부분이 없는지 검토해야할 때 (**git diff** 로 확인)

### rebase

: 현재 브랜치의 베이스를 특정 브랜치로 재지정할 때 사용

- **merge** vs **rebase**
    1. rebase는 새로운 커밋을 만들지 않는다.
    2. rebase로 만들어진 커밋 히스토리는 merge로 만들어진 커밋 히스토리보다 깔끔하다.
    3. 사실 결과물은 같다.
        - merge : 두 브랜치를 합쳤다는 정보가 커밋 히스토리에 꼭 남아야하는 경우
        - rebase : 커밋 히스토리를 깔끔하게 유지하는 게 더 중요한 경

### stash

: 작업 내용을 아직 커밋하지 않았는데 임시 저장해야할 때, 잘못된 브랜치에서 작업했을 때 사용

- stack 구조로 저장되며 최근 커밋 이후로 작업했던 내용은 모두 스택에 옮겨지고 working directory 내부는 최근 커밋의 상태로 초기화된다.
    
    <aside>
    💡 stack은 브랜치에 제한없이 접근할 수 있다.
    
    </aside>
    

## gitignore

: working directory 내에 존재하는 파일들 중에서 마치 존재하지 않는 것처럼 Git이 인식해야할 파일들의 목록

### gitignore의 이유

- 버전 관리를 할 정도의 가치가 없다.
- 버전 관리를 하면 용량만 더 차지한다.
- 나중에 각 버전을 살펴볼 때 가독성을 떨어뜨린다.