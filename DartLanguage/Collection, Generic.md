# Collection
- 데이터들을 모아서 가지고 있는 자료구조
- 다른 언어에서 사용되는 배열과 개념이 같다.
- 사용법
    ```Dart
    // 생성(타입 미지정)
    var listA = [];
    List<dynamic> listA = [];

    // 생성(타입 지정)
    List<int> listA = [];
    List<String> listA = [];
    ```


# Generic
- Collection이 가지고 있는 데이터들의 데이터 타입을 지정Collection, Generic.md
- 코드의 재사용성을 가능하게 하는 기법
- 사용법
    ```Dart
    // Int값만 들어올 수 있는 List
    List<int>
    ```