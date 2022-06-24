# BuildContext
- widget tree에서 현재 widget의 위치를 알 수 있는 정보
- 모든 위젯은 자신의 BuildContext를 가지고 있다.
- ```BuildContext는 stateless 위젯이나 state 빌드 메서드에 의해서 리턴된 위젯의 부모가 된다.(중요)```
- Stateless Widget을 기본 생성하면 아래와같은 코드가 생성된다. 이때 build 메서드의 파라미터는 BuildContext타입이 있는것을 확인할 수 있다.
    ```Dart
    class TestWidget extends StatelessWidget {
        const TestWidget({Key? key}) : super(key: key);

        @override
        Widget build(BuildContext context) {
            return Container();
        }
    }
    ```

## Scaffold.of(context)
- 현재 주어진 context에서 위로 올라가면서 가장 가까운 Scaffold를 찾아서 반환

## Theme.of(context)
- 현재 주어진 context에서 위로 올라가면서 가장 가까운 Theme을 찾아서 반환하는 함수

## SnackBar
- 스크린 하단에 간단한 메시지를 띄우는 기능

## Builder 위젯
- 기존에 ```Scaffold.of(context)``` 메서드를 호출했을 때 부모 위젯으로부터 가장 가까운 Scaffold 위젯을 찾는다.
- Builder를 사용하면 Builder를 시작점으로 가장 가까운 Scaffold 위젯을 찾아간다.
- 사용법
    ```Dart
    return Scaffold(
      body: Builder(
        // 빌더를 사용해서 현재 위젯에서 가장 가까운 부모 Scaffold를 찾아갈 수 있음
        builder: (BuildContext ctx) {
          return Center(
              child: TextButton(
                style: TextButton.styleFrom(backgroundColor: Colors.red),
                child: Text(
                  'data',
                  style: TextStyle(color: Colors.white),
                ),
                onPressed: () {
                  // ctx(Builder)로부터 가장 가까운 부모 Scaffold위젯을 찾아감
                  Scaffold.of(ctx)
                      .showSnackBar(SnackBar(content: Text('buttonClicked')));
                },
              )
          );
        },
      ),
    );
    ```