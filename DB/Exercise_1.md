## Exercise 1

도메인: 

운동1길
도메인: 제조업체
제조업체가 제품을 생산한다. 제품명, 제품ID, 수량 등 다음과 같은 제품 정보가 저장되어 있다.

 이 제품들은 많은 부품들로 구성되어 있다. 

각 부품은 하나 이상의 공급업체가 공급할 수 있다. 

구성요소 ID, 이름, 설명, 이를 공급하는 공급자 및 해당 부품이 사용되는 제품 등 구성품 정보가 보관된다. 

이 연습에는 그림 B.1을 사용한다. 

이 정보를 추적하는 방법을 보여주는 ERD를 생성하십시오. 

개체 이름, 기본 키, 각 개체에 대한 속성, 개체와 카디널리티 간의 관계를 표시하십시오. 





- a supplier는 components를 제공하지 않고도 존재할 수 있다.  => components 없이 독립적으로 존재 가능
- a component는 supplier와 연결될 필요가 없다.  => 0일 수도 있다는건지?
- components는 product과 연결될 필요가 없다. all components가 products에 사용되는 것은 아니다.  => 0일 수도 있다는건지?
- components가 없으면 a product이 존재할 수 없다. => 무조건 하나 이상이 필요하다



제조업체가 product을 생산한다.

- 다음의 product 정보에는 포함된다. : 
  - product name
  - product id 
  - quantity

- 이러한 product들은 많은 components에 의해 만들어진다.

- 각 components에는 하나 이상의 supplier로 공급 되어질 수 있다.

- 다음 components 정보에는 보관되어 진다. :
  - component id
  - name
  - description
  - suppliers who supply them
  - products in which they are used