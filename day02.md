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

4. `git remote`
- 로컬 저장소에 원격 저장소를 `등록, 조회, 삭제`할 수 있는 명령어
   1. git remote add <이름> <주소>
   ```bash
   git remote add origin https://github.com/jiyeonil/TIL.git
   [풀이] 
   git 명령어를 작성할건데, remote(원격 저장소)에 add(추가)한다. 
   origin이라는 이름으로 https://github.com/jiyeonil/TIL.git라는 주소의 원격 저장소를


