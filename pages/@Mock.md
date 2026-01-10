- Mockito가 만드는 **가짜 객체**
	- 실제 로직 ❌
	- DB 접근 ❌
	- Spring Context ❌
	- **단위 테스트 전용**
	-
- ```javascript
  @ExtendWith(MockitoExtension.class)
  class SeatServiceTest {
  
      @Mock SeatRepository seatRepository;
      @Mock MemberRepository memberRepository;
      @Mock PaymentRepository paymentRepository;
    
    	@Test
    	void test() {
        Seat seat = new Seat();
        seat....build();
        
        when(seatRepository.findById(1L)).thenReturn(seat);
      }
  }
  ```
	-