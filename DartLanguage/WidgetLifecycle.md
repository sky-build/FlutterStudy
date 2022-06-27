# WidgetLifecycle

## StatelessWidget의 Lifecycle
- StatelessWidget생성
- destory(변경되었을 때)
- rebuild

## StatefulWidget의 Lifecycle
- Widget tree - Element tree - Render tree 로 연결되어 있다.
- Widget tree는 Element tree에 있는 StateObject와 결합하게 된다.
- StateObject의 역할은 Widget의 구성요소나 속성 등을 지속적으로 추적하는 것이다.
    - 따라서 원하는대로 위젯의 구성요소나 속성의 변수를 setState 메서드를 사용해서 Widget을 업데이트할 수 있다.
- 따라서, StatefulWidget은 StatelessWidget보다 생명주기가 더 길다.

- 생명주기
    - initState 함수
        - Stateful 위젯을 생성하고 Widget tree에 삽입되었을 때 호출되는 함수
    - build 함수
        - 
    - dispose 함수 or deactive 함수
        - 위젯이 Widget tree에서 완전히 제거될 때 실행되는 함수