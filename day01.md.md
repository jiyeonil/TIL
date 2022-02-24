# 2022.02.23 GIT HUB 특강

## 1) CLI 기초

## [1] Git 설치

1. git 설치 후 탐색기를 엽니다. (`윈도우 +e키`)
2. `C://users/유지연` 계정으로 이동합니다.
3. 폴더 내 빈 공간에서 마우스 우클릭 후 `git bash here`을 클릭합니다.
4. git bash창에 HOME폴더를 의미하는 `~`만 있다면 정상!



## [2]Git vs CLI

### (1) GUI와 CLI의 정의

![화면](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Ff889708b-b1fb-4087-bffb-8253c6f007df%2FUntitled.png?table=block&id=fd7d183f-f862-48ad-8df8-3d9232a882e2&spaceId=daa2d103-3ecd-4519-8c30-4f55e74c7ef4&width=1490&userId=7d87deec-743b-4f06-8160-c1171916ff9e&cache=v2)

> 왼쪽이 GUI, 오른쪽이 CLI입니다. 화면에 나타나는 모습만 다를 뿐, 결국 같은 일을 합니다.

1. `GUI (GRAPHIC USER INTERFACE)`: 그래픽을 통해 사용자와 컴퓨터가 상호작용하는 방식
2. `CLI(Command Line Interface)`: 터미널을 통해 사용자와 컴퓨터가 상호작용하는 방식

```markdown
interface(인터페이스)
인터페이스: 서로 다른 개체끼리 맞닿아 있는 면
> 여기에서는 사용자와 컴퓨터가 서로 소통하는 접점의 의미
```

### (2) CLI를 사용하는 이유

`new`라는 이름으로 새 폴더를 생성해 봅시다.

1. GUI를 사용하는 경우(4단계): 마우스 우클릭 -> 새로 만들기 -> 폴더 -> NEW 작성
2. CLI를 사용하는 경우(1단계): `mkdir 폴더명`

GUI는 CLI에 비해 사용하기 쉽지만, 단계가 많고 컴퓨터의 성능을 더 많이 소모합니다.

그리고 CLI는 GUI로는 불가능한, 많은 세부적인 기능을 사용할 수 있습니다.

```markdown
# 그렇다면 GUI가 존재하는 이유는?
많은 사람들이 쉽게 컴퓨터를 사용할 수 있음(사용하기 쉬움)
```

### (3) Git Bash를 사용하는 이유

Windows에는 CLI환경인 `Powershell`과 `명령프롬프트` 가 이미 존재합니다.

하지만 왜 Git Bash라는 것을 사용할까요?

1. **명령어의 통일을 위해서 입니다.**

   - UNIX계열 운영체제의 명령어와 Windows의 명령어의 차이가 존재
   - 따라서 Git Bash라고 하는 일종의 번역기를 통해 windows에서도 unix계열 운영체제의 터미널 명령어를 사용하기 위함입니다.

2. **UNIX계열 운영체제의 명령어를 더 많이 쓰기 때문입니다.**

   - 개발자 입장에서는 Windows보다는 UNIX계열 운영체제 기반의 프로그램이 훨씬 많습니다.
   - 그만큼 개발 시장에서는 UNIX계열 운영체제가 더 많이 사용되기 때문에, `GIT BASH`를 통해서 UNIX계열 운영체제의 터미널 명령어를 연습합니다.

   

## [3] 경로

### (1) 루트, 홈 디렉토리

1. 루트 디렉토리(Root Directory, `/`)
   - 모든 파일과 폴더를 담고 있는 최상위 폴더 입니다.
   - Windows의 경우, 보통 `c드라이브`를 의미합니다.
2.  홈 디렉토리(Home Directory, ~)
   - Tilde(틸드)라고도 부르며, 현재 로그인 된 사용자의 홈 폴더를 의미합니다.
   - Windows의 경우, `c://사용자(users)//현재 사용자 계정`을 의미합니다.

```markdown
# 폴더 vs 디렉토리
거의 같은 의미로 사용되기 때문에 구분이 무의미
그러나, 윈도우 탐색기 특수 폴더(ex.네트워크 환경, 내컴퓨터 등)는 폴더이지만 디렉토리는 아님.
> 폴더가 디렉토리보다 넓은 개념
```

