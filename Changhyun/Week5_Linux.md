# week_5

복습: No
작성일시: 2023년 3월 6일 오후 9:15

## 리눅스와 친해지기

### 리눅스의 의미

리눅스는 리눅스 커널을 사용하는 Unix 계열 운영체제, 터미널을 통해 명령어로 컴퓨터를 조작

OS 내에 존재하는 커널을 이용해 하드웨어에 접근

### 인스턴스 접속(PuTTY)

인스턴트의 SSH client에서 ssh -i “pwd.pem” 이하의 문장을 복사하여 Host Name에 입력, 이름 설정

SSH - Auth - Credential에서 ppk파일 browse

open 실행

### 기본 명령어

- ls: 현재 상황(ls -l, ls -al)
- clear: 화면 깔끔하게 비우는 것
- alias: 단축키 지정
- mv: 파일 이동
- mkdir: 폴더 생성
- touch: 파일 생성
- cd ..: 상위 폴더
- cd -: 이전 폴더
- cp: 복사
- cd: 현재 위치 변경
- rm: 삭제
- rm -i: 물어보고 삭제
- rm -f, rm-rf: 강력한 삭제
- top: 현재 프로세스 상황
- htop: 좀 더 깔끔한 프로세스 상황
- q 누르면 나가짐
- ps: 현재 프로세스
- du: 용량을 얼마나 차지하는지
- find: 원하는 파일 찾아오기
- man: 명령어 사전
- which: 명령어에 대한 정보
- echo ~: 출력값 지정
- cat: 출력
- tail: 다른 프로그램에서의 변화를 모니터
- 다중 명령어: 명령어; 명령어; 명령어 후 Enter
- &&, ||: 둘다 실행 혹은 되는것만 실행
- 명령어 | 서브 명령어: 명령어의 결과를 2차적으로 처리
- grep: 표준 출력에서 원하는 단어를 선별
- redirection: 표준 출력으로 발생한 결과를 파일로 저장
    - ps -ef > ./list.txt
    - echo asdf >> folder
    - cat text_file | grep “WARN” -n > ./warn_log.txt
- File descripotr: 표준 입출력, 에러를 숫자로 표현
    - 0, stdin, 표준 입력
    - 1, stdout, 표준 출력
    - 2, stderr, 표준 오류
- vi 편집기: 터미널 환경에서 사용하는 텍스트 편집기
    - command mode: esc를 누른 상태, 키보드 입력 x, 이미 만들어진 문서 수정
    - editor mode: command mode에서 i 혹은 a, 키보드 입력 가능
    - last line mode: command mode에서 :, 파일을 저장, 종료, 문서검색

### 유용한 Linux Tool

- apt-get: 필요한 패키지 및 프로그램을 설치할 수 있는 패키지 관리 도구
- htop: top을 좀 더 정돈되게 보여줌
- nohup: 스크립트가 터미널을 끄더라도 실행되도록 백그라운드로 실행
- screen: nohup을 통해 백그라운드로 돌아간 프로세스를 다시 볼 수는 없지만 screen을 띄워 실행하면 세션을 다시 볼 수 있도록 해줌

### 계정과 권한

r(read): 읽을 수 있는 권한

w(write): 수정, 삭제 등 권한

x(execute): 실행 권한

—-, —x, -w-, r—, -wx, rw-, r-x, rwx(0~7)

ex. chmod 755

소유자의 권한, 그룹의 권한, 소유자가 아닌 사람의 권한을 구분함

- sudo: 임시로 root의 권한을 위임받을 수 있는 방법 → root 계정 접속을 남발하지 않도록 해줌

### 환경변수 $path

프로그램 실행 시 자동으로 참조하는 절대경로의 모음

/bin, /sbin, /usr/bin, /usr/sbin

### 쉘 스크립트

반복적인 작업을 자동으로 할 수 있음

- 셔뱅(shabang)

쉘 스크립트 시작 시 맨 처음에 기입(ex. #!/usr/bin/python3)

- 변수(variable)

선언: VAR=?, 사용은 $VAR, 특수한 경우 ${VAR}, 매개변수 $0, $1.. $*

- 조건문, 비교 연산자

if then ~ elif then ~ fi

정수 -eq, -ne, -gt, -lt, -ge, -le

문자열 ==, !=, -z, -n

- 반복문

while, for, break, continue, exit

### 파이썬 개발 환경

> 가상환경 툴
> 
- virtualenv: 프로젝트 폴더 안에 새 환경 생성
- pyenv: 특정 파이썬 버전 및 다른 가상환경 툴 구성
- Anaconda: 모두 알아서 해주고 Cuda 설치 가능