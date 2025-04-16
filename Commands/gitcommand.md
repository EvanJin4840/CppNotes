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
