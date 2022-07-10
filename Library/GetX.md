# GetX
- 세가지 기능을 제공하는 라이브러리
    - 상태 관리
    - 종속성 관리
    - 라우트 관리

## 상태 관리
- 반응형 프로그래밍을 간단하게 구현할 수 있다.
- 값 뒤에 ".obs"를 붙이면 반응형 변수가 된다.
    ```Dart
    class Controller with GetxController {
        RxInt count = 1.obs;
    }
    ```
- obs 변수를 토대로 화면에 보여주려면 아래처럼 할 수 있다.
    ```Dart
    GetX<Controller>(
        builder: (controller) {
            // count 값이 변경되면 지속적으로 rebuild됨
            return Text('${controller.count.value}');
        },
    ),
    ```