### (2) 절대경로와 상대경로

1. **절대 경로**: 루트 디렉토리부터 목적 지점까지 거치는 모든 경로를 전부 작성한 것

   - 윈도우 바탕화면의 절대 경로 ex) 경기도 하남시 신우실로 15 ~

     `C:/Users/kyle/Desktop`

2. **상대 경로**: 현재 작업하고 있는 디렉토리를 기준으로 계산된 상대적 위치를 작성한 것

   - 현재 작업하고 있는 디렉토리가 `C:/Users`라고 한다면
   - 윈도우 바탕화면의 상대경로는 `kyle/Desktop`이 됩니다. ex) 철수 윗 집
   - 간결해서 좋지만, 현재 작업하고 있는 디렉토리가 변하면, 상대경로도 변경됩니다.
   - `./`: 현재 작업하고 있는 폴더를 의미
   - `../`: 현재 작업하고 있는 폴더의 부모 폴더를 의미합니다. 

   

## [4] 터미널 명령어

1. `touch`

   - <u>파일을 생성하는 명령어</u> 

     - 폴더는 mkdir 폴더명

   - 띄어쓰기로 구분하여 여러 파일을 한꺼번에 생성합니다.

     ```bash
     touch a.txt b.txt c.txt
     ```

   - 숨김파일을 만들기 위해서는 `.`을 파일명 앞에 붙입니다.

2. mkdir

   - make directory
   - <u>새 폴더를 생성하는 명령어</u>
   - 띄어쓰기로 구분하여 여러 폴더를 한꺼번에 생성 가능합니다.
   - 폴더 이름 사이에 공백을 넣고 싶다면, `따옴표`로 묶어서 입력합니다.
     - 다만, 오류가 날 수 있기 때문에 공백보다는 _를 추천

```bash
mkdir folder
mkdir "happy ending"
```

3. `ls`
   - list segments
   - <u>현재 작업 중인 디렉토리의 폴더/파일 목록을 보여주는 명령어</u>
   - `-a`: all 옵션. 숨김파일까지 모두 보여줍니다ㅣ
   - `-l`: long 옵션. 용량, 수정날짜 등 파일 정보를 자세히 보여줍니다.

```bash
#기본 사용
ls
#all 옵션
ls -a
#all, long 옵션 함께 적용
ls -a -l #띄어쓰기 각각 1번씩
#여러 옵션 축약 가능
ls -al
```

4. `mv`

   - move

   - <u>폴더/파일을 다른 폴더 내로 이동하거나 이름을 변경하는 명령어</u>

   - 작성한 폴더가 있어야 그 폴더로 이동. 없으면 이름이 바뀝니다.

     > `move (텍스트))파일 없는 폴더` 로 입력했다면 
     >
     > 텍스트파일이 그냥 빈 파일(형식無)로 되어버림

```bash
#text.txt를 folder 폴더 안에 넣을 때
mv text.txt folder
#text1.txt의 이름을 text2.txt로 바꿀 때
mv text1.txt text2.txt
```

5. `CD`
   - change directory
   - 현재 작업 중인 디렉토리를 변경하느 명령어
   - `cd~` or `cd`를 입력하면 홈 디렉토리로 이동합니다.
   - `cd ..`를 입력하면 부모 디렉토리로 이동합니다.(위로 가기)
   - `cd -`를 입력하면 바로 전 디렉토리로 이동합니다.(뒤로 가기)

```bash
#현재 작업 중인 디렉토리에 있는 folder
cd folder
#절대 경로를 통한 디렉토리 변경
cd C:/Users/kyle/Desktop
#상대 경로를 통한 디렉토리 변경
cd ../parent/child
```

6. `rm`

   - remove
- 폴더/파일을 지우는 명령어
   - GUI와 달리 휴지통으로 바로 이동하지 않고, 바로 `완전 삭제`
- `*(asterisk, wildcard)`를 사용해서 `rm *.txt`라고 입력하면 txt 파일 전체를 다 지웁니다.
   - `-r`: recursive 옵션. 폴더를 지울 때 사용합니다.(재귀적)
- `-rf`: 강제 삭제 옵션

```bash
rm test.txt
rm -r folder
```

7. `start`
   - 폴더/파일을 여는 명령어
   - `windows`에서는 start를 사용

