## Storage Gateway

ISCSI,SMB,NFS 같은 표준 스토리지 프로토콜 세트 제공, 기존 APP 재작성 X

자주 액세스 하는 데이터는 온프레미스에 캐싱

S3, FSX for Windows FS, IAM과 통합,KMS와 통합,CloudTrail과 통합

On-Premise에서  SGW가 포함된 가상 머신을 VMware,Hyper-V,KVM에 배포하거나 하드웨어 어플라이언스로 배포 가능, EC2에서 AMI로 배포 가능

#### S3 File Gateway

NFS,SMB같은 파일 프로토콜 사용, S3에 객체를 저장하고 검색

표준 파일 스토리지 프로토콜 사용, S3객체를 저장 및 검색 지원

S3, S3 IT, S3 IA 지원, 수명주기 정책을 이용하여 Glacier로 이동 가능

AD 솔루션과 통합

#### FSx File Gateway

SMB 프로토콜, FSx for Windows File Server 내 파일을 저장 및 검색

자주 사용하는 데이터의 로컬 캐시 이점

VMware,Hyper-V,KVM 또는 하드웨어 어플라이언스로 배포

전송 중 암호화 지원, 게이트웨이 작동에 대해 일련의 지속적인 상태 점검-고가용성

#### Volume Gateway

iSCSI 연결, On-Premise에 Block Storage 제공, 볼륨의 데이터-S3에 저장, EBS SnapShot으로 저장

AWS Backup : 볼륨의 복사본을 가져와 보존 관리 수행

캐싱 모드 : S3에 데이터 저장, 자주 액세스하는 데이터는 로컬로 캐시에 보존

저장 모드 : 기본 데이터 로컬에 저장, 액세스 지연시간 짧게 하기 위해 전체 데이터 세트가 주어지며 AWS에 비동기식으로 백업됨

#### Tape Gateway

iSCSI 가상 테이프 라이브러리 (VTL) 인터페이스를 백업 애플리케이션에 제공

가상 테이프는 S3에 저장, S3 Glacier 또는 S3 Glacier Deep Archive에 아카이브



