#### Azure 아키텍처 구성요소

#### 1. 지역(Region)
- 특정 지역에 있는 하나 이상의 데이터센터 모음을 `Region` 이라 함.
- 사용자와 가장 가까운 지역에 리소스를 배포 가능 (서비스 런칭 전 특정 지역에 리소스가 배포 가능한지 지역 가용성을 유의해야함)
- 지역 독립적인 글로벌 서비스 존재 (CDA, Azure Policy기능 등)
- BCDR (Business continuity and disaster recovery)
  + Azure 지역은 항상 쌍을 이루는 다른 지역이 있음
  + Azure Paired Region(Main Region, Backup Region) : 한국에는 Main Region인 Korea Central/ Backup Region인 Korea South가 있음
  + (ex)한국은 Korea Central에 리소스를 만들어 놓으면 Korea South로 데이터 백업을 하는것을 권장
  + 데이터 센터 간 300마일 이상의 분리를 선호
  
***

#### 2. 가용성 옵션
- Availability set을 통해 고가용성 구현 (99.95% SLA보장)
- Availability Zone : 리소스를 여러 데이터센터에 명시적으로 배포 (99.99% SLA보장)
- Multi-region disaster recovery : paired region에 배포하는 것이 권장됨 (SLA X)

- 가용성 세트(Availability sets)
  + 유지관리 또는 하드웨어 오류 중에 응용프로그램을 온라인 상태로 유지하기 위한 옵션
  + 장애단위를 쪼개서 관리할 수 있도록 하는 옵션
  + 마이크로소프트에서 관리
  + Availabilty set에 가상컴퓨터 배포시 Azure에서 알아서 구성 
  + Fault domains와 Update domains로 나누어진다.
    + Fault domains : 
    + 데이터 센터의 여러 하드웨어에서 워크로드를 물리적으로 분리
    + 전원, 네트워크에 대한 장애가 격리될 수 있도록 나누어줌
    + Update domains :
    + 하나의 서버에 두개 이상의 가상컴퓨터가 배포되지 않도록 조절
    + 예약된 유지관리, 성능, 보안 업데이트는 업데이트 도메인을 통해 순서를 결정
   
- 가용영역 (Availability zones)
  + Azure 지역 내에서 물리적으로 위치를 구분
  + 물리적으로 구분한 데이터센터에 명시적으로 가상컴퓨터나 리소스를 직접 배포 (어떻게 배포할지에 대한 부분도)
  + 고가용성을 사용자가 관리하며 고가용성 구성은 사용자의 책임
  + 독립적인 전원, 냉각기 및 네트워크 등 모든 것이 격리되어 있는 것을 가용영역이라 부르며 이 영역에 배포
  + 통신비용발생
    
***

- 재해복구(DR)구현
  + Region간 복제 지원
  + 지역간 중간 트래픽 관리는 트래픽매니저를 통해
 
- 리소스 그룹
  + 동일한 수명주기를 가지는 리소스들을 묶는 것이 좋음
  + Web Server(리소스그룹A), Application Server(리소스그룹B), Database Server(리소스그룹C)
      + 해당 리소스그룹에 대해 하나의 라이프사이클로 볼건지 각각의 수명주기를 가진 그룹으로 나눌 것인지 분류
  + 리소스 그룹 이동 가능
 
-Azure Resource Manager
  + 리소스에 대한 모든 명령을 관리
  + 리소스 또는 리소스 그룹을 생성, 구성, 관리, 삭제
  + 리소스 조직화 및 자동화
  + 리소스 그룹은 구독이라는 과금체계에 종속이 됨

***

#### Azure Compute 서비스 (Iaas의 대표격)

#### 1. Azure Compute
- Azure에서 Compute 작업을 하는 서비스로 Web Server를 운영하거나 Application Server를 운영시 사용하는 리소스
- 기본적으로 Virtual Machine이 있으며 사용자가 직접 프로세스에 관여함
- Azure Virtual Machine(운영체제 관리 필요), VM Scale Sets, App services(PaaS,소스파일만 업로드하면 됨), Functions

***
