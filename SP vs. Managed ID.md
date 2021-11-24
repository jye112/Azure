## 1. Service Principal
- 사용자가 만든 앱, 서비스 등에서 특정 Azure 리소스에 액세스하는 데 사용하는 보안 ID 개체이다.
- 특정 서비스에 액세스하기 위해 Azure Active Directory에서 '가짜' 사용자를 만드는 것을 방지하기 위해 사용한다.
- 특정 리소스 집합에만 액세스할 수 있도록 Azure 역할을 할당하여 제한할 수 있다.
- 인증서는 1~2년 후에 만료된다. Default는 1년이지만 2년으로 늘릴 수 있다.

## 2. Managed Identity
- Service Principal처럼 보안 ID를 관리하는 데 선호되는 접근 방식이다.
- Service Principal과는 다르게 별도의 작업없이 서비스 주체의 초기 생성 및 자동 갱신을 관리한다.(만료 기간없이 자동 갱신)
- System-assigned Managed Identity
  - Azure 서비스에서 활성화되며 실제 서비스에서 Azure AD 내의 ID를 제공한다. 해당 ID는 서비스 인스턴스가 삭제되거나 비활성화될 때까지만 활성화된다.
  - Azure는 Azure AD 내의 서비스 ID를 자동으로 정리한다.
- User-assigned Managed Identity
  - Azure AD 내에 하나 이상의 Azure 서비스 인스턴스에 할당할 수 있는 ID를 생성한다.
  - System-assigned와는 달리 ID 정리가 자동으로 이뤄지지 않으므로 정리하려면 사용자 입력이 필요하다.
