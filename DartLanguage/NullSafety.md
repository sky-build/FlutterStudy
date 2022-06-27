# NullSafety
- Flutter 2.0에서 새롭게 나온 개념
- nullSafety 개념이 나오게 되면서 기본 변수는 null이 될 수 없으며, not-nullable한 변수에는 null값을 할당할 수 없게된다.
- not-nullable 변수는 반드시 값이 할당되기 때문에 null 체크를 해주지 않아도된다.
- ***Class 내의 변수***는 반드시 선언과 동시에 초기화를 시켜야한다.

- 사용법
    ```Dart
    int? age = null;
    String? name = null;
    // 항상 null이 아닌 경우 변수 뒤에 느낌표를 추가한다.
    int realAge = age!;
    ```

## required
- 파라미터로 전달받을 때 반드시 전달해야하는 값을 설정
- 사용법
    ```Dart
    int add({required int a, required int b}) {
        return a + b;
    }
    ```

## late
- 변수가 나중에 설정될것임을 알려준다.
- 사용법
    ```Dart
    late int age;
    ```