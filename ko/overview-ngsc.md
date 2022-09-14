## Network > NAT Gateway > 개요
NAT 게이트웨이를 이용하면 인터넷 게이트웨이가 연결되지 않은 인스턴스들이 인터넷에 액세스할 수 있습니다. 하지만 인터넷에서 이 인스턴스들로 연결을 시작할 수는 없습니다.


### 주요 기능
* 인터넷 게이트웨이에 연결되지 않은 인스턴스들이 NAT 게이트웨이의 플로팅 IP로 인터넷에 액세스할 수 있습니다.
* 라우팅 테이블에서 특정 CIDR에 대해 NAT 게이트웨이를 게이트웨이로 지정하는 라우트를 설정하는 경우, 이 라우팅 테이블에 연결된 인스턴스들로부터 설정된 CIDR을 목적지로 하는 패킷의 소스 IP는 NAT 게이트웨이의 플로팅 IP로 변환됩니다.
* 하나의 NAT 게이트웨이는 동일 VPC 내의 여러 라우팅 테이블에서 게이트웨이로 지정할 수 있습니다.
* 하나의 라우팅 테이블에서 목적지 CIDR을 구분하여 다수의 NAT 게이트웨이를 게이트웨이로 지정할 수 있습니다.
* NAT 게이트웨이 주소로 인스턴스에 액세스할 수 없습니다.
* 특정 소스 IP에 대해서만 내부 접근을 허용하는 방화벽 정책을 운영하는 경우 NAT 게이트웨이의 플로팅 IP를 지정하여 정책 설정을 할 수 있습니다. 
* 외부에서 NAT 게이트웨이 주소로 연결을 시작하려는 트래픽은 차단됩니다.
* 한국(평촌) 리전에는 네트워크 ACL을 적용할 수 있습니다.