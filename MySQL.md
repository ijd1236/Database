# MySQL Workbench

## schema생성
![image](https://github.com/ijd1236/Database/assets/130967884/d91be147-a139-49a1-8a9f-06758ebe0473)

- 데이터베이스의 테이블, 열, 관계, 제약 조건 등의 개체들을 정의하는 데 사용되는 스키마(schema)를 생성합니다.

## 테이블 생성

![image](https://github.com/ijd1236/Database/assets/130967884/23ca0c7c-b1a2-419b-998c-83eecc715df8)

- 스키마 내부의 테이블을 우클릭후 Create Table 을 클릭하여 여러 조건을 입력하여 테이블을 만들 수 있습니다.
### 테이블 작성 예시

![image](https://github.com/ijd1236/Database/assets/130967884/efd030d5-c5e8-4ea8-b153-44e0791b9bf5)

### Full-text indexing
-  전체 텍스트 색인(Full-text indexing)은 데이터베이스 시스템에서 텍스트 검색 기능을 향상시키기 위해 사용되는 기술입니다. 
-  이를 통해 텍스트 필드 내의 단어나 용어에 대한 효율적인 검색이 가능해집니다.

![image](https://github.com/ijd1236/Database/assets/130967884/6f7f84e0-e430-4a03-858f-b45ae75ff072)




### UNIQE

- 유니크한 값을 만들기 위한 작업입니다.
- 입력 값의 중복을 막아줍니다.
- 테이블 아래 index 에서 설정할 수 있습니다

![image](https://github.com/ijd1236/Database/assets/130967884/fcd22f94-245f-4296-a7d6-6575121e4ed0)




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

- decimar(자릿수, 소수점)

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
- 조건문 뒤에 or , and로 이어서 조건을 추가 할 수 있습니다.

##### 결측치 찾기
-  null 인 값을 찾는 조건: where 컬럼이름 is null
-  null 이 아닌 값을 찾는 조건 :  where 컬럼이름 is not null

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



- 사용할 테이블 
- 
![image](https://github.com/ijd1236/Database/assets/130967884/214cf878-f2b0-4356-b8e9-b4eff0e1a022)



- 기본적인 테이블을 보는 방법은 
```SQL
select *(열 이름 선택, *은 모든 열 선택)
from books(테이블이름)
```
- 이렇게 출력하면 테이블내 모든 데이터를 볼 수 있습니다.

#### replace
- 문자열의 내용을 바꾸는 함수입니다
```SQL
select replace(title, 'The', '' ), pages, author_fname
from books;
```
- 해당 코드를 입력하면 title의 'The' 문자를 없애고 출력합니다.
#### reberse
- 문자열 순서를 역순으로 바꿔주는 함수입니다.
```SQL
select reverse( author_lname )
from books;
```
- 해당 코드를 입력하면 author_lname 열의 모든 문자가 역순으로 바뀐 데이터를 출력합니다

#### char_length 
- 문자열의 갯수(길이)를 구하는 함수입니다
```SQL
select char_length(title)
from books;
```
- 해당코드를 입력하면

![image](https://github.com/ijd1236/Database/assets/130967884/33a8e387-45d9-43de-a5a3-f6f123e32021)

- title의 텍스트 갯수를 출력합니다.

#### upper 과 lower

- 이함수들은 각각 문자를 소문자, 대문자로 바꿉니다
```SQL
select upper(author_fname), lower(author_fname)
from books;
```

![image](https://github.com/ijd1236/Database/assets/130967884/0bc1fcc3-66e2-4120-9c2f-460d52d7b901)

- 해당 코드를 입력하면 해당 열의 문자들을 대문자, 소문자로 바꿔 출력합니다.


#### concat

- concat 함수를 사용하여 열과 열을 합쳐서 볼 수 있습니다
```SQL
select concat(author_fname, ' ' , author_lname) as 'full name'
from books;
```
- 해당 코드를 입력하면 author_fname 열과 author_lname 열에 공백을 넣어 입력되고 열 이름이 full name인 데이터를 출력합니다.

![image](https://github.com/ijd1236/Database/assets/130967884/1b89a15e-88b0-4623-86ca-b7350bc283bc)

```SQL
select concat_ws(' ', author_fname, author_lname) as full_name
from books;
```
- concat_ws 를 사용하면 맨앞에 입력하는 조건을 넣어 열과 열을 연결 할 수 있습니다.

#### substr

```SQL
select substr(title, 1, 10) as 'short title'
from books;
```
![image](https://github.com/ijd1236/Database/assets/130967884/492f954d-3ff3-41b8-b2be-611b59b328a3)

- substr 함수를 사용하여 지정한 문자열 까지만 출력하게 할 수 있습니다

#### distinct 키워드로 유니크한 데이터 가져오기

- 중복되는 데이터를 제외한 값을 가져오고 싶을때 사용합니다.
```SQL
select distinct author_lname 
from books;
```
- 해당 코드를 입력하면 중복된 값을 제외한 데이터를 출력합니다.

#### order by 키워드
- order by 는 데이터를 정렬해주는 키워드입니다
- order by 키둬드의 위치는 항상 from 아래에 위치해야합니다

```SQL
select *
from books
order by author_lname;
```
- 해당 코드를 입력하면 author_lname의 열 데이터로 오름차순으로 정렬됩니다.
- oder by 키워드는 기본적으로 오름차순(asc) 가 생략되어 있습니다. 만약 내림차순을 원한다면 열 이름 뒤에 desc를 붙여 실행하면 됩니다.

#### limit 키워드
- 데이터를 끊어서 가져올 때 사용하는 키워드 입니다
```SQL
select *
from books
limit 0, 5;
```
![image](https://github.com/ijd1236/Database/assets/130967884/d152e344-ff5c-4168-94bf-22dc8f4cca74)
- 해당 코드를 입력하면 딱 5개의 행만 출력됩니다.
- limit 처음에 입력하는 값은 가져올 위치이고 두번째로 입력하는 값음 가져올 갯수입니다
- 위의 코드는 0,5를 적었으므로 첫번째부터 5개의 데이터를 가져옵니다.

#### like 키워드

- like 키워드는 문자열 안에 찾고 있는 데이터를 찾아 출력하는 키워드 입니다.

```SQL
select *
from books
where title like '%the%';
```
![image](https://github.com/ijd1236/Database/assets/130967884/916eef64-2c40-418d-ab13-3e291de29be5)

- 해당 코드를 입력하면 title 데이터 안에 'the'가 들어간 데이터만 찾아 출력합니다
- %를 한개만 입력하고 위치를 조절하여 해당 문자로 시작하는, 혹은 끝나는 데이터도 찾을 수 있습니다
- 위의 코드에서 where title like 'the%' 라고 입력하면 the로 시작하는 데이터를 의미하며 where title like '%the'를 입력하면 끝나는 데이터를 의미합니다.

- like 키워드는 찾고 싶은 문자뿐만 아니라 숫자의 자릿수도 찾아 출력할 수 있습니다.
- 찾고 싶은 자릿수를 선택할땐 _ 를 사용합니다. 
-  _ 의 자릿수에 따라 찾고 싶은 자릿수가 결정됩니다.

```SQL
select *
from books
where stock_quantity like '__' ;
```

- 해당 코드를 _ 가 2개 입력되었으니 2자리 숫자를 찾아서 출력합니다.

- not like를 사용하여 반대 조건을 거는것도 가능합니다.

#### count

- count 함수를 사용하여 갯수를 셀 수 있습니다
```SQL
select count(*)
from books
where title like "%the%";
```

![image](https://github.com/ijd1236/Database/assets/130967884/402cc20b-3467-4aa8-8f52-b85b2defc1da)

- 해당 코드를 입력하면 타이틀에 the 가 들어간 데이터의 갯수를 출력합니다.

#### group by 키워드

- group by로 데이터 별로 묶어서 집계할 수 있습니다.
```SQL
select author_lname,count(*) as count
from books
group by author_lname;
```

- 해당 코드를 입력하면
- author_lname 을 기준으로 묶어 해당 데이터의 count 값을 출력할 수 있습니다.
- 
![image](https://github.com/ijd1236/Database/assets/130967884/cfc43298-0d02-4339-bd3c-d2883c201c87)




#### max 와 min, sum, avg 함수

```SQL
select  max(pages)
from books;
```
- max와 min 함수를 사용하여 해당 열의 최대값과 최소값을 출력할 수 있습니다.
- avg 함수를 사용하면 열의 평균값을 구할 수 있습니다.
- sum 함수를 사용하면 열에 있는 값을 전부 더합니다.



#### 함수를 사용한 값과 다른 열의 값이 맞지 않는 경우

- 예를 들어

```SQL
select title, max(pages)
from books;
```
- 해당 코드를 실행하면
- title 과 max(pages) 값이 서로 맞물리지 않습니다.

- 함수를 사용한 데이터 값이 서로 맞물리게 하는 방법 2가지를 알아보겠습니다.

##### 첫번째 방법 : 정렬해서 가져온다
```SQL
select title, pages
from books
order by pages desc
limit 1;
```
- order by 키워드를 사용하여 pages 값을 내림차순으로 정렬하고 limit 키워드로 1개만 출력하게 하면 가장 많은 page 수를 가진 title을 알 수 있습니다

##### 두번째 방법 : max 값을 구해서 , sub query 하는 방법

```SQL
select *
from books
where pages = (select max(pages) from books);
```
- where 조건문에 pages는 가장 높은 값을 출력하는 코드를 넣습니다.


#### having

- HAVING 절은 SQL 쿼리에서 그룹 함수를 사용하여 그룹화된 결과를 필터링하는 데 사용됩니다.

```SQL
select released_year,avg(stock_quantity) as avg_stock
from books
group by released_year having avg_stock>=70;
```
- havig을 사용한 코드입니다.
- group by로 그룹화된 released_year를 기준으로 stock_quantity의 평균값이 70 이상인 값을 출력하게 합니다.


#### case 문과 와 if
##### case
- CASE 문은 SQL 쿼리에서 조건에 따라 다른 값을 반환하는 데 사용됩니다. CASE 문은 CASE 키워드로 시작하고, END 키워드로 끝납니다
```SQL
select *, 
	case
		when released_year >= 2000 then '최근책'
        else '예전책'
	end as type
from books;
```

- 해당 코드처럼 입력하면 released_year가 2000 이상일때 '최근책'을 출력하게하고 그렇지 않으면 '예전책'을 출력하게 합니다.
- when을 반복하여 여러가지 규칙을 넣을 수 있습니다.

##### if()

- if함수는 2개의 조건을 입력할때 사용합니다.
- case 문보다 간단하게 쓸 수 있는 장점이 있습니다.
```SQL
select *, if(pages > 300, '긴책', '짧은책') as book_type
from books;
```
- 해당 코드를 입력하면 pages가 300 초과인 것엔 '긴책', 아니면 '짧은책'을 출력하게 합니다.

- 값에 NULL이 있으면 NULL을 지정 값으로 세팅하는 ifnull() 함수도 존재합니다.
```SQL
select id, title, author_fname, author_lname, released_year, 
ifnull(stock_quantity, 0) as stock_quantity,
pages
from books;
```
- 해당 코드를 입력하면 stock_quantity의 NULL 값이 0으로 바껴서 출력됩니다.















