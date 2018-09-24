git 명령어
===============

## 1. 설정과 초기화

### 전역 설정 정보 조회
> git config - -global - -list

### 전역 설정 정보 삭제시키기
> git config --global --unset-all user.email

> git config --global --unset-all user.name

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

<br></br>
## 2. 기본적인 사용법

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

<br> </br>
## 3. 브랜치

### 지역 브랜치 목록 보기
> git branch

### 원격 브랜치 목록 보기
> git branch -r

### 지역과 원격을 포함한 모든 브랜치 목록 보기
> git branch -a

### 현재 브랜치에서 새로운 브랜치 생성하기
> git branch <새로운 브랜치>

### 다른 브랜치 체크아웃하기
> git checkout <브랜치>

### 현재 브랜치에서 새로운 브랜치 생성하고 체크아웃하기
> git checkout -b <새로운 브랜치>

### 다른 시작 지점에서 브랜치 생성하기
> git branch <새로운 브랜치> <브랜치를 생성할 위치>

### 기존의 브랜치를 새로운 브랜치로 덮어쓰기
> git branch -f <기존 브랜치> [<브랜치를 생성할 위치>]

### 브랜치를 옮기거나 브랜치명 변경하기
> git checkout -m <기존 브랜치> <새로운 브랜치>
* <새로운 브랜치>가 존재하지 않을 경우
> git checkout -M <기존 브랜치> <새로운 브랜치>
* 무조건 덮어쓰기

### 다른 브랜치를 현재 브랜치로 합치기
> git merge <브랜치>

### 커밋하지 않고 합치기
> git merge - -no-commit <브랜치>

### 선택하여 합치기
> git cherry-pick <커밋명>

### 커밋하지 않고 선택하여 합치기
> git cherry-pick -n <커밋명>

### 브랜치의 이력을 다른 브랜치에 합치기
> git merge - -squash <브랜치>

### 브랜치 삭제하기
> git branch -d <삭제할 브랜치>
* 삭제할 브랜치가 현재 브랜치에 합쳐졌을 경우에만
> git branch -D <삭제할 브랜치>
* 삭제할 브랜치가 현재 브랜치에 합쳐지지 않았어도

<br></br>
## 4. git 이력

### 모든 이력 보기
> git log

### 변경 사항을 보여주는 패치와 함께 로그 표시하기
> git log -p

### 1개의 항목만 보이도록 로그 개수 제한하기
> git log -1

### 20개의 항목과 패치만 보이도록 로그 제한하기
> git log -20 -p

### 6개월 동안의 커밋 로그 보기
> git log - -since=”6 hours”

### 이틀 전까지의 커밋 로그 보기
> git log - -before=”2 days”

### HEAD보다 세 개 이전의 커밋 로그 보기
> git log -1 HEAD-3
> git log -1 HEAD^^^
> git log -1 HEAD~1^^

### 두 지점 사이의 커밋 로그 보기
> git log <시작 지점>…<끝 지점>
* 시작 지점이나 끝 지점은 커밋명, 브랜치명, 혹은 태그명이 될 수 있고 조합하여 사용 가능하다.

### 각 항목의 로그 이력 한 줄씩 보기
> git log - -pretty=oneline

### 각 항목마다 영향 받은 줄의 통계 보기
> git log - -stat

### 커밋할 시점의 파일 상태 보기
> git log - -name-status

### 현재 작업 트리와 인덱스의 차이점 보기
> git diff

### 인덱스와 저장소의 차이점 보기
> git diff - -cached

### 작업 트리와 저장소의 차이점 보기
> git diff HEAD

### 작업 트리와 특정 위치 간의 차이점 보기
> git diff <시작 지점>
* 시작 지점은 커밋명 or 브랜치명 or 태그명이다.

### 저장소의 두 지점 사이의 차이점 보기
> git diff <시작 지점> <끝 지점>

### 차이점의 통계 보기
> git diff - -stat <시작 지점> [<끝 지점>]

### 파일의 커밋 정보 줄 단위로 보기
> git blame <파일>

### 파일의 줄 단위의 복사, 붙여 넣기, 이동 정보 보기
> git blame -M <파일>

### 파일의 줄 단위의 이동과 원본 파일 정보 보기
> git blame -C -C <파일>

### 로그에서 복사와 붙여 넣은 정보 보기
> git log -C -C -p -1 <특정 지점>

<br></br>
## 5. 원격 저장소

### 저장소 복제하기
> git clone <저장소>

### 마지막 200개의 커밋만 포함하여 저장소 복제하기
> git clone - -depth 200 <저장소>

### 새로운 원격 저장소 추가하기
> git remote add <원격 저장소> <저장소 url>

### 모든 원격 브랜치 목록 보기
> git branch -r

### 원격 브랜치에서 지역 브랜치 생성하기
> git branch <새로운 브랜치> <원격 브랜치>

### 원격 태그에서 지역 브랜치 생성하기
> git branch <새로운 브랜치> <원격 태그>

### origin 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
> git fetch

### 원격 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
> git fetch <원격 저장소>

### 원격 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
> git pull <원격 저장소>

### origin 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
> git pull

### 지역 브랜치를 원격 브랜치에 푸싱하기
> git push <원격 저장소> <지역 브랜치>:<원격 브랜치>

