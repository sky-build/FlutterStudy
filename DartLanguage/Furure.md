# Future
- 비동기 작업을 할 때 사용
- 일정 소요시간 후에 실제 데이터나 에러를 반환
- async 클래스는 await 메서드를 가지고 있다.
    - await으로 선언된 메서드는 응답이 처리될 때까지 대기

## Future 실행방법
- Dart에 의해서 Future 객체가 내부적인 배열에 등록
- Future 관련해서 실행되어야하는 코드들이 이벤트 큐에 등록
- 불완전한 future 객체가 반환
- ```Synchronous 방식으로 실행되어야 할 코드 먼저 실행(중요)```
- 최종적으로 실제적인 data 값이 future 객체로 전달.

## async 함수
- 메서드를 통해서 나오는 결과물은 Future
- await 키워드를 만날때까지 동기(synchronous) 방식으로 코드 처리
- await 키워드를 만나면 future가 완료될 때까지 대기
- future가 완료되자마자 그 다음 코드들을 실행

### Thread
- 프로세스내에서 실행되는 흐름의 단위
- Dart는 싱글 스레드로 운영되는 언어이다.
- 플러터는 어떻게 복잡한 작업들의 순서를 처리할까?
    - Event loop
        - FIFO 방식으로 MicroTask와 Event를 준비
        - main 함수 실행
        - Event loop 실행
    