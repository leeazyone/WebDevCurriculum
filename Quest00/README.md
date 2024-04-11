# Quest 00. 형상관리 시스템

## Introduction

- git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics

- git
  - `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
  - `.git` 폴더
- GitHub

## Resources

- [Resources to learn Git](https://try.github.io)
- [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
- [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist

- **형상관리 시스템은 왜 나오게 되었을까요?**
  형상관리: 형상관리 또는 소프트웨어 구성 관리(SCM : Software Configuration Management)는 소프트웨어의 변경사항을 체계적으로 추적하고 통제하는 것
  -> 개발자의 입장에서 보았을 때 개발과 협업에서의 많은 불편함이 있어 생겨났다고 생각한다.

- **git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?**
  Git이란, 소스코드를 효과적으로 관리하기 위해 개발된 '분산형 버전 관리 시스템'이다. Git의 특징은 빠른 속도, 단순한 구조, 비선형적인 개발, 완벽한 분산 등이 있다. 분산형 형상관리 시스템은 다른 사람과 공유해 한다면 저장소에 푸쉬(push)를 하면 저장소를 공유하게 되는 방식이다.

  - **git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?**
    2005년에 커뮤니티가 만드는 Linux 커널과 이익을 추구하는 회사가 개발한 BitKeeper의 관계가 틀어졌다. BitKeeper의 무료 사용이 재고된 것이다. 이 사건은 Linux 개발 커뮤니티(특히 Linux 창시자 Linus Torvalds)가 자체 도구를 만드는 계기가 됐다. git이 분산형 시스템을 채택한 이유는 리눅스 창시자인 리누스 토르발스가 자신에게 맞는 접근이 자유로운 시스템을 찾다가 분산형 시스템을 선택하게 된 것이다.

- **git과 GitHub은 어떻게 다를까요?**
  git: 형상관리 툴
  github: git을 공유/업로드 할 수 잇는 눈에 보이는 웹 호스팅 서비스, 즉 플랫폼이다.

- **git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?**
  명령어의 앞에 git을 붙여 사용한다.

* git clone: 원격 저장소에 있는 프로젝트를 로컬 저장소로 가져오는 명령어
* git add: 작업 중인 파일들을 스테이징 상태로 변경하는 명령어
* git commit: 로컬 저장소에 있는 모든 파일에 대한 스냅샷을 기록하는 명령어
* git push: 로컬 저장소에서 작업한 후 커밋한 내용을 원격 저장소로 보내는 명령어
* git pull: 원격 저장소에 업로드 된 내용을 로컬 저장소로 가져오는 명령어
* git branch: 새로운 작업 공간을 만들어주는 명령어, 브랜치 목록보기, 생성, 삭제가 가능
* git stash: 작업 내용을 커밋하고 싶진 않지만 다른 곳에 두고 나중에 가져와서 쓰고 싶을 때 사용하는 저장소이자 명령어

- **git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?**

* Object: 파일들을 관리하기 위한 파일
* Commit: tree SHA-1값, parent 오브젝트의 SHA-1값, author, committer, commit message를 저장
* Head: 커밋을 가르키는 포인터와 같은 역할
* Branch: 작업 트리를 나타냄
* Tag: 특정 커밋에 태그를 달아주는 역할
  git 시스템이 히스토리를 저장하는 방식: git은 파일들을 관리하기 위해 파일을 만드는데 이를 Object라고 부르며 tree, blob, commit, tag 4가지로 이루어져있다.

- **리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?**
  -> git reset --hard commit id

## Quest

- GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
- Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  - 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
- 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
- `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced

- **Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?**
  -> 분산형 버전관리 시스템이고, 프로젝트에 비해 저장소의 규모가 완만하게 선형적으로 증가하지만 굉장히 안정적이다.

- **실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?**
  -> Git, Perforce, Subversion
