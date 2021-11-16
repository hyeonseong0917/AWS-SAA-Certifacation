## EC2 Storage



### EBS

내구성이 있는 블록 수준 스토리지 볼륨 제공, 실행중인 인스턴스에 연결 가능

세분화된 업데이트 자주 사용 시(데이터 베이스 실행 시) 권장

볼륨의 스냅샷을 S3에 저장,데이터의 백업 사본 유지.. 스냅샷에서 새 EBS 볼륨을 생성하여 다른 인스턴스에 연결할 수 있음



### EC2 Instance Store

호스트 컴퓨터에 물리적으로 연결된 디스크의 스토리지

블록 수준의 임시 스토리지

연관 인스턴스의 수명 기간에만 유지, 중단 or 최대 절전 모드 -> 볼륨 데이터 손실



### EFS

하나의 EFS file system을 여러 인스턴스에서 실행하는 워크로드에 공통 데이터 소스로 사용 가능



### S3

EC2 내 or 웹의 어디서나 원하는 데이터의 양을 저장하고 가져올 수 있게 해주어 웹 규모 컴퓨팅 작업 쉽게 수행

EBS Snapshot,Instance Store 지원,AMI 저장



### ROOT STORAGE DEVICE

AMI에서 인스턴스 실행 시, ROOT STORAGE DEVICE 생성

BLOCK DEVICE MAPPING-AMI 생성 시 or 인스턴스 실행 시 루트 디바이스 볼륨과

스토리지 볼륨 지정 가능