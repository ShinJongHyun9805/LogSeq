- `@Mock`으로 만든 객체들을 **테스트 대상 객체에 자동 주입**
- Spring의 Autowired랑 비슷한 기능
- 즉, @Mock으로 만든 dao를 주입한 Service를 만든다고 생각.
- ```javascript
  @ExtendWith(MockitoExtension.class)
  class SeatServiceTest {
  
      @Mock SeatRepository seatRepository;
      @Mock MemberRepository memberRepository;
      @Mock PaymentRepository paymentRepository;
  
      @InjectMocks
      SeatService seatService;
  }
  ```