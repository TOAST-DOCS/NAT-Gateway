## Network > NAT Gateway > 콘솔 사용 가이드
콘솔에서 NAT Gateway 서비스를 사용하는 방법을 설명합니다.

## NAT 게이트웨이 

### NAT 게이트웨이 생성
아래 항목을 설정하여 NAT 게이트웨이를 생성합니다.

| 항목      | 설명                                                         |
| --------|------------------------------------------------------------ |
| 이름      | NAT 게이트웨이 이름을 지정할 수 있습니다. |
| VPC      | NAT 게이트웨이를 생성할 VPC를 지정합니다. |
| 서브넷     | 선택한 VPC의 서브넷 중에 인터넷 게이트웨이가 연결되어 있는 라우팅 테이블에 연결된 서브넷을 지정합니다. 조건에 만족하지 않는 서브넷으로는 NAT 게이트웨이를 생성할 수 없습니다.  |
| 플로팅 IP  | NAT 게이트웨이에 할당할 플로팅 IP를 지정합니다. 인터넷에 액세스할 때 이 IP가 소스 IP로 변환됩니다. |
| 설명      | NAT 게이트웨이에 대한 설명을 추가할 수 있습니다.  |

* NAT 게이트웨이의 VPC, 서브넷, 플로팅 IP는 변경할 수 없습니다.
* NAT 게이트웨이에 설정된 플로팅 IP는 연결을 해제할 수 없습니다. NAT 게이트웨이가 삭제되면 자동으로 연결이 해제됩니다.
* NAT 게이트웨이 주소로 인스턴스에 액세스할 수 없습니다.
* 외부에서 NAT 게이트웨이 주소로 연결을 시작하려는 트래픽은 차단됩니다.
* 네트워크 ACL이 적용됩니다.
* NAT 게이트웨이의 Quota는 3개입니다.

### 라우트 설정
* 라우팅 테이블에서 특정 CIDR에 대해 NAT 게이트웨이를 게이트웨이로 지정하는 라우트를 설정하면, NAT 게이트웨이를 사용하게 됩니다.
* NAT 게이트웨이를 라우트로 설정한 라우팅 테이블에 연결된 인스턴스들에서 라우트에 설정된 CIDR을 목적지로 하는 경우, 패킷의 소스 IP가 NAT 게이트웨이의 플로팅 IP로 변환됩니다.
* 하나의 NAT 게이트웨이는 동일 VPC 내의 여러 라우팅 테이블에서 게이트웨이로 지정할 수 있습니다.
* NAT 게이트웨이 설정 시 지정한 서브넷과 다른 서브넷에 연결된 라우팅 테이블도 NAT 게이트웨이를 게이트웨이로 지정할 수 있습니다.
* 하나의 라우팅 테이블에서 목적지 CIDR을 구분하여 다수의 NAT 게이트웨이를 게이트웨이로 지정할 수 있습니다.
* 라우트 설정에서 IP Prefix 0 (/0)이 아닌 라우트 대상 CIDR에 대해 NAT 게이트웨이를 게이트웨이로 설정하면, 인스턴스에 플로팅 IP가 설정되어 있더라도 NAT 게이트웨이로 통신됩니다.


### 네트워크 ACL 설정
NAT 게이트웨이의 VPC에 대해서 네트워크 ACL 설정을 하는 경우에 NAT 게이트웨이에도 적용됩니다. [네트워크 ACL 설정 방법](https://docs.gov-nhncloud.com/ko/Network/Network%20ACL/ko/overview/)