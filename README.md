# git 명령어

## 1.설정과 초기화
### 전역 설정 정보 조회
>  git config - -global - -list

### 전역 설정 정보 삭제시키기
> git config --global --unset-all user.email

> git config --global --unset-all user.name

### 전역 설정 정보 조회
> git config - -global - -list

### 저장소별 설정 정보 조회
> git config - -list

### Git의 출력결과 색상 활성화하기
> git config - -global color.ui “auto”

### 새로운 저장소 초기화하기
> mkdir /path/newDir
> cd /path/newDir
> git init

### 저장소 복제하기
> git clone <저장소 url>

### 새로운 원격 저장소 추가하기
> git remote add <원격 저장소> <저장소 url>