```bash
#windows
start test. txt
```

8. pwd
   - 현재 경로를 보여줌

8. **유용한 단축키**

- `위, 아래 방향키`: 과거에 작성했던 명령어 조회
- `tab`: 폴더/파일 이름 자동완성
- `ctrl + a`: 커서가 맨 앞으로 이동
- `ctrl + e`: 커서가 맨 뒤로 이동
- `ctrl + w`: 커서가 앞 단어를 삭제
- `ctrl + l `: 터미널 화면을 깨끗하게 청소(스크롤 올리면 과거내역 조회 가능)
- `ctrl + insert`: 복사
- `shift + insert`: 붙여넣기



---

***

## 2) visual Studio Code

## [3] Vscode 터미널 사용

> 지금까지는 Git Bash 혹은 Terminal과 폴더를 작업 폴더를 옆에 띄워두고 수업을 진행했습니다. ( 반갈이)
>
> 이제부터는 vscode에서 모든 수업과 실습을 진행합니다

### (1) 기본 터미널 지정

1. vscode 화면에서 터미널을 엽니다.

- `vscode 화면 상단 -> Terminal -> New Terminal`
- 혹은 단축키 `ctrl + `(백틱)`을 통해 터미널을 열고 닫을 수 있습니다.
  - tab키 위에 있음(물결 표시)

2. 기본 터미널을 `powershell -> Git bash`로 바꾸기

- 현재, 윈도우 vscode 터미널의 기본값은 powershell입니다.
- `아래 화살표 -> 기본 프로필 선택 -> 상단에 있는 Git Bash 클릭`

```bash
# 터미널을 닫을 때 x(닫기)와 휴지통의 차이
x(닫기)는 터미널의 내용은 유지하고 (가독성을 위해) 잠시 숨겨두는 것
휴지통은 터미널을 아예 삭제
```

### (2) vscode에서 터미널 명령어 사용해 보기

- CLI 수업에서 학습했던 터미널 명령어를 vscode에서 실습



---

***

## 3) Markdown

## [1] Typora 시작하기

```bash
# Typora 왜 쓰나요?
- typora는 마크다운 문법을 읽고 쓰기 위한 일종의 메모장입니다
- 마크다운 형태로 즉시 변환되기 때문에 직관적으로 글 작성이 가능해집니다.
- 목차, 표와 같은 복잡한 기능을 손쉽게 만들 수 있도록 도와줍니다.
- 특히 이미지 삽입과 관련해서 상당히 편리
```

## [2] Markdow

### (1) 마크다운이란?

- 일반 텍스트 기반의 경량 마크업(Markup) 언어
- 마크업을 더욱 쉽고 간단하게 사용하고자 만들어졌습니다.
- `.md` 확장자를 가지며, 개발과 관련된 많은 문서는 마크다운 형식으로 작성되었습니다.
- 개발 분야에서 `문서화`는 아주 중요한 능력이고, 마크다운은 그 토대가 됩니다.

```bash
# 마크업(Markup)이란 무엇인가요?
마크업 언어는 말 그대로 마크(Mark)로 둘러싸인 언어입니다.
여기서 마크(Mark)란 글의 역할을 지정하는 일종의 표시와 같습니다.
ex) HTM(Markup)L, HTML에서 제목을 표시할 때는 <h1>제목</hi>로 작성
```

### (2) 마크다운의 장점, 단점, 주의사항

1. **장점**
   - 문법이 객관적이고 쉽습니다.
   - 관리가 쉽습니다.
   - 지원가능한 플랫폼과 프로그램이 다양합니다.
2. **단점**
   - 표준이 없어, 사용자마다 문법이 상이할 수 있습니다.
   - 모든 HTML마크업 기능을 대신하지는 못 합니다.
3. **주의사항**
   - 마크다운의 본질은 글에게 역할을 부여하는 것!
   - 따라서, 역할에 맞는 마크다운 문법으로만 작성해야 합니다.
   - 예를 들면, 글씨의 크기를 키우고 싶다는 이유로 `내용`에 `제목`의 역할을 부여하면 안 됩니다.

### (3) 마크다운 문법

1. **제목**
   - `h1 ~ h6`에 해당하는 제목을 표현합니다.
   - `#`을 사용합니다.
   - 작성

