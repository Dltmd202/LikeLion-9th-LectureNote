# 👨🏽‍💻9주차!

***

## 9.2 터미널 사용법 1

***

### 9.2.1 명령어 구조

​	__명령어__ [옵션] [인자...]

* 옵션

  "-"로 시작해서 영문 대소문자로 구성 명령어의 기능을 구체화

* 인자

  명령어 수생시 대상이 될 파일이나 디렉터리 명령어에 따라 필요 없을 수도 있고 필요할 수도 있다.

***

### 9.2.2 필수 명령어

* pwd

  Print Working Directory

  현재 위치를 알려준다.

  ```ba
  pwd
  ```

  

* man

  manual

  명령어 설명서

  man [알고싶은 명령어]

  ```
  man pwd
  ```

* ls

  list

  디렉터리의 목록을 보여준다

  1. 옵션 a

     숨김파일까지 보여줌

  2. 옵션 ㅣ

     상세하게 보여줌

  3. 옵션 f

     파일인지 디렉터리인지 알려줌

  ```bash
  ls
  ls -l
  ls -al
  ls /
  ```

* cd

  change Directory

  현재 위치를 이동해줌

  cd [이동하고자 하는 위치]

  ```bash
  cd 1
  cd ..
  cd /Library
  ```

* clear

  터미널 청소기

***

### 9.2.3 부가 설명

* history

  지금까지 사용한 명령어를 불러옴

  ```
  history
  ```