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

## 종속성 관리
- GetX 인스턴스 안에서 의존성을 주입해 간편하게 사용할 수 있다.
- 사용법
    ```Dart
    // 의존성 주입
    Controller controller = Get.put(Controller());

    // Controller에 접근
    // 두가지 방법중에 하나를 사용하면 됨
    final controller = Get.find<Controller>();
    Controller controller = Get.find();
    ```

## 라우트 관리
- 라우트관리를 GetX를 사용해 관리할 수 있다.
- 우선 아래 코드처럼 MaterialApp을 GetMaterialApp으로 바꾼다.
    ```Dart
    GetMaterialApp( // Before: MaterialApp(
        home: MyHome(),
    )
    ```
- 화면이동법은 아래와 같다.
    ```Dart
    // NextPage 위젯으로 이동할 때
    Get.to(NextPage());

    // 이전화면으로 돌아갈 때
    Get.back();
    ```