```bash
# 제목1
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6
```

2. **목록(list)**
   - 순서가 없는 목록은 `_ * +`를 사용합니다.
   - 순서가 있는 목록은 `1. 2. 3.`을 사용합니다.
   - `tab`키를 사용하여 들여쓰기를 할 수 있습니다.
     - `shift +tab`을 사용하여 내어쓰기를 할 수 있습니다.
   - 작성

```bash
- 순서가 없는 목록
	- 서브 목록
	- 서브 목록
	
+ 순서가 없는 목록
	+ 서브 목록
	+ 서브 목록
	
* 순서가 없는 목록
	* 서브 목록
	* 서브 목록
	
> 전부 동그라미들로 나옴

1. 순서가 있는 목록
	1. 서브 목록
	2. 서브 목록
	
1. 혼합 해보기 1
	- 순서 없음
	_ 순서 없음
	* 순서 없음 # 순서없는 애들은 동그라미로 나옴
	
2. 혼합 해보기2
	1. 순서 있음
	- 순서 없음
	2. 순서 있음
	
> 나머지는 작성한 그대로 나옴
```

3. **강조**(Emphasis)

   - 글자의 스타일링을 표현

   1. *기울임*: `*글자*` 혹은 `_글자_`
   2. **굵게**: `**글자**` 혹은 `__글자__`

   > ***기울이고 굵게***: `***글자***`

   1. ~~취소~`: `~~글자~~`
   2. <u>밑줄</u>: `<u>글자</u>`

4. **코드**(Code)

   1. 인라인 코드: ``inline code``처럼 백틱을 통해 코드를 감싸줍니다.
   2. 블록 코드: ````python`처럼 백틱을 3번 입력하고 코드의 종류를 작성합니다.

