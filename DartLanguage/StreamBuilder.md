# StreamBuilder
- 앱은 비동기 처리가 자주 생겨날 수 있다.
- Dart에서는 비동기 데이터 흐름을 Sream을 통해 사용할 수 있다.
- Flutter 앱에서 사용하는것이 StreamBuilder이다.
- 사용법
    ```Dart
    StreamBuilder(
        stream: _stream, // 반영할 스트림
        builder: (context, snapshot) {
            // 반영할 위젯
            // 오류, snapShot의 상태별로 위젯을 리턴
        }
    )
    ```
