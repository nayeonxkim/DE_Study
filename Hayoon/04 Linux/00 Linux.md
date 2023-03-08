# Linux

---

- 컴퓨터 OS 커널의 일종인 리눅스 커널, 또는 리눅스 커널을 사용하는 운영체제를 가리키는 말이기도 하다. 소스 코드가 공개되어 있는 대표적인 오픈 소스 소프트웨어다. 컴퓨터 역사상 가장 많은 참여자가 관여하고 있는 오픈 소스 프로젝트다.
- 데스크톱/랩톱 용도뿐만 아니라 웹 서버, 클라우드 컴퓨팅, 모바일 기기, 임베디드 기기 등 여러 분야에서 폭넓게 사용되고 있다.
- 구성요소
    - 커널 : 하드웨어와의 통신을 담당한다.
    - 디스플레이 서버 : 클라이언트와의 입출력을 담당하며 화면을 표시하는 기초적인 부분이다.
    - 윈도우 매니저 : 커널과 창, 그리고 창과 창 사이의 통신을 관리한다.
    - 디스플레이 매니저 : 디스플레이 서버와 데스크톱 환경을 시동시키고 사용자 로그인을 관리한다.
    - UI/UX 툴킷 : 유저 인터페이스 UI를 구성하기 위해 사용되는 프로그래밍 툴이다.
    - 데스크톱 환경 : 사용자가 위와 같은 기술적인 내용을 몰라도 사용할 수 있게끔 세트로 묶고 일관된 경험을 제공한다. 일반적으로 운영체제를 설치하고 볼 수 있는 것들이 데스크톱 환경이다.
- GUI(Graphical User Interface) :
한 화면에 많은 정보를 담을 수 있다. 눈으로 보고 대상을 선택 가능
- CLI(Command-Line Interface) :
터미널로 명령어를 통해 제어한다. 리눅스를 잘 다룬다는 것은 리눅스 환경에서 파일, 프로그램을 얼마나 잘 다루는가 그리고 CLI 환경이 얼마나 익숙한가 이다.

![https://www.channelfutures.com/files/2008/05/difficulty-divide-1_0.png](https://www.channelfutures.com/files/2008/05/difficulty-divide-1_0.png)

- Linux Family

![http://1.bp.blogspot.com/-csXvkovQT2s/TrR7QpoFtYI/AAAAAAAAFOA/hM59099HFes/s1600/distros_gnu.png](http://1.bp.blogspot.com/-csXvkovQT2s/TrR7QpoFtYI/AAAAAAAAFOA/hM59099HFes/s1600/distros_gnu.png)

- Linux 시작하기
    - AWS에서 인스턴스 생성
    - 독립 실행형 SSH 클라이언트로 연결
        - SSH(Secure Shell) :
        원격으로 다른 컴퓨터에 연결할 수 있도록 해주는 프로그램 + 보안 연결
        - Port :
        목적지(Host)의 프로세스에 연결하기 위한 구분
    - SSH Key Pair
        - Private Key
        - Public Key
    - 접속
    - SHELL :
    운영체제 상에서, 사용자와 커널 사이에 존재, 사용자의 명령을 해석하고 처리결과를 출력해주는 프로그램
        - 종류 : bash, zsh, csh, ksh
- 기본 명령어
    - 다 외우지는 못 한다. 자주 쓰는 것과 중요한 명령어는 외우자
- 리눅스 이해
    - Sudo :
    시스템의 중요한 부분을 변경하거나 업데이트 해야 할 때 Root 계정 접속을 남발하면 보안상 좋지 않으니 일시적으로 Root의 권한을 위임 받을 수 있는 방법
- Shell Script : 셸 위에서 실행 가능한 명령어를 조합해서 작업을 자동화 하기 위해 사용
(귀찮아서 사용하는 것임)
- Python 개발환경 설정