### 지역 브랜치를 동일한 이름의 원격 브랜치에 푸싱하기
> git push <원격 저장소> <지역 브랜치>

### 새로운 로컬 브랜치를 원격 저장소에 푸싱하기
> git push <원격 저장소> <지역 브랜치>

### 원격 저장소에서 쓸모가 없어진 원격 브랜치 제거하기
> git remote prune <원격 저장소>

### 원격 저장소를 제거하고 관련된 브랜치도 제거하기
> git remote rm <원격 저장소>

<br><br></br>
markdown 문법
=============

* Markdown은 텍스트 기반의 마크업언어로 2004년 존그루버에 의해 만들어졌으며 쉽게 쓰고 읽을 수 있으며 HTML로 변환이 가능하다. 특수기호와 문자를 이용한 매우 간단한 구조의 문법을 사용하여 웹에서도 보다 빠르게 컨텐츠를 작성하고 보다 직관적으로 인식할 수 있다. 

## 1. 헤더
* 큰제목: 문서 제목

This is an H1  

> =============

* 작은제목: 문서 부제목

This is an H2

> -------------

* 글머리: 1~6까지만 지원
```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
####### This is a 7.

## 2. BlockQuote
이메일에서 사용하는 ```>``` 블럭인용문자를 이용한다.
```
> This is a blockqute.
```
> This is a first blockqute.
>	> This is a second blockqute.
>	>	> This is a third blockqute.

이 안에서는 다른 마크다운 요소를 포함할 수 있다.
> ### This is a H3
> * List
>	```
>	code
>	```

## 3. 목록
### ● 순서있는 목록(번호)
순서있는 목록은 숫자와 점을 사용한다.
```
1. 첫번째
2. 두번째
3. 세번째
```
1. 첫번째
2. 두번째
3. 세번째

**현재까지는 어떤 번호를 입력해도 순서는 내림차순으로 정의된다.**
```
1. 첫번째
3. 세번째
2. 두번째
```
1. 첫번째
3. 세번째
2. 두번째


### ● 순서없는 목록(글머리 기호)
```
* 빨강
  * 녹색
    * 파랑

+ 빨강
  + 녹색
    + 파랑

- 빨강
  - 녹색
    - 파랑
```
* 빨강
  * 녹색
    * 파랑

+ 빨강
  + 녹색
    + 파랑

- 빨강
  - 녹색
    - 파랑

혼합해서 사용하는 것도 가능하다(내가 선호하는 방식)
```
* 1단계
    - 2단계
    	+ 3단계
            = 4단계
```

* 1단계
    - 2단계
    	+ 3단계
			= 4단계

## 4. 코드```<pre><code></code></pre>```
4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다.

> 한줄 띄어쓰면 인식이 제대로 안되는 문제가 발생하곤 합니다.

```
This is a normal paragraph:

    This is a code block.
end code block.
```

<code>
```
This is a normal paragraph:
    This is a code block.
end code block.
```
</code>

실제로 적용해보면,
This is a normal paragraph:

    This is a code block.
end code block.

## 5. 수평선```<hr/>```
아래 줄은 모두 수평선을 만든다. 마크다운 문서를 미리보기로 출력할 때 *페이지 나누기* 용도로 많이 사용한다.
```
* * *

***

*****

- - -

---------------------------------------
```

* * *

***

*****

- - -

---------------------------------------


## 6. 링크
* 참조링크

```
[link keyword][id]
[id]: URL "Optional Title here"

Link: [Google][googlelink]
[googlelink]: https://google.com "Go google"
```

Link: [Google][googlelink]
[googlelink]: https://google.com "Go google"

* 인라인 링크
```
syntax: [Title](link)
```
Link: [Google](https://google.com, "google link")

* 자동연결
```
<http://example.com/>
<address@example.com>
```

<http://example.com/>
<address@example.com>

## 7. 강조
```
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
++underline++
~~cancelline~~
```
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
++underline++
~~cancelline~~


## 8. 이미지
```
![Alt text](/path/to/img.jpg)
![Alt text](/path/to/img.jpg "Optional title")
```
![석촌호수 러버덕](http://cfile6.uf.tistory.com/image/2426E646543C9B4532C7B0)
![석촌호수 러버덕](http://cfile6.uf.tistory.com/image/2426E646543C9B4532C7B0 "RubberDuck")

사이즈 조절 기능은 없기 때문에 ```<img width="" height=""></img>```를 이용한다.


## 9. 표
* 표 만들기
```
Col1|Col2
---|---
aaa1|aaa2
bbbbb1|bbbbb2 
c1|c2
```
Col1|Col2
---|---
aaa1|aaa2
bbbbb1|bbbbb2 
c1|c2

* 표 정렬하기
```
| Header 1 | Header 2 | Header 3 |
| :-------- | :--------: | --------: |
| Left | Center | Right |
```
| Header 1 | Header 2 | Header 3 |
| :-------- | :--------: | --------: |
| Left | Center | Right |


## 10. 글자 기본 포맷
```
**Bold**
__Bold__
*Italic*
_Italic_
~~Cancel~~
```
**Bold**

__Bold__

*Italic*

_Italic_

~~Cancel~~






