# Git

**기초가 가장 중요하다.** 개발자가 되기 위한 기초중의 기초, Git을 공부했습니다.

## 1. Git이란?

Git은 버전 관리 시스템중 하나이다.

버전 관리 시스템은 파일 변화를 시간에 따라 기록했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템이다.

*우리는 왜 버전을 관리해야할까?*  
(VCS - Version CControl System)

버전 관리를 하게된다면 각 파일을 이전 상태로 되돌릴 수 있고, 프로젝트를 통째로 이전 상태로 되돌릴 수 있고, 시간에 따라 수정 내용을 비교해 볼 수 있고, 누가 문제를 일으켰는지도 추적할 수 있고, 누가 언제 만들어낸 이슈인지도 알 수 있다. VCS를 사용하면 파일을 잃어버리거나 잘못 고쳤을 때도 쉽게 복구할 수 있다.

#### 그렇다면 Git 말고 다른 버전 관리 시스템은 없을까?
*있다!*
 
바로 **SVN(Subversion)** 이라는 친구이다. 

Git 과 SVN의 차이는 무엇일까?

1. SVN : 중앙 서버에 소스코드와 히스토리를 저장<br>
    Git : 소스코드를 여러 개발 PC와 저장소에 분산해서 저장

    위의 이유 때문에 Git은 중앙 서버에 장애가 발생해도 로컬 저장소에 커밋을 할 수 있으며, 로컬 저장소들을 이용하여 중앙 저장소의 복원도 가능하다. 
2. 사본을 로컬에서 관리하기 때문에 GIT이 SVN에 비해 훨씬 빠르다.(SVN은 변경 로그 하나 보는 것도 인터넷을 경유해야 한다.)

***이러한 이유 때문에 사람들은 주로 Git을 사용한다.***

## 2. Git의 장점

Git의 장점으로는 어떤것이 있을까?

1. 소스코드를 주고 받을 필요 없이, 같은 파일을 여러 명이 동시에 작업하는 병렬 개발이 가능하다.
2. 분산 버전 관리이기 때문에 인터넷 연결이 되지 않은 곳에서도 개발을 진행할 수 있으며, 중앙 저장소가 날라가도 원상복구할 수 있다. 
3. 개발을 체계적으로 진행할 수 있으며, 배포하는 과정도 간편해진다.

![img](https://t1.daumcdn.net/cfile/tistory/998E643C5AA61E2D0F?original)
[사진 출처](http://pismute.github.io/whygitisbetter/images/local-remote.png)

## 3. Git에서 자주 나오는 용어 정리

1. <span style='background-color:#ffdce0'>**브랜치(Branch)**</span> : 모든 버전 관리 시스템은 브랜치를 지원한다. 개발을 하다 보면 코드를 여러 개로 복사해야 하는 일이 자주 생긴다. 코드를 통째로 복사하고 나서 원래 코드와는 상관없이 독립적으로 개발을 진행할 수 있는데, 이렇게 독립적으로 개발하는 것이 브랜치다.

2. <span style='background-color:#ffdce0'>**머지(Merge)**</span> : git branch를 다른 branch로 합치는 과정을 merge라 한다. merge의 기본 단위는 브랜치이며, git merge 명령어로는 커밋 단위로 합치기가 불가능하다. 

3. <span style='background-color:#ffdce0'>**충돌(Conflict)**</span> : git 에서 master의 branch를 만들고 작업을 하다보면, pull request 할 때 conflict(충돌)가 나는 경우가 있다. 이런 경우는 자신이 pull origin master를 한 후에 다른 작업자가 자신과 같은 라인을 수정하고, 그 수정한 내역을 master 와 합쳤을때(merge) 발생한다.

4. <span style='background-color:#ffdce0'>**풀 리퀘스트(Pull Request)**</span> : 풀리퀘스트(Pull Request)는 당신이 변경한 내용에 대해서 다른 사람들(동료)에게 말해준다. 투박하게 표현하면, "여러분! 제가 Commit을 했습니다. 특정 branch(주로 develop)에 Merge해도 될까요?" 라고 알리는 활동이 Pull Request이다.

5. <span style='background-color:#ffdce0'>**포크(Fork)**</span> : fork는 다른 사람의 Github repository에서 내가 어떤 부분을 수정하거나 추가 기능을 넣고 싶을 때 해당 respository를 내 Github repository로 그대로 복제하는 기능이다. 흔히 포크를 뜬다고 표현한다.

6. <span style='background-color:#ffdce0'>**클론(Clone)**</span> : 보통 클론(clone)은 원격 저장소에 있는 코드를 내 컴퓨터에 복제할때 사용한다. 클론(clone)은 원격 저장소에 있는 코드를 그대로 복제하기 때문에 직접 코드를 입력하는 번거로움을 해결 할 수 있다.

7. <span style='background-color:#ffdce0'>**커밋(Commit)**</span> : 코드의 변화를 기록하는 것을 커밋(commit) 이라고 한다.


![img2](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbmLHdw%2FbtqSAT8P41o%2FN4JI0Yw6DhX5vZQGhukBUk%2Fimg.png)
[사진출처](https://ebbnflow.tistory.com/260)