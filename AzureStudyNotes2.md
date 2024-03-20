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
