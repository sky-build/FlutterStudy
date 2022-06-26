# StatefulWidget
- StatefulWidget의 특징은 아래 코드처럼 내부에 State라는 클래스를 가지고 있다는 점이다.
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