## 영어 문제
Exercise 2
Domain: Car Dealership
Create an ERD for a car dealership. The dealership sells both new and used cars, and it operates a service facility (see Figure B.2). Base your design on the following business rules: A salesperson may sell many cars, but each car is sold by only one salesperson. A customer may buy many cars, but each car is bought by only one customer.
A salesperson writes a single invoice for each car he or she sells. A customer gets an invoice for each car he or she buys. A customer may come in just to have his or her car serviced; that is, a customer need not buy a car to be classified as a customer. When a customer takes one or more cars in for repair or service, one service ticket is written for each car. The car dealership maintains a service history for each of the cars serviced. The service records are referenced by the car’s serial number.
A car brought in for service can be worked on by many mechanics, and each mechanic may work on many cars. A car that is serviced may or may not need parts (e.g., adjusting a carburetor or cleaning a fuel injector nozzle does not require providing new parts).

###

실습 2
도메인 : 자동차 대리점
자동차 대리점의 ERD를 만듭니다. 
대리점은 신차와 중고차를 모두 판매하며 서비스 시설을 운영합니다 (그림 B.2 참조). 
다음 비즈니스 규칙을 기반으로 설계하십시오. 
영업 사원은 많은 자동차를 판매 할 수 있지만 각 차량은 한 명의 영업 사원 만 판매합니다. 
고객은 많은 자동차를 구입할 수 있지만 각 자동차는 한 명의 고객 만 구매합니다.
영업 사원은 자신이 판매하는 각 차량에 대해 단일 송장을 작성합니다. 
고객은 구매 한 자동차마다 송장을받습니다. 
고객이 자동차 서비스를 받기 위해 들어올 수도 있습니다. 
즉, 고객은 고객으로 분류되기 위해 자동차를 구입할 필요가 없습니다. 
고객이 수리 또는 서비스를 위해 하나 이상의 차량을 탑승하면 각 차량에 대해 하나의 서비스 티켓이 작성됩니다. 
자동차 대리점은 서비스되는 각 자동차의 서비스 기록을 유지합니다. 서비스 레코드는 차량의 일련 번호로 참조됩니다.
정비를 위해 반입 된 자동차는 많은 기계공이 작업 할 수 있으며 각 기계공은 많은 자동차에서 작업 할 수 있습니다. 
서비스되는 자동차는 부품이 필요할 수도 있고 필요하지 않을 수도 있습니다 
(예 : 기화기 조정 또는 연료 분사기 노즐 청소에는 새로운 부품 제공이 필요하지 않음).

## 1. 개념 스키마
### (E) 1.1 영업 사원
- ID, 이름, 소속대리점, 전화번호, ...
### (E) 1.2 고객
- ID, 이름, 연락처
### (E) 1.3 자동차
- ID, 차종, 번호, 가격, 신차여부, 판매여부, 색깔, 옵션 등..
### (E) 1.4 정비공
- ID, 이름, 소속대리점, 전화번호, ...
### (R) 1.5 송장
- ID, 영업사원ID, 고객ID, 자동차ID, 가격, 계약일, 인수일,  ...
### (R) 1.6 서비스티켓
- ID, 고객ID, 정비공ID, 수리비, 차 반입일, 차 반출일, 사용부품, ... 

## 2. 논리스키마
### 2.1 영업 사원
- dealer(**id**, name, *agency_id*, phone)
### 2.2 고객
- customer(**id**, name, phone)
### 2.3 자동차
- car(**id**, name, price, isused, color, options, soldout)

### 2.4 정비공
- mechanic(**id**, name, phone)

### 2.5 송장
- invoice(**id**, *dealer_id*, *cutomer_id*, *car_id*, price, contract_date, acquisition_date)

### 2.6 서비스티켓
- serviceticket(**id**, *customer_id*, *mechanic_id*, cost, import_date, export_date, part)
