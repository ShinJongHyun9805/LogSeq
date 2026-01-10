- 설명:
	- 아직 커밋되지 않은 데이터를 다른 트랜잭션이 읽어버리는 현상임.
-
- 예시:
	- 트랜잭션 A가 금액을 100 → 0으로 수정하고 아직 커밋하지 않았는데, 
	  logseq.order-list-type:: number
	- 트랜잭션 B가 이 값을 읽어 “잔액 부족”으로 처리함. 
	  logseq.order-list-type:: number
	- 그런데 나중에 A가 롤백되면, B는 존재하지 않는 정보를 기반으로 처리한 셈이 됨.
	  logseq.order-list-type:: number