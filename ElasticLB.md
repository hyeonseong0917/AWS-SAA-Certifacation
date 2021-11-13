# ELB

### LB 결정

HTTP,layer7 : ALB

네트워크/전송 프로토콜(TCP,UDP)-layer 4 + 지연시간 low : NLB



### public IP 사용x, VPC에서 ELB API에 비공개 액세스

VPC endpoint-NAT GW,VPN 연결 없이 상호 간 라우팅 처리,AWS PrivateLink에서 제공

AWS PrivateLink-ENI 사용하는 AWS 서비스와 VPC내 프라이빗 IP간에 프라이빗 연결 제공



### ALB

1.ALB에서 고정 IP 또는 PrivateLink를 사용하려면?

NLB-가용 영역 별 PrivateLink 및 고정 IP주소를 지원

NLB 트래픽 -> ALB 유형 대상 그룹

2.1~65535 TCP Port

3.웹 소켓 기본적 지원

4.IPv6 지원,HTTPS 종료 지원

5.AWS WAF와 통합

6.VPC와 On-Premise APP Load Balancing

각자의 target group 생성, 콘텐츠 기반 라우팅 - 트래픽을 각 target group으로 라우팅

or 

별개의 LB, DNS 가중치 이용, 가중치 기반 LB

7.기본적으로 교차 영역 LB 활성화

8.ALB를 통한 Lambda 호출

AWS Lambda Invoke API를 이용하여 Lambda호출, HTTPS 요청 - 콘텐츠 기반 라우팅 규칙 처리



### NLB

1.리스너에 대해 TCP or UDP(layer 4),TLS 생성

2.변도성이 높은 트래픽 패턴 처리, 지연시간 low,클라이언트의 소스 IP유지

3.TCP와 UDP 프로토콜 트래픽을 모두 동일한 포트에서 처리 - TCP+UDP

4.LB에 가용 영역당 고정 IP를 자동으로 제공

5.DNS 리전 및 영역 장애 조치 지원

Route53 상태 확인 + DNS 장애 조치 ->NLB뒤에 실행되는 APP 가용성 up

6.각 서브넷에서 NLB에 EIP 할당 불가

7.단일 프라이빗 IP만 지원

8.웹 소켓 설정 가능

9.NLB와 TCP, TLS 리스너를 사용하여 PrivateLink 설정가능

10.ACM,IAM과 통합



### GLB

1.인라인 가상 어플라이언스 배포

2.TLS 종료 암호화/복호화 수행 x



### CLB

1.HTTP,HTTPS,SSL,TCP 프로토콜 사용

2.API 호출 기록 - CloudTrail

3.SSL 종료 지원

4.SDK를 이용하여 교차 영역 로드 밸런싱 활성화











