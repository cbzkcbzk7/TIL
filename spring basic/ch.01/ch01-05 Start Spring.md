## 3. AWS에 서버 구축하기

#### 3-1 : AWS란?

    - Amazone이 제공하는 cloud service.
    관리가 쉽고 빠르고 유연한 확장성이 장점.보안. 필요할 때만 사용하고, 사용한 만큼만 비용지불

### 3-2 : AWS에 가입하기 - 최초 가입시 12개월 동안 프리티어 계정(무료계정) 사용가능

[주의] 무료 사용량을 초과하면 과금될 수 있음

### 3-3 : Amazo EC2 : 크기 조정이 가능한 컴퓨팅 용량을 클라우드에서 제공하는 웹 서비스

    - Amazon S3 : 확장성, 가용성, 내구성을 가진 데이터 저장 공간(Simple Storage)을 제공
    - Amazon RDS : 관계형 DB 관리 서비스. 관계형 DB(MySQL(Oracle)등)를 모니터링, 주기적 백업

### 3-4 : 로컬에서 가상 컴퓨터 tomcat 연결하기

    - 가상 컴퓨터 열리면 jdk, tomcat 설치
    - firewall inbound rules port 8080 추가
    - EC2 대시보드 > 보안 그룹 > firewall 로컬 inbound rules 모든 TCP 추가
