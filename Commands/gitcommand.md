## git log --oneline
- 각 커밋을 한 줄로 간략히 표시 (커밋 해시 및 메시지만 출력)

## git reset HEAD
- 가장 최근에 add (.)로 추가한 모든 파일들을 staging area에서 제거시킴(언스테이징)

## gitignore

- .gitignore파일에 다음과 같은 내용을 넣으면, 굳이 add할 필요가 없는 파일들을 빼고 add .으로 staging area로 이동시킬 수 있습니다.

*.class
.vscode/
a.out
*.exe
.DS_Store

* git init : 현재 폴더를 Git 저장소로 초기화 (숨김 폴더 .git 생성)
* git clone [url] : 원격 저장소를 로컬에 복제 (다운로드)
* git add [파일] : 변경된 파일을 스테이지(Stage) 상태로 올림(commit 준비)
* git commit -m "메시지" : 스테이지에 올라간 변경사항을 로컬 저장소에 저장
* git status : 현재 작업 상태 확인 (추적 여부, 수정 여부 등)
* git log : 커밋 기록(히스토리)을 확인
* git branch : 브랜치 목록 확인 또는 브랜치 생성 (git branch new-bran)
* git checkout [브랜치명] : 특정 브랜치로 이동
* git checkout -b [브랜칭명] : 브랜치 생성 후 바로 이동
* git merge [브랜치] : 현재 브랜치에 다른 브랜치 내용을 병합(다른 브랜치의 변경 사항을 현재 브랜치로 병합)
* git remote : 원격 저장소 목록 확인 (예: origin)
* git remote add [별칭] [URL] : 원격 저장소 등록
* git fetch : 원격 저장소의 변경 사항을 가져오기만 함 (병합 안 됨)
* git pull : fetch + merge -> 원격 저장소의 변경 사항을 가져오고 병합
* git push : 로컬 저장소의 커밋 내용을 원격 저장소에 업로드
* git reset : 커밋이나 스테이지 상태를 이전으로 되돌림(주의 필요)
* git revert [커밋ID] : 지정한 커밋을 취소하는 새 커밋을 생성(기록 보존)
* git show [커밋ID] : 특정 커밋의 상세 정보 보기
* git remove [파일] : Git 추적 대상에서 파일 제거 (git rm)와 동일한 의미로 보임