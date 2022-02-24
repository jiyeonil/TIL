# 2022.02.24 Git hub 특강

## [1] Github 가입하기

### (1) 회원 가입

[깃허브 회원가입](https://goddaehee.tistory.com/218)

### (2) Github 설정 변경

![상단프로필](2022.02.24 Git hub 특강.assets/image-20220224230652384.png)

1.  오른쪽 상단 프로필을 클릭합니다.

2. `settings`를 클릭합니다.

3. 왼쪽 안내 바에서 `Repositories`를 선택합니다.

4. `Repository default branch`의 입력창에서 `main`을 지우고 `master`로 작성합니다.

   > 인종차별 이슈로 master대신 main으로 바뀌었지만, 수업 진행 편의상 master 브랜치를 사용하도록 하겠습니다.

5. `update`를 클릭합니다.

### [2] 원격저장소(Remote Repository)
1.  여태까지는 내 컴퓨터라는 한정된 공간에 있는 로컬 저장소에서만 버전 관리를 진행했습니다.
2. 이제는 Gitnub의 원격저장소를 이용해 내 컴퓨터의 로컬 저장소를 다른 사람과 `공유`해 봅시다.
3. Github의 주요 목적 중 하나인 `협업`을 위해 로컬 저장소와 원격 저장소의 연동방법을 학습합니다.

### (1) Github에서 원격 저장소 생성
![](2022-02-24-23-18-47.png)]
1. 화면 오른쪽 상단 더하기(+) 버튼을 누르고 New Repository를 클릭합니다.
2. 저장소의 이름, 설명, 공개여부를 선택하고 create repository를 클릭합니다
> 체크박스는 건드리지 않습니다!

### (2) 로컬저장소와 원격 저장소 연결
1. 원격 저장소가 잘 생성되었는지 확인 후, 저장소의 주소를 복사합니다.
2. 기존 실습 때 만들었던 홈 디렉토리의 TIL 폴더로 가서 vscode를 엽니다.
3. git init을 통해 TIL 폴더를 로컬 저장소로 만들어 줍니다.
```bash
user@LAPTOP-OQJECPU4 MINGW32 ~/TIL
$ git init
Initialized empty Git repository in C:/Users/jiyeonil/TIL/.git/
```

4. `git remote`
- 로컬 저장소에 원격 저장소를 `등록, 조회, 삭제`할 수 있는 명령어
   1. `git remote add <이름> <주소>`형식으로 작성합니다.
   ```bash
   git remote add origin https://github.com/jiyeonil/TIL.git
   [풀이] 
   git 명령어를 작성할건데, remote(원격 저장소)에 add(추가)한다. 
   origin이라는 이름으로 https://github.com/jiyeonil/TIL.git라는 주소의 원격 저장소를
   ```
   2. 원격 저장소 조회
   `git remote -v`로 작성합니다.
   ```bash
   origin  https://github.com/edukyle/TIL.git (fetch)
   origin  https://github.com/edukyle/TIL.git (push)

   add를 이용해 추가했던 원격 저장소의 이름과 주소가 출력됩니다.
   ```
   3. 원격 저장소 연결 삭제
   `git remote rm <이름>` 혹은 `git remote remove <이름>`으로 작성합니다.
   > 로컬과 원격 저장소의 연결을 끊는 것이지, 원격 저장소 자체를 삭제하는 게 아닙니다.
   ```bash
   $ git remote rm origin
   $ git remote remove origin

   [풀이]
   git 명령어를 작성할건데, remote(원격 저장소)와의 연결을 rm(remove, 삭제)한다.
   그 원격 저장소의 이름은 origin이다.
   ```
### (3) 원격 저장소에 업로드
- 실습 때 작성했던 TIL파일을 Github 원격 저장소에 업로드해 보겠습니다.
- <u>정확히 말하면, 파일을 업로드하는 게 아니라 커밋을 업로드 하는 것입니다.</u>
- 따라서 먼저 로컬저장소에서 커밋을 생성해야 원격 저장소에 업로드 할 수 있습니다.
1. 로컬 저장소에서 커밋 생성
```bash
# 현재 상태 확인

$ git status
On branch master

No commits yet

Untracked files:
   (use "git add <file>..." to include in what will be committed)
        day2.md
   nothing added to commit but untracked files present (use "git add" to track)
```
```bash
$ git add day02.md
```
```bash
$ git commit -m "Upload TIL Day2"
[master (root-commit) f3d6d42] Upload TIL Day1
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 day1.md
```
```bash
# 커밋 확인

$ git log --online
f3d6d42 (HEAD -> master) Upload TIL Day2
```

2. git push
   - 로컬 저장소의 커밋을 원격 저장소에 업로드하는 명령어
   - `git push <저장소 이름> <브랜치 이름>`형식으로 작성합니다.
   - `-u` 옵션을 사용하면, 두 번째 커밋부터는 `저장소 이름, 브랜치 이름`을 생략가능합니다.
   ```bash
   $ git push origin master

   [풀이]
   git 명렁어를 사용할건데, origin이라는 원격 저장소의 master 브랜치에 push한다.

   ---

   $ git push -u origin master
   이후에는 $ git push 라고만 작성해도 push가 됩니다.
   ```

3. vscode 자격 증명
- 처음 로컬 저장소와 원격 저장소를 연결하는 경우, 본인 확인(로그인)창이 나옵니다.
- 로그인하고 Authorize GitCredential Manager를 클릭합니다.
- 이후 git push 완료
```bash
$ git push -u origin master
info: please complete authentication in your browser...
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 218 bytes | 218.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/edukyle/TIL.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```
4. 원격 저장소에 정상 업로드 확인

```python
(주의) Github 원격 저장소에 파일을 드래그해서 업로드하지 않습니다.

가끔 Github를 구글드라이브처럼 여겨서, 파일을 직접 드래그해서 올리는 경우가 있습니다.
반드시 git add -> git commit -m -> git push 의 단계로만 업로드 해야 합니다.

그 이유는 로컬 저장소와 원격 저장소의 동기화 때문입니다.

로컬 저장소에서 변경이 먼저 일어나고 원격 저장소에 변경 사항을 반영하는 형태여야 합니다. 
Github에 드래그를 해서 파일을 업로드하면 원격 저장소에서 변경이 먼저 일어나는 형태가 되기 때문에 지양해야 합니다.
```

5. git push를 그림으로 이해하기
![](2022-02-25-00-17-00.png)
> 로컬 저장소의 commit 이력이 원격 저장소에 그대로 반영됩니다.
