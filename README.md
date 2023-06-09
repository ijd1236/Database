# Database 환경 설정

- 데이터 베이스란
- 여러 사람이 공유하여 사용할 목적으로 체계화해 통합, 관리하는 데이터의 집합으로 작성된 목록으로써 여러 데이터 베이스 관리 시스템(DBMS)의 통합된 정보들을 저장하여 운영할 수 있는 공용 데이터들의 묶음을 말합니다.


## AWS MySQL Free Tier 설치

- AWS에서는 MySQL 데이터베이스를 관리하는 Amazon RDS(관계형 데이터베이스 서비스)라는 서비스를 제공합니다. Amazon RDS를 사용하면 MySQL 데이터베이스를 클라우드에서 실행할 수 있습니다. Amazon RDS는 데이터베이스 설정, 패치, 백업, 자동 소프트웨어 업데이트와 같은 관리 작업을 자동으로 처리해줍니다.

![image](https://github.com/ijd1236/Database/assets/130967884/0d455a26-0c69-4218-bb55-a11265afb25c)

- AWS 로그인 후 서비스에서 데이터베이스 -> RDS로 들어갑니다.


![image](https://github.com/ijd1236/Database/assets/130967884/e9786aeb-172d-4c5b-b350-390a956702d4)


![image](https://github.com/ijd1236/Database/assets/130967884/8eebcb08-3da6-4b81-a84a-b57414430f16)

![image](https://github.com/ijd1236/Database/assets/130967884/f1db453b-f414-42ba-bca6-b88d7f479a4d)

- 프론트 티어를 선택해야합니다.

![20230609_110228](https://github.com/ijd1236/Database/assets/130967884/6fcbf688-08fb-4098-a178-8169b1469dc3)

![image](https://github.com/ijd1236/Database/assets/130967884/f5f8ccaf-cb80-45a4-a61d-3905e6d1e93b)


- 사용자 이름과 암호를 설정해주고

![image](https://github.com/ijd1236/Database/assets/130967884/bb55ae81-1ad4-45d4-b502-31ea27a9c179)


![image](https://github.com/ijd1236/Database/assets/130967884/ed259e37-330e-4cff-86bd-b6c787420cdf)

- 암호인증인지 확인하고 넘어갑니다.


![image](https://github.com/ijd1236/Database/assets/130967884/bc7e50c0-ef6f-46de-a5dc-5742e5f8218b)


- 이외의 것들은 건들지 말고 데이터 베이스 생성을 클릭합니다.(생성까지 10분정도 소요)

![20230609_110455](https://github.com/ijd1236/Database/assets/130967884/16d96133-43c8-44ef-902a-ac62bb584578)

- 이후 RDS에 다시 들어가면 DB인스턴스가 1개가 있다고 나오며

![20230609_110505](https://github.com/ijd1236/Database/assets/130967884/a4cff7f0-a0bb-416a-8893-71ff51f69703)

-데이터 베이스가 설치된걸 볼 수 있습니다.

## MySQL Workbench

- MySQL Workbench은 오라클에서 개발한 시각적인 데이터베이스 디자인 및 관리 도구입니다. 이 도구를 사용하면 MySQL 데이터베이스를 관리하기 위한 그래픽 인터페이스를 제공하여 사용자가 데이터베이스 스키마, 테이블 및 데이터를 쉽게 생성, 구성 및 조작할 수 있습니다.

- 설치 사이트 https://dev.mysql.com/downloads/workbench/

![20230609_101213](https://github.com/ijd1236/Database/assets/130967884/b428ab10-1312-4876-9bd9-0872413946fb)


![20230609_101225](https://github.com/ijd1236/Database/assets/130967884/5031ba94-388f-4207-9083-490afc6f81cb)


- 에러가 발생하 C+(2019)가 설치되어 있어야한다고 나온다면
- https://learn.microsoft.com/ko-KR/cpp/windows/latest-supported-vc-redist?view=msvc-170 여기 사이트에 접속하여
 ![image](https://github.com/ijd1236/Database/assets/130967884/717c33b5-b7fb-47be-b2a9-ab2190eb0c95) 해당 파일을 설치합니다.

![image](https://github.com/ijd1236/Database/assets/130967884/74a598bc-9b02-45b5-82c5-5e5554d4ac58)

- 정상적으로 설치된 MySQL Workbench 입니다.

- AWS에 만든 데이터 베이스로 접속해야 합니다.
![20230609_104905](https://github.com/ijd1236/Database/assets/130967884/024c81fb-aa25-40db-ab3c-d561b7746e12)
![20230609_104916](https://github.com/ijd1236/Database/assets/130967884/247cf4b9-bb09-42b2-bdb7-f0ba8c98094b)












