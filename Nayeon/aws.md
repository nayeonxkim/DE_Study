# AWS

### 기존 클라우드를 이용하지 않았던 전통적인 방식

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/b8950b90c08c4ee6840a792d8daebc8c/586b4fc3-92ba-4333-8c8f-ccfa85702d93.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/b8950b90c08c4ee6840a792d8daebc8c/586b4fc3-92ba-4333-8c8f-ccfa85702d93.png)

부터 재생11:02

서비스 트래픽은 우리가 예상할 수 없는 형태로 증감한다.

트래픽이 늘어나면 IT 인프라 자원 (서버, 스토리지, 네트워크 장비)도 따라서 늘리는 방식이었다.

- > 1) 트래픽이 급증한 경우, IT 인프라 자원이 그만큼 구축되어있지 않아 품질이 저하됨. 품질이 저하되며 고객 이탈이 발생할 수 있다.
- > 2) 트래픽이 감소한 경우, 증가한 IT 인프라 자원의 용량 낭비가 생김. IT인프라자원의 유용성(utilization)이 낮아진다.

### 클라우드 방식의 탄력적인 구조

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/b8950b90c08c4ee6840a792d8daebc8c/426aa008-50a0-4864-827f-91d3536b7905.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/b8950b90c08c4ee6840a792d8daebc8c/426aa008-50a0-4864-827f-91d3536b7905.png)

부터 재생13:06

증감하는 트래픽에 맞추어 확장성과 탄력성을 바탕으로  IT 리소스가 같이 늘어난다.

### 제약사항

시스템 요구사항이 클라우드에서 충분히 제공되는지 확인할 것

클라우드로 충족되지 않는 시스템 요구사항은 어떻게 극복해야할지 고민할 것

- 온프레미스 환경과 동일한 하드웨어/솔루션을 활용하는 것은 어렵다.

추상화된 자원을 활용하여 서비스를 딜리버리할 수 있어야한다.

- On-Premise (온프라미스) : 내부에 자체 구축 및 설치한 시스템 = 클라우드처럼 가상의 환경이 아니라 **기업의 서버를 자체적으로 보유하고 있는 서버에 직접 설치하고 운영하는 방식**

예) 데이터베이스 읽기 성능 확보 방법

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/b8950b90c08c4ee6840a792d8daebc8c/f012cb74-bad5-43e6-9f61-e83d0c1f56cc.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/b8950b90c08c4ee6840a792d8daebc8c/f012cb74-bad5-43e6-9f61-e83d0c1f56cc.png)

부터 재생17:52

- IDC : 온프레미스 환

DB의 직접적인 메모리 증설을 통해 성능을 확보하는 것이 아니라, 클라우드 앞단에 추상적인 서비스를 활용하여 성능을 확보한다.

### 가상화 시스템 관리자

시스템 관리자는 가상화 시스템 관리자의 역할도 수행해야한다.

서버, 스토리지, 네트워크 뿐만 아니라 추상화된 서비스또한 제어, 관리 및 제안할 수 있는 역량이 필요

### AWS의 이점

온디맨드 (오토스케일링) 서비스, 즉각적인 탄력성

비용 절감 효과

API를 바탕으로 개방성 및 유연성

보안

### AWS의 대표 솔루션

어플리케이션 호스팅 : 서버 자원

웹 사이트 : 서버 자원 (CPU, 메모리, 스토리지)

백업 및 스토리지 : 클라우드에 저장 S3, EBS 등

데이터베이스 : 관계형 데이터베이스 등

엔터프라이즈 IT