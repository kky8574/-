# git 명령어


### 전역 설정 정보 조회
>  git config - -global - -list

### 전역 설정 정보 삭제시키기
> git config --global --unset-all user.email

> git config --global --unset-all user.name



### 새로운 저장소 초기화하기
> git init

### 저장소 복제하기
>  git clone <저장소 url>

### 새로운 원격 저장소 추가하기
>  git remote add <원격 저장소> <저장소 url>

### 새로운 파일 git에 등록시키기(staging)
> git add <파일>

### 현재까지 작업한 내용 저장하기

> git commit -m “<메시지>”


### 원격 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
> git fetch <원격 저장소>

### 원격 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
> git pull <원격 저장소>

### 새로운 로컬 브랜치를 원격 저장소에 푸싱하기
> git push <원격 저장소> <지역 브랜치>

### 새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기
> git add <파일>

> git commit -m “<메시지>”

### 파일의 일부를 스테이징하기
> git add -p [<파일> [<파일> [기타 파일들…]]]

### add 명령에서 Git 대화 모드를 사용하여 파일 추가하기
> git add -i

### 수정되고 추적되는 파일의 변경 사항 스테이징하기
> git add -u [<경로> [<경로>]]

### 수정되고 추적되는 모든 파일의 변경 사항 커밋하기
> git commit -m “<메시지>” -a

### 작업 트리의 변경 사항 돌려놓기
> git checkout HEAD <파일> [<파일>]

### 커밋되지 않고 스테이징된 변경 사항 재설정하기
> git reset HEAD <파일> [<파일>]

### 마지막 커밋 고치기
> git commit -m “<메시지>” - -amend

### 이전 커밋을 수정하고 커밋 메시지를 재사용하기
> git commit -C HEAD - -amend
