
1주차 Git

git init : 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리(=working directory)로 설정하고 그 안에 레포지토리(.git 디렉토리) 생성
git config user.name 'codeit' : 현재 사용자의 아이디를 'codeit'으로 설정(커밋할 때 필요한 정보)
git config user.email 'teacher@codeit.kr' : 현재 사용자의 이메일 주소를 'teacher@codeit.kr'로 설정(커밋할 때 필요한 정보)
git add [파일 이름] : 수정사항이 있는 특정 파일을 staging area에 올리기
git add [디렉토리명] : 해당 디렉토리 내에서 수정사항이 있는 모든 파일들을 staging area에 올리기
git add . : working directory 내의 수정사항이 있는 모든 파일들을 staging area에 올리기
git reset [파일 이름] : staging area에 올렸던 파일 다시 내리기
git status : Git이 현재 인식하고 있는 프로젝트 관련 내용들 출력(문제 상황이 발생했을 때 현재 상태를 파악하기 위해 활용하면 좋음)
git commit -m "커밋 메시지" : 현재 staging area에 있는 것들 커밋으로 남기기
git help [커맨드 이름] : 사용법이 궁금한 Git 커맨드의 공식 메뉴얼 내용 출력
git push -u origin master : 로컬 레포지토리의 내용을 처음으로 리모트 레포지토리에 올릴 때 사용
git push : 로컬 레포지토리 > 리모트 레포지토리 
git pull : 리모트 레포지토리 > 로컬 레포지토리 반영
git clone  [프로젝트의 GitHub 상 주소] : 깃허브 프로젝트 레모지토리를 복제
*출력 : cat 파일명
원칙적으로 자신의 리모트 레포지토리에는 자신만 git push를 할 수 있습니다.
만약 다른 사용자도 git push를 할 수 있게 해주려면 그 사용자를 해당 리모트 레포지토리의 collaborator로 지정하면 됩니다.
보통 README.md 파일에는
이 프로젝트가 어떤 프로젝트인지 설명하거나
프로그램의 주요 사용법을 알려주거나
프로그램을 실행시키려면 어떤 사전 작업이 필요한지를 알려주는
 마크다운이란 특정 규칙에 맞게, 간단한 텍스트만으로 어떤 표시를 해두면, 그것이 자동으로 HTML 태그로 전환되도록 약속된 문법 
