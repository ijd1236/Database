## 메인 서버에서 스키마 생성, 해당 스키마를 다른 커넥션에서 사용하고 싶다

-- 서버가 DB에 접속할 수 있도록 계정 생성.

use mysql;
create user 'asd_db_user'@'%' identified by '1234';
-- 권한부여
grant ALL privileges on asd.* to 'asd_db_user'@'%';

-- 테스트해본다. => MySQL Workbench 로

![image](https://github.com/ijd1236/Database/assets/130967884/43f82431-6a93-4eac-83db-5216f4ec2c83)

다음과 같이 유저 이름 맞춰서 커넥션을 생성해주면


![image](https://github.com/ijd1236/Database/assets/130967884/fb817b28-2830-47a1-9351-aa5c87af25a7)

스키마가 들어가 있는걸 확인할 수 있다

## 테이블 복사

![image](https://github.com/ijd1236/Database/assets/130967884/a9413f0f-ff43-46c2-b205-79f1679f6219)

위와 같잉 테이블을 선택한후 클릭하면

![image](https://github.com/ijd1236/Database/assets/130967884/73fceb78-3f14-42b8-9088-570bd99c2350)

이렇게 복사가 되어 있는걸 확인할 수 있다.

![image](https://github.com/ijd1236/Database/assets/130967884/a76637a9-3c89-4788-b37f-d037ecaa4577)

해당 코드를 다른 스키마를 선택후 입력하면

![image](https://github.com/ijd1236/Database/assets/130967884/8e52d477-de51-444f-abe6-ee9499ee79b1)

이렇게 테이블이 해당 스키마에 복사된다


