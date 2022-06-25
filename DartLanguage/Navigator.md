# Navigator
- Stack 자료구조로 되어있다.
- push, pop 기능을 수행할 수 있다.
- 사용법
    ```Dart
    // push
    Navigator.push(
        context,
        MaterialPageRoute(builder: (context) => const SecondPage()),
    );

    // pop
    Navigator.pop(context);
    ```

## Push Name Method
- named Route를 생성해서 Navigator를 이동할 때 중복되는 코드를 최소화할 수 있다.
- 사용법
    ```Dart
    class MyApp extends StatelessWidget {
        const MyApp({Key? key}) : super(key: key);

        @override
        Widget build(BuildContext context) {
            return MaterialApp(
                debugShowCheckedModeBanner: false,
                initialRoute: '/',  // 초기 화면 설정
                routes: {   // 경로 설정
                    '/': (context) => ScreenA(),
                    '/b': (context) => ScreenB(),
                    '/c': (context) => ScreenC(),
                },
            );
        }
    }

    // push
    Navigator.pushNamed(context, '/b'); // ScreenB()로 이동
    ```


- Route의 개념
- Navigator의 정의와 push, pop 함수, stack 자료구조
- MaterialPageRoute 위젯과 context
- 페이지 이동 기능 구현 완성