- 설명:
	- 같은 트랜잭션 내에서 같은 조건으로 두 번 읽었는데 값이 달라짐.
- 예시:
	- 트랜잭션 A가 제품 가격을 조회했을 때 10,000원이었는데, 
	  logseq.order-list-type:: number
	  :LOGBOOK:
	  CLOCK: [2026-01-10 Sat 14:23:17]
	  :END:
	- 트랜잭션 B가 그 사이에 가격을 8,000원으로 수정 후 커밋함. 
	  logseq.order-list-type:: number
	- A가 다시 조회하니 8,000원이 나옴. 가격이 트랜잭션 중에 바뀐 것처럼 보이게 됨.
	  logseq.order-list-type:: number
-
-