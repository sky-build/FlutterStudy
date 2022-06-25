# Button
- 아래 3가지 버튼 위젯이 다음 이름으로 변경되었다.

    |이전 이름|현재 이름|
    |-------|-------|
    |FlatButton|TextButton|
    |RaisedButton|ElevatedButton|
    |OutlineButton|OutlinedButton|

- 사용법
    ```Dart
    TextButton(
        onPressed: () {},
        style: TextButton.styleFrom(
            primary: Colors.red,    // 텍스트 색상 변경
        ),
        child: Text('button'),
    ),

    ElevatedButton(
        onPressed: () {},
        style: ElevatedButton.styleFrom(
            primary: Colors.orangeAccent, // 배경색
        child: Text('button'),
    ),

    OutlinedButton(
        onPressed: () {},
        style: OutlinedButton.styleFrom(
            primary: Colors.green,
        ),
        child: Text('button'),
    ),
    ```

## ButtonBar
- Button을 쉽게 정렬할 수 있는 위젯
- 사용법
    ```Dart
    ButtonBar(
        children: [
            TextButton(
                onPressed: () {}, 
                child: Text('button')
            ),
            ElevatedButton(
                onPressed: () {},
                child: Text('button')
            ),
        ],
    ),
    ```