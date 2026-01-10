- 설명:
	- 같은 조건으로 조회했는데 처음엔 없던 행이 두 번째엔 생기거나, 반대로 사라지는 현상임.
- 예시:
	- 트랜잭션 A가 “서울 지역 주문”을 조회했더니 5건이 나왔는데, 
	  logseq.order-list-type:: number
	- 트랜잭션 B가 새로운 서울 주문을 등록하고 커밋함. 
	  logseq.order-list-type:: number
	- A가 같은 조건으로 다시 조회하니 6건이 나옴. 중간에 유령(팬텀) 같은 행이 튀어나온 셈임
	  logseq.order-list-type:: number