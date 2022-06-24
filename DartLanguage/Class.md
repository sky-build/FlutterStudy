# Class
- class에는 속성과 기능이 포함되어 있다.
- 클래스를 생성하면 인스턴스가 된다.
- 클레스가 매모레상에서 할당되면 이것을 ***객체***라고 한다.
- 생성자를 아래처럼 구현할 수 있다.
    ```Dart
    class Person {
        String name;
        int age;
        String sex;

        // 생성자
        Person(this.name, this.age, this.sex);
    }
    ```
- 만약 전체값을 생성하지 않고싶다면 생성자를 아래처럼 구현하면 된다. 단, 이때 클래스의 멤버변수는 Optional이 될 것이다.
    ```Dart
    class Person {
        String? name;
        int? age;
        String? sex;

        // 생성자
        Person({this.name, this.age, this.sex});
    }
    // 아래처럼 멤버변수를 직접 선언해서 값을 할당해야한다.
    // 이 방식은 위젯을 생성하는 방법과 동일하다.
    var p = Person(
        name:'name',
        );
    ```
- 클래스와 위젯의 생성방법이 동일하기 떄문에 모든 위젯은 Class로 이루어져있음을 확인할 수 있다.