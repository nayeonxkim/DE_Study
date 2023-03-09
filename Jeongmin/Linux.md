# Linux

### SHELL (셸)

- 운영체제 상에서, 사용자와 커널 사이에 존재, 사용자의 명령을 해석하고 처리 결과를 출력

### 필수 명령어

- ls - 현재 위치의 파일 목록 조회
- cd - 디렉터리 이동
- touch - 0바이트 파일 생성, 파일의 날짜와 시간을 수정
- mkdir - 디렉터리 생성
- cp - 파일 복사
- mv - 파일 이동
- rm - 파일 삭제
- cat - 파일의 내용을 화면에 출력, 리다이렉션 기호('>')를 사용하여 새로운 파일 생성
- redirection - 화면의 출력 결과를 파일로 저장
- alias - 자주 사용하는 명령어들을 별명으로 정의하여 쉽게 사용할 수 있도록 설정

[마크다운 명령어 모음]([https://dora-guide.com/linux-commands/](https://dora-guide.com/linux-commands/))

- which - 현재 실행되는 명령어의 위치를 출력
- tail - 선택한 파일의 변화를 실시간 트래킹
- 다중 명령어
    - 세미콜론 (;)
    - &&, ||

### 환경 변수 $PATH

- /bin - 기본적인 명령어 - 일반 사용자
- /sbin - 시스템 관리위한 명령어 - root
- /usr/bin - /bin에 있는 명령을 제외한 기본적인 명령어 - 일반 사용자
- /usr/sbin - /sbin에 있는 명령을 제외한 시스템 관리를 위한 명령어 - root

### Shell Script

- 셔뱅(Shabang)
    - #! {인터프리터 위치}
    - 셸 스크립트 시작할 때 맨 처음에 기입
- 변수
    - 선언 VAR=
    - 사용 $VAR
    - 특수한 경우  ${VAR}
    - 매개변수 $0, $1, …, $*, $@
- 조건문, 비교연산자
    - if then~elif then ~fi
    - 정수: -eq, -ne, -gt, -lt, -ge, -le
    - 문자열: ==, !=, -z, -n
- 반복문
    - while 조건에 만족하면
    - for 지정된 범위 안
    - break, continue, exit로 제어
    