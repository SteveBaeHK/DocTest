# SHIELDGate 데모체험 PoC 진행방법



SHIELDGate는 내부 리소스에 대한 원격 접속에 대한 제로트러스트 보안을 실현하는 솔루션입니다.

SHIELDGate를 통하여 고객은 신뢰할 수 없는 외부의 원격 접속에 대해서 접속하는 시간, 장소등의 조건에 따라 사용자에 대한 추가 인증, 각종 사용권한 제한, 스크린 마킹등의 보안 통제를 수행하며, 사용자 행위에 대한 스크린 캡처,  화면에 대한 키워드 검색을 통한 감사를 수행할 수 있다.



## SHIELDGate의 데모체험 PoC 환경

SHIELDGate는 사용자의 권한에 따라 지정되어 있는 접속할 수 있는 App, Desktop이 등록되어 있으며, 사용자가 다운로드/업로드하는 파일은 모두 SHIELDrive를 통해서 이루어진다. 

SHIELDGate에서 제공하는 사용자, 관리자 계정은 다음과 같다.

이들 계정은 모두 Microsoft 365 Business Premium 구독되어 있으며, Microsoft 365 서비스와 SSO을 수행하여 동작한다.



### 사용자 계정

* 사용자 

   표시 이름 : 

  계정 : user@security365demo.com

  패스워드 : 

  

### 관리자 계정

* 관리자

  표시이름 : 

  계정 : admin@security365demo.com

  패스워드 :

  SHIELDGate의 관리자 콘솔을 접속할 수 있는 권한 사용자이다. 하지만 security365demo.com 테넌트의 Microsoft 365의 관리자 권한은 없다.





SHIELDGate에서 제공하는 App, Desktop, SHIELDrive의 설정 및 동작환경은 다음과 같다.

## 데모 체험 App

사용자 계정이 접속 가능한 데모 체험 App 및 동작 권한

* Microsoft 365 Web Outlook 

  * 사용권한
    * 접속시 OTP 추가 인증 요구
    * 업로드/다운로드 : SHIELDrive를 통하여 가능

* 하이웍스 그룹웨어

  * 접속 계정 정보 : user@security365demo.com 아이드/ 패스워드 동일
  * 사용권한
    * 스크린 마킹
    * 업로드/다운로드 : SHIELDrive를 통하여 가능

* AWS 관리자 콘솔 페이지

  * 접속 계정 정보 : user@security365demo.com 아이드/ 패스워드 동일 ???--> 이거 위험한거 아님?
  * 접속시 OTP 추가 인증 요구
  * 스크린 마킹
  * 업로드/다운로드 차단
  * 키보드 입력 차단 --> 이거만으로 구독을 못하게 할 수 있나?

* 고려사항

  * 데모체험 App 추가????
  * 사용자 클릭시에 스크린 캡처가 동작하는가? 그리고 이를 검색 조회할 수 있는가?

  

## 데모 체험 Desktop

사용자가 접속 가능한 데모체험 Desktop

* Dedicated Desktop
  * 사내의 Windows VM
* Pooled Desktop
  * 종량제 Azure Virtual Desktop 
  * 사용하지 않을 경우 비용이 발생하지 않도록 접속 종료시 Power off하여야 한다. 만일 이를 지원하지 못할 경우 Pooled Desktop은 데모환경에서 제공하지 않는다.

접속할때는 현재의 재택근무동의서가 나오는 데, 이것을 그대로 사용하고 향후에 ZTCA(Zero Trust Conditional Access) 정책에 따란 동작하도록 업데이트 한다.



### 데모 체험 Desktop의 설정

Dedeicated 또는 Pooled Desktop 모두 다음과 같이 설정한다.

1) SHIELDrive 접속 바로가기 아이콘을 바탕화면에 제공한다.

2. 자사의 PC Keeper를 설치하여 다음을 통제한다.

   * Desktop의 운영체제 환경 설정을 보호한다.

   * 프로그램 설치등을 차단

   * 재부팅시 혹은 주기적으로 깨끗한 상태로 복원

* 고려사항
  * 사용자 클릭시에 스크린 캡처가 동작하는가? 그리고 이를 검색 조회할 수 있는가?



### 별도의 Desktop 제공이 필요한 서비스 체험 지원

SHIELDRM과 SHIELDrive 의 경우 고객사에서 사용하는 Endpoint DRM과의 혼재와 호환성 이슈로 별도의 가상 데스크탑 환경에서 동작 체험하는 환경을 제공할 필요가 있다.

SHIELDGate의 Desktop 접속 기능을 통하여 SHIELDRM과 SHIELDrive를 체험할 수 있도록 설정된 가상 데스크탑을 접속할 수 있도록한다.

이를 위하여 다음 내용을 준비하여 제공한다.

* 접속하는 가상 데스크탑에는 최신 Document Security Client 프로그램 군을 설치한다.
  * DS Client, SHIELDInfo 프로그램 (승인반출은 제외)
* DS 는 SSO를 통한 자동 로그인되어야 한다.
  * Microsoft365 로그인은 어떻게?  --> 시작과 동시에 DS는 SSO를 수행하고, M365 로그인은 화면에서 인증하도록 한다. (취소하거나 실패할 경우 계속 로그인하도록한다. 장애나 어려움시에 도움말 필요)
* 바탕화면
  * SHIELDrive 바로가기 아이콘 제공
  * MS Teams 실행 아이콘 제공
* 



## 데모 체험 SHIELDrive

데모 체험용 SHIELDrive는 Microsoft OneDrive에 연동하여 제공한다.

SHIELDGate로 부터 다운로드 받은 파일과 업로드할 수 있는 위치는 (?) SHIELDrive > 개인함 > OneDrive > SHIELDGate 폴더이다.

SHIELDrive의 동작 환경 설정은 다음과 같다.

* 

