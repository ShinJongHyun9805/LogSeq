### 방법
	- lock 획득 실패 시, 일정 시간/횟수 동안 Lock 획득을 재시도
-
- ```javascript
  재시도 횟수 = 0
  while (true) {
    락 획득 여부 = redis 에서 key 로 확인 // SETNX key "1"
    if (락 획득) {
  		try {
  		  로직 실행
  		} finally {
  		  lock 제거
  		}
  		break;
    } else {
  	  재시도 횟수 ++
  	  if (재시도 횟수 == 최대 횟수) throw Lock 획득 실패 예외
  	  시간 지연 ( 대기 (wait time)) )
    }
  }
  ```
-
- ### 고려해야할 점
	- Lock 획득 실패 시, 지속적인 재시도로 인한 네트워크 비용 발생
	- 재시도에 지속적으로 실패할 시, 스레드 점유 등 문제 발생