5. **링크**(Links)

   - 클릭하면 해당 주소로 이동할 수 있는 링크를 표현합니다.
   - `[표시할 글자](이동할 주소)`의 형태로 작성합니다.

   > ex) [google](https://google.com)

6. **이미지**(Links)

   - 마크다운 문서에 이미지를 삽입할 수 있습니다.
   - url로 연결할 때는 `![대체 텍스트](이미지 주소) ` 형태로 작성합니다.
   - `복사 붙여넣기 할 때, assets에 저장됨`
   - `대체 텍스트`란 이미지를 정상적으로 불러오지 못 했을 때 표시되는 문구입니다.
   - 타이모라에서는 이미지 파일을 끌어와서 놓아도 자동 업로드 됩니다.

7. **인용**(Blockqoute)

   - 주석이나 인용문구를 표현합니다
   - `>`를 사용합니다. 개수에 따라 중첩가능

8. **표**(table)

   - 테이블(표)를 생성합니다.

   - `파이프(|)`와 `하이픈(-)`을 이용해서 행과 열을 구분합니다.

   - 테이블 양쪽 끝의 파이프(|)는 생략 가능합니다,

   - 헤더 셀을 구분할 때는 `3개 이상의 하이픈 (-)`이 필요합니다.

   - `타이포라에서는 ctrl + T를 통해서 쉽게 표 생성이 가능합니다. #그냥 이거 사용`

   - 행을 늘릴 때는 `ctrl + enter`를 누릅니다.

9. **수평선**(Horizontal Rule)

   - 구분 선을 생성합니다

   - `- * _`을 3번 이상 연속으로 작성

     

💓💓💓

[마크다운 참고 사이트](https://www.notion.so/hphk/Git-5-_E-22-02-23-22-02-25-1b97e73779554044b56f15cd57693e9a?p=6b05ae8ddc624060a81e317d1c868589)





## 4) git 기초

### [1] git 초기 설정

> 최초 한 번만 설장합니다. 매번 git을 사용할 때마다 설정할 필요가 없습니다.

1. 누가 커밋을 남겼는지 확인할 수 있도록 이름과 이메일을 설정합니다.

   작성자를 수정하고 싶을 때에는 이름, 메일 주소만 다르게 하여 동일하게 입력합니다.

```bash
git config --global user.name "이름"
git config --global user.email "메일"

#작성자가 올바르게 설정되었는지 확인하는 법
git config --global -l
또는
git config --global --list
```



1. git의 3공간

   - 분장실, 무대 사진 촬영본

   - working directory, staging area, commits

   1. `Working Directory(= Working Tree)` : 사용자의 일반적인 작업이 일어나는 곳

   2. `Staging Area(= index)`: 커밋을 위한 파일 및 폴더가 추가되는 곳`
   3. `Repository`: staging area에 있던 파일 및 폴더의 변경사항(커밋)을 저장하는 곳
   4. GIT은 Working Directory -> Staging Area -> Repository의 과정으로 버전 관리를 수행합니다.



1. git init 

   - 현재 작업 중인 디렉토리를 Git으로 관리한다는 명령어

   - `.git`이라는 숨김 폴더를 생성하고, 터미널에는 `(master)`라고 표기됩니다.

     ```bash
     # 주의사항
     1. 중첩금지: 이미 git 저장소인 폴더 내에 또 다른 git 저장소를 만들지 않습니다. 즉, 맨 처음 1회만, 터미널에 이미 (master)가 있다면 git init을 절대 입력하면 안 됩니다.
     > 중첩돼서 잘 작동하지 않기 때문입니다.
     2. 절대로 홈 디렉토리에서 git init을 하지 않습니다. 터미널의 경로가 `~`인지 확인합니다.
     > 과부하가 걸리기 때문입니다,
     ```

     

2. git status: 파일의 상태를 확인(untracted, modified, index)

```bash
git status
or branch master

no comits yet

nothing to commit (create/copy files and use "git add" to track)
```

- working directory와 staging area에 있는 파일의 현재 상태를 알려주는 ㅁ녕령어

- 어떤 작업을 시행하기 전에 수시로 status를 확인하면 좋습니다.

- 상태

  - 1. `untracked`: Git이 관리하지 않는 파일 

       > 한번도 Staging Area에 올라간 적이 없는 파일

    2. `Tracked`: Git이 관리하는 파일

       1. `Unmodifed`: 최신 상태
       2. `Modified`: 수정되었지만 아직 Staging Area에 반영하지 않은 상태
       3. `Staged`: Staging Area에 올라간 상태

  ![파일의 라이프사이클](2022.02.23 GIT HUB 특강.assets/image-20220224100505434.png)

3. git add

```bash
#특정 파일
git add a.txt

#특정 폴더
git add my_folder/

#현재 디렉토리에 속한 파일/폴더 전부
git add .
```

- Working Directory에 있는 파일을 Staging Area로 올리는 명령어
- Git이 해당 파일을 추적(관리)할 수 있도록 만듭니다.
- `Untracked, Modified -> Staged`로 상태를 변경합니다.

```bash
# 예시
touch a.txt b. txt

git status
On branch master

No commits yet

Untracked files: # 트래킹되고 있지 않는 파일 목록
	(use "git add <file>..." to include in what will be commiteed)
				a.txt
				b.txt
				
nothing added to commit but untracked files present (use "git add" to track)

#a.txt만 Staging Area에 올립니다.
git add a.txt

git status
On branch master
Nocommits yet
Changes to be committed: #커밋 예정인 변경사항(Staging Area)
	(use "git rm --cached <file>..." to unstage)
				new file : 	a.txt

untracked files: #트래킹 되고 있지 않은 파일
	(use "git add <file>..." to include in what will be committed)
			b.txt
```

4. git commit

```bash
git commit -m "first commit"
[master (root-commit) c02659f] fitst commit
1 file changed, - insertions(+), 0 deletions(-)
 create mode 100644 a.txt
```

- Staging Area에 올라온 파일의 변경사항을 하나의 버전(커밋)으로 저장하는 명령어
- `커밋메세지`는 현재 변경 사항들을 잘 나타낼 수 있도록 `의미`있게 작성하는 것을 권장합니다.
- 각각의 커밋은 `SHA-1`알고리즘에 의해 반환된 고유의 해시값을 ID로 가집니다.

- git commit -m "메시지"
- 
- git log: 기록(커밋)들의 내역을 보여줌
  - --online: 한 줄 출력(전부 보기엔 너무 길음)

- git config --global --unset user.name(or mail): 입력했던 이름(or 메일) 정보 삭제



# TIL

`Today I Learned` : 하루하루 배웠던 내용을 기록하는 repository

 