1. 커밋 메시지 작성 가이드라인
(1) 커밋 메시지의 제목과 상세 설명 사이에는 한 줄을 비워두세요.
(2) 커밋 메시지의 제목 뒤에 온점(.)을 붙이지 마세요.
(3) 커밋 메시지의 제목의 첫 번째 알파벳은 대문자로 작성하세요.
(4) 커밋 메시지의 제목은 명령조로 작성하세요.(Fix it / Fixed it / Fixes it)
(5) 커밋의 상세 내용에는 이런 걸 적으면 좋습니다.
왜 커밋을 했는지
어떤 문제가 있었고
적용한 해결책이 어떤 효과를 가지는지
(6) 다른 사람들이 자신의 코드를 바로 이해할 수 있다고 가정하지 말고 최대한 친절하게 작성하세요.
(1) 하나의 커밋에는 하나의 수정사항, 하나의 이슈(issue)를 해결한 내용만 남기도록 하세요. 
(2) 현재 프로젝트 디렉토리의 상태가 그 내부의 전체 코드를 실행했을 때 에러가 발생하지 않는 상태인 경우에만 커밋을 하도록 하세요. 
Git에는 이렇게 길이가 긴 경우의 커맨드 전체에 별명을 붙여서 그 별명을 사용할 수 있도록 해주는 기능이 있습니다.
이 때 붙이는 별명을 alias라고 하고, 별명을 붙이는 행위를 aliasing이라고 합니다.
git config alias.history 'log --pretty=oneline'
git histroy라고만 써도 자동으로 git log --pretty=oneline을 실행
git reset [옵션] [커밋 아이디]
HEAD가 현재 가리키는 커밋을 기준으로 한 상대적인 표현법인
HEAD^
HEAD~2
EX) git reset --hard HEAD~2
git tag [태그 이름] [커밋 아이디]
git tag : 모든 태그 조회
git show [태그 이름] : 태그에 연결된 커밋 조회
git log : 커밋 히스토리를 출력
git log --pretty=oneline : --pretty 옵션을 사용하면 커밋 히스토리를 다양한 방식으로 출력할 수 있습니다. --pretty 옵션에 oneline이라는 값을 주면 커밋 하나당 한 줄씩 출력해줍니다. --pretty 옵션에 대해 더 자세히 알고싶으면 이 링크를 참고하세요.
git show [커밋 아이디] : 특정 커밋에서 어떤 변경사항이 있었는지 확인
git commit --amend : 최신 커밋을 다시 수정해서 새로운 커밋으로 만듦
git config alias.[별명] [커맨드] : 길이가 긴 커맨드에 별명을 붙여서 이후로 별명으로 해당 커맨드를 실행할 수 있도록 설정
git diff [커밋 A의 아이디] [커밋 B의 아이디] : 두 커밋 간의 차이 비교
git reset [옵션] [커밋 아이디] : 옵션에 따라 하는 작업이 달라짐(옵션을 생략하면 --mixed 옵션이 적용됨)
(1) HEAD가 특정 커밋을 가리키도록 이동시킴(--soft는 여기까지 수행)
(2) staging area도 특정 커밋처럼 리셋(--mixed는 여기까지 수행)
(3) working directory도 특정 커밋처럼 리셋(--hard는 여기까지 수행)
그리고 이때 커밋 아이디 대신 HEAD의 위치를 기준으로 한 표기법(예 : HEAD^, HEAD~3)을 사용해도 됨
git tag [태그 이름] [커밋 아이디] : 특정 커밋에 태그를 붙임
git branch [새 브랜치 이름]: 새로운 브랜치를 생성
git checkout -b [새 브랜치 이름]: 새로운 브랜치를 생성하고 그 브랜치로 바로 이동
git branch -d [기존 브랜치 이름]: 브랜치 삭제
git checkout [기존 브랜치 이름]: 그 브랜치로 이동
git merge [기존 브랜치 이름]: 현재 브랜치에 다른 브랜치를 머지
git merge --abort: 머지를 하다가 conflict가 발생했을 때, 일단은 머지 작업을 취소하고 이전 상태로 돌아감
git checkout master
​
이 커맨드의 뜻은 다음과 같이 해석됩니다.
= master 브랜치로 이동하라
= HEAD가 master 브랜치를 가리키도록 하라
= HEAD가 master 브랜치가 가리키던 커밋을 간접적으로 가리키게 됨으로써
= working directory의 내부도 그 커밋에 맞게 변함으로써
= master 브랜치로 이동한 것을 사용자는 실감하게 됨
git reset
git checkout
HEAD가 가리키던 브랜치가 다른 커밋을 가리키도록 한다
HEAD 자체가 다른 커밋이나 브랜치를 가리키도록 한다
HEAD도 결국 간접적으로 다른 커밋을 가리키게되는 효과가 생긴다
브랜치를 통하지 않고, 커밋을 직접적으로 가리키는 HEAD를 Detached HEAD라고 한다
git fetch: 로컬 레포지토리에서 현재 HEAD가 가리키는 브랜치의 업스트림(upstream) 브랜치로부터 최신 커밋들을 가져옴(가져오기만 한다는 점에서, 가져와서 머지까지 하는 git pull과는 차이가 있음)
git blame: 특정 파일의 내용 한줄한줄이 어떤 커밋에 의해 생긴 것인지 출력
git revert: 특정 커밋에서 이루어진 작업을 되돌리는(취소하는) 커밋을 새로 생성
6. Git 실전 I
git fetch : 로컬 레포지토리에서 현재 HEAD가 가리키는 브랜치의 업스트림(upstream) 브랜치로부터 최신 커밋들을 가져옴(가져오기만 한다는 점에서, 가져와서 머지까지 하는 git pull과는 차이가 있음)
git blame : 특정 파일의 내용 한줄한줄이 어떤 커밋에 의해 생긴 것인지 출력
git revert : 특정 커밋에서 이루어진 작업을 되돌리는(취소하는) 커밋을 새로 생성
7. Git 실전 Ⅱ
git reflog : HEAD가 그동안 가리켜왔던 커밋들의 기록을 출력
git log --all --graph : 모든 브랜치의 커밋 히스토리를, 커밋 간의 관계가 잘 드러나도록 그래프 형식으로 출력
git rebase [브랜치 이름] : A, B 브랜치가 있는 상태에서 지금 HEAD가 A 브랜치를 가리킬 때, git rebase B를 실행하면 A, B 브랜치가 분기하는 시작점이 된 공통 커밋 이후로부터 존재하는 A 브랜치 상의 커밋들이 그대로 B 브랜치의 최신 커밋 이후로 이어붙여짐(git merge와 같은 효과를 가지지만 커밋 히스토리가 한 줄로 깔끔하게 된다는 차이점이 있음)
git stash : 현재 작업 내용을 스택 영역에 저장
git stash apply [커밋 아이디] : 스택 영역에 저장된 가장 최근의(혹은 특정) 작업 내용을 working directory에 적용
git stash drop [커밋 아이디] : 스택 영역에 저장된 가장 최근의(혹은 특정) 작업 내용을 스택에서 삭제
git stash pop [커밋 아이디] : 스택 영역에 저장된 가장 최근의(혹은 특정) 작업 내용을 working directory에 적용하면서 스택에서 삭제
git cherry-pick [커밋 아이디] : 특정 커밋의 내용을 현재 커밋에 반영
그 밖에 알아야할 사실
(1) git commit이라고만 쓰고 실행하면 커밋 메시지를 입력할 수 있는 텍스트 에디터 창이 뜹니다. 거기서 커밋 메시지를 입력하고 저장하고 나면 커밋이 이루어집니다.
(2) git push와 git pull은 그 작업 단위가 브랜치입니다. 예를 들어, master 브랜치에서 git push를 하면 master 브랜치의 내용만 리모트 레포지토리의 master 브랜치로 전송되지, premium 브랜치의 내용이 전송되는 것은 아닙니다.(git push에 --all이라는 옵션을 주면 모든 브랜치의 내용을 전송할 수 있기는 합니다.)
*git 컨벤션 / code 컨벤션 : 커밋메세지, 변수 명 등 규칙을 정함
