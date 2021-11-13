### SQS

분산 APP에서 폴링 모델을 통해 메시지를 교환하는 데 사용되는 메시지 대기열 서비스

송신 구성 요소와 수신 구성 요소 분리 가능 

1.FIFO 대기열 & 표준 대기열

FIFO-메시지 전송, 수신의 정확한 순서를 보존, 정확히 1회 처리

표준-느슨한 FIFO 기능, 정확한 순서 보장 x, 최소 1회 전달

2.SQS vs Kinesis Streams

SQS : APP-APP or MS-MS 이동 시, 메시지 저장

Kinesis Streams : 빅데이터 스트리밍 실시간 처리, Kinesis App의 레코드 처리, KCL은 주어진 파티션 키에 대한 모든 레코드를 동일한 레코드 프로세서에 제공, 동일한 Kinesis Streams의 데이터를 읽는 APP 보다 쉽게 구축

3.SQS와 함께 사용되는 서비스

EC2, ECS, Lambda, S3, DynamoDB

4.배달 못한 편지 대기열

5.SQS 긴 폴링

SQS 대기열에서 메시지를 검색하는 방법, 빈 응답 수신 횟수 감소, 메시지가 메시지 대기열에 도착하거나 긴 폴링 제한 시간이 초과될 때 까지 응답 반환 x

6.FIFO 대기열

중복 메시지 절대 삽입 x

7.대기열에 대한 SSE 활성화 - SQS용 CMK 사용(관리형 고객 마스터키,사용자 지정 CMK)

8.HTTPS + TLS







