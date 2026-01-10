- 유닛, 단위 테스트에서만 사용
- Mock이 어떤 메서드를 몇 번, 혹은 아예 호출하지 않았는지에 대한 **행동을 검증**
- ```javascript
  @Test
  void 좌석_예약_시_저장_호출됨() {
      when(seatRepository.findById(1L))
          .thenReturn(Optional.of(seat));
  
      seatService.reserve(1L);
  
      verify(seatRepository).findById(1L);
      verify(seatRepository).save(any());
  }
  
  // 자주 쓰는 문법
  verify(repo).save(any());                     // 기본 1번
  verify(repo, times(2)).findById(any());       // 정확히 n번
  verify(repo, never()).delete(any());          // 한 번도 안 됨
  verify(repo, atLeastOnce()).save(any());      // 최소 1번
  verify(repo, atMost(1)).evict(any());         // 최대 n번
  verifyNoInteractions(repo);                   // 아예 호출 없음
  verifyNoMoreInteractions(repo);               // 이거 말고 없음
  ```
-