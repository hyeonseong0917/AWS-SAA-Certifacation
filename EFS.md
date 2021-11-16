### EFS

- 클라우드에서 파일 스토리지를 최적화 할 수 있게 해주는 탄력적 서버리스 파일 시스템
- EC2, ECS,Fargate,EKS에 액세스 가능, 파일 시스템 인터페이스를 통해 Lambda에 액세스
- 스토리지 프로비저닝 필요 x,자동으로 기가바이트,페타바이트로 확장
- Amazon Computing(EC2,Container,Serverless) 및 온프레미스 서버와 함께 사용 가능
- 데이터를 파일 시스템으로 로드
  - AWS DataSync-기존 파일 시스템을 EFS에 안전하고 빠르게 동기화, EFS 파일 시스템 간 파일 복사 가능
- EFS Standard -> EFS Standard-IA 수명 주기 정책, 7일 이상 액세스 x
- EFS Intelligent-Tiering
  - 액세스 패턴이 변경되는 워크로드를 위한 자동 비용 절감 기능



### 데이터 보호 및 가용성

내구성과 가용성

- Standard :  EFS 파일 시스템 객체가 다중 AZ에 중복 저장
- One-Zone : 단일 AZ내에 중복 저장, 자동 백업 -> 추가 사본은 다른 AZ에 저장해야함



### 확장성 및 성능

- 페타바이트 규모의 데이터 저장, 탄력적으로 파일을 추가하고 제거함에 따라 증감



### 보안

인스턴스의 액세스 관리

- VPC SG-파일 시스템에서 송수신되는 네트워크 트래픽 제어
- IAM정책을 파일 시스템에 연결, 클라이언트의 권한 및 액세스 제어



### EFS ACCESS POINT

EFS 파일 시스템의 공유 데이터 세트에 접근을 간소화

IAM과 연동하여 액세스 포인트를 통해 들어오는 파일 시스템 요청에 대해 운영 체제 사용자 및 그룹 디렉토리를 적용

NFS 환경에서 유연한 애플리케이션 액세스

자체적인 컨테이너 기반 개발 환경, 프로덕션 데이터에 대한 액세스 권한이 필요한 데이터 과학 분야, 다른 AWS 계정과 특정 디렉토리를 공유하는 경우



### 암호화

암호화 키는 KMS에서 관리 - 보안 키 관리 인프라를 구축 및 유지 관리할 필요가 x



### On-Premise Access

On-Premise Data Center에서 EFS File System에 접근하는 방법

- DC와 VPC간에  Dirrect Connect 또는 VPN 연결 구성
- NFS 프로토콜 - DC에 EFS FS 탑재



DC가 EFS FS에 접근하는 사용 사례

- DataSync-DC에 EFS FS탑재 가능, 모든 네트워크(Direct Connect,VPN 등)
- Migration-EFS FS에 영구 보관
- 애플리케이션 처리를 클라우드로 오프로드하여 클라우드 버스팅 워크로드를 지원
- DC의 파일 데이터를 주기적으로 EFS로 복사하여 백업 시나리오 지원



### Data Transfer

File System기반 데이터 전송?

- DataSync : DC와 EFS간 데이터 이동, 특별 제작된 프로토콜-Direct Connect 통해 오픈 소스 도구보다 10배 빠른 속도로 전송 
- Transfer Family : SFTP,FTPS,FTP 지원 완전관리형 파일 전송 서비스

