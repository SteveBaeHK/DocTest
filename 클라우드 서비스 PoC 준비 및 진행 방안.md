# 클라우드 서비스 PoC 준비 및 진행 방안



PoC는 Proofe of Concept의 준말로 실제 환경에서 데모, 시뮬레이션 또는 프로토타입을 통하여 새로운 기술의 검증하는 것을 의미합니다. 

PoC의 목표는 개념이 실현 가능함을 증명하고 제안된 솔루션이 특정 문제 또는 사용 사례의 요구 사항을 충족할 수 있음을 입증하는 것입니다.  

클라우드 서비스는 특성상 체험이 매우 편리하게 진행할 수 있으므로, 근래 고객사들은 새로운 클라우드 서비스를 채택하기 이전에 PoC를 통하여 자신들의 요구사항을 충족시키는 서비스인지를 검증하고 도입을 결정하게되는 것이 일반화되고 있습니다.



## PoC 진행 환경

고객의 PoC 진행은 다음의 두가지 방법이 있습니다.

1) 데모환경 PoC

   우리회사에서 제공한 환경에서 고객이 사용 체험해보는 PoC 진행 방법입니다.  회사에서 제공하는 별도의 사용자, 관리자 계정으로 접속하여 PoC를 진행합니다.  고객사의 PC와 충돌이 있을 수 있는 경우 (예를들어 DS 사용 고객사환경에서 SHIELDRM PoC진행) 에는   별도의 회피방안도 같이 제공되어야 합니다. 

2)  고객사 실환경 PoC

   고객사의 실환경에 적용/구축하여 진행하는 PoC로   PoC가 종료후 서비스 구독 단계로 진행할 경우 구축한 환경을 그대로 유지하여 사용하게 되므로  단순 PoC라기 보다는 실제 사용 구독을 위한 전단계 프로젝트 성격이 강합니다.
   
   고객이 직접 security365.com 에 회원가입하여 스스로 설정하여 사용 검증하는 것도 고객사 실환경 PoC에 속한다.



## 데모환경 PoC

### 데모환경 PoC가 가능한 서비스

현재 PoC 를 준비해야되는 서비스는 다음과 같습니다.

* SHIELDEX Remote Browser
  * Edge Server 불포함

* SHIELDGate
* SHIELDrive
  * Edge Server 불포함

* SHIELDRM
* SHIELD Mail

향후에 준비되면 X-Scan, SHIELDWorks등도 준비가 필요합니다.



## 고객사 실환경 PoC

### 고객사 실환경 PoC가 가능한 서비스

* SHIELDEX Remote Browser
  * Edge Server 포함
* SHIELDGate
* SHIELDrive
  * Edge Server 포함
* SHIELDRM
* SHIELD Mail
  * Exchange Server 2016 이상만 지원 (Exchange Cloud 서비스 포함)



