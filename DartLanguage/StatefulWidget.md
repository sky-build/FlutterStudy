# StatefulWidget
- StatefulWidget의 특징은 아래 코드처럼 내부에 State라는 클래스를 가지고 있다는 점이다.
    - 즉, 2개의 클래스가 합쳐져서 StateWidget을 구성하고 있는것이다.
    ```Dart
    class Test extends StatefulWidget {
        const Test({Key? key}) : super(key: key);

        @override
        State<Test> createState() => _TestState();
    }

    class _TestState extends State<Test> {
        @override
        Widget build(BuildContext context) {
            return Container();
        }
    }
    ```
- StatefulWidget이 rebuild되는 경우는 2가지이다.
    - Child 위젯의 생성자를 통해서 데이터가 전달될 때
    - Internal State가 바뀔 때

## StatefulWidget은 왜 클래스가 2개인가?
- StatefulWidget은 Widget 클래스를 상속받았다.
    - 즉 변경할 수 없다는 뜻이다.