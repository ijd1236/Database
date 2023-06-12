# MySQL Workbench

## schema생성
![image](https://github.com/ijd1236/Database/assets/130967884/d91be147-a139-49a1-8a9f-06758ebe0473)

- 데이터베이스의 테이블, 열, 관계, 제약 조건 등의 개체들을 정의하는 데 사용되는 스키마(schema)를 생성합니다.

## 테이블 생성

![image](https://github.com/ijd1236/Database/assets/130967884/23ca0c7c-b1a2-419b-998c-83eecc715df8)

- 스키마 내부의 테이블을 우클릭후 Create Table 을 클릭하여 여러 조건을 입력하여 테이블을 만들 수 있습니다.
### 테이블 작성 예시

![image](https://github.com/ijd1236/Database/assets/130967884/efd030d5-c5e8-4ea8-b153-44e0791b9bf5)


##  데이터 입력 방법.

### 테이블에 들어가기

- 먼저 자신이 입력할 테이블을 선택 위해

```SQL
use yhdb(테이블이름)
```
를 입력합니다

![image](https://github.com/ijd1236/Database/assets/130967884/b3cfac92-0cc2-4fdd-93e8-ca8e6e41365a)

- 성공했으면 좌측에 테이블이 굵게 변하는 모습을 볼 수 있습니다

### 테이블에 데이터 넣기

- 테이블내에 데이터를 넣기 위해서 insert into 테이블이름 를 사용합니다

```SQL
insert into books
(title, author_fname, author_lname, released_year, stock_quantity,
pages)
values
('10% Happier', 'Dan', 'Harris', 2014, 29, 256),
('fake_book', 'Freida', 'Harris', 2001, 287, 428),
('Lincoln In The Bardo', 'George', 'Saunders', 2017, 111, 388);
```
- 이렇게 입력한 경우 books 테블에 title, author_fname, author_lname, released_year, stock_quantity,
pages 열 내에 values 값이 들어가게 됩니다.


### 조건문, 데이터 수정
#### where
- where 을 사용하여 조건에 맞게 데이터를 찾을 수 있습니다
```SQL
select * 
from shirts
where color = 'off white';
```
- 해당 코드는 shirts 테이블에서 where color 가 'off white'인 모든 열의 데이터를 출력합니다.

#### 데이터 수정(update)
- update 와 set을 사용하여 테이블내 데이터를 수정할 수 있습니다.
```SQL
update shirts
set shirt_size = 'L'
where article = 'polo shirt';
```
- 해당 코드를 입력하면 shirts 테이블의 article이 'polo shirt'인 데이터의 shirt_size가 전부 'L' 로 수정됩니다.

#### 데이터 삭제
- delete 를이용하여 테이블내 데이터를 삭제할 수 있습니다
```SQL
delete from shirts
where article = 'tank top';
```
- 해당 코드를 입력하면 shirts 테이블 내의 ariticle 열의 값이 'tank top'인 데이터가 삭제됩니다

```SQL
delete from shirts;
```
- 해당 코드를 입력하면 전체 데이터가 삭제됩니다.


### 문자열 데이터 다루기

- 기본적인 테이블을 보는 방법은 
```SQL
select *(열 이름 선택, *은 모든 열 선택)
from books(테이블이름)
```
- 이렇게 출력하면 테이블내 모든 데이터를 볼 수 있습니다.

- concat 함수를 사용하여 열과 열을 합쳐서 볼 수 있습니다
```SQL
select concat(author_fname, ' ' , author_lname) as 'full name'
from books;
```
- 해당 코드를 입력하면 author_fname 열과 author_lname 열에 공백을 넣어 입력되고 열 이름이 full name인 데이터를 출력합니다.




