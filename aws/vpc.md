# VPC
Amazon Virtual Private Cloud(VPC)를 사용하면 리소스 배치, 연결 및 보안을 포함하여 가상 네트워킹 환경을 완벽하게 제어할 수 있습니다. 첫 번째 단계는 VPC를 생성하는 것입니다. 그런 다음 Amazon Elastic Compute Cloud(EC2) 및 Amazon Relational Database Service(RDS) 인스턴스와 같은 리소스를 VPC에 추가할 수 있습니다. 마지막으로, 여러 계정, 가용 영역(AZ) 또는 리전에 있는 VPC 간의 상호 통신 방법을 정의할 수 있습니다. 이 경우 네트워크 트래픽은 각 리전 내의 VPC 2개에서 공유됩니다. - [출처](https://aws.amazon.com/ko/vpc/)

VPC를 적용하지 않으면 인스턴스들이 상호적으로, 그리고 인터넷과 거미줄 처럼 얽혀 복잡도를 높일 수 있다. 또한 인스턴스 하나를 추가하면 다른 모든 인스턴스를 수정 해아한다. 

VPC를 사용하면 논리적으로 격리된 가상 네트워킹 환경 위에 인스턴스를 생성할 수 있으므로, 복잡도가 줄어들고 네트워크 설정 등이 용이해진다. 

## VPC 생성하기
https://www.44bits.io/ko/post/understanding_aws_vpc

## 참고
https://medium.com/harrythegreat/aws-%EA%B0%80%EC%9E%A5%EC%89%BD%EA%B2%8C-vpc-%EA%B0%9C%EB%85%90%EC%9E%A1%EA%B8%B0-71eef95a7098 - 개념 이해하기 쉽게 정리되어 있으므로 헷갈릴 때 읽어보면 좋음

### VPC 위에 만든 EC2 인스턴스에 DNS 할당이 되지 않을 경우
인스턴스에 DNS를 자동 할당해 주기 위해서는 **VPC 목록**에서 해당 VPC를 선택하고 **작업 -> DNS 호스트 이름 편집 -> DNS 호스트 이름 활성화에 체크** 한다. 

### VPC 위에 만든 EC2 인스턴스에 퍼블릭 IP 할당이 되지 않을 경우
인스턴스에 퍼블릭 IP를 자동 할당해 주기 위해서는 **서브넷 목록**에서 해당 서브넷을 선택하고 **작업 -> 자동 할당 IP 설정 수정 -> 퍼블릭 IPv4 주소 자동 할당 활성화에 체크** 한다.
