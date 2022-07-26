# BloC
- Business Logic, Compnent의 줄임말으로 UI와 비즈니스 로직을 구분한 것이다.
- 구글에서 개발자가 권장하는 플러터 아키텍처

## Cubit
- Blocbase를 확장하는 클래스
- emit()이 호출되기 전 상태가 될 초기 상태가 필요하다.
- Cubit의 초기 상태는 getter를 통해 액세스할 수 있다.
- 새로운 상태로 업데이트해 Cubit의 상태를 업데이트 할 수 있다.