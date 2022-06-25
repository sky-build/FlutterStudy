# ScaffoldMessenger

## Scaffold의 단점
- 현재 위치에서 상위 위젯의 Scaffold를 찾지 못한다면 Builder를 써야한다는 단점이 존재한다.

## ScaffoldMessenger
- ScaffoldMessenger는 MaterialApp의 기본값으로 포함되어있다.
- 부모 위젯에 Scaffold 위젯이 없더라도 최상위에 있는 Scaffold로 관리된다.
- 사용법
    ```Dart
    ScaffoldMessenger.of(context).showSnackBar(SnackBar(
        content: Text('텍스트'),
        duration: Duration(seconds: 3),
    ));
    ```
- 다음 화면으로 이동하더라도 SnackBar가 유지되기 때문에 이것을 막으려면 위젯에서 ScaffoldMessenger를 리턴시키고, ScaffoldMessenger 안에 Builder를 만들어 가장 가까운 상위 ScaffoldMessenger를 변경시킨다.
- Builder를 써야한다는 단점이 존재한다.
- 사용법
    ```Dart
    @override
    Widget build(BuildContext context) {
        return ScaffoldMessenger(
            child: Scaffold(
                appBar: AppBar(
                    title: Text('Third Page'),
                ),
                body: Builder(builder: (context) {
                    return TextButton(
                        onPressed: () {
                            // Builder로 감쌌기 때문에 리턴하는 ScaffoldMessenger에서 snackBar를 보여준다.
                            // 다른 화면으로 이동하면 SnackBar는 사라진다.
                            ScaffoldMessenger.of(context)
                    .showSnackBar(SnackBar(content: Text('message')),);
                        }, 
                        child: Text('Button'),
                    );
                }),
        ),
        );
    }
    ```