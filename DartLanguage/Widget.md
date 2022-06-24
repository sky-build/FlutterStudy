# Widget

## Flutter 상에서의 위젯이란?
- UI를 만들고 구성하는 모든 기본 단위 요소
- 눈에 보이지 않는 요소들까지 위젯이라고 한다.
    - center, column, padding 같은것들도 위젯이다.
- 앱 자체도 하나의 위젯이다.

## 3가지 중요한 위젯
- Stateless Widget
    - 위젯에서 움직임이나 변화가 없는 위젯
    - 스크린상에 존재만 할 뿐 아무것도 하지 않음
    - 어떠한 실시간 데이터도 저장하지 않음
    - 어떠한 모양의 변화나 움직임이 없다.
- Stateful Widget
    - 사용자의 상호작용에 따라 모양이 바뀜
    - 데이터를 받게 되었을 때 모양이 바뀜
- Inhererited Widget

### Flutter Widget tree
- Widget들은 tree 구조로 정리될 수 있다.
- 한 위젯 안에 다른 위젯들이 포함될 수 있다.
- 부모 위젯을 widget container라고 부르기도 한다.

### Class와 Widget
- 우리가 지금 사용하고 있는 위젯은 전체다 Class로 되어있다.

## AppBar
- 상단바를 의미한다.
- leading
    - 아이콘 버튼이나 간단한 위젯을 왼쪽에 배치할 때
- actions
    - 복수의 아이콘 버튼을 오른쪽에 배치할 때
- onPressed
    - 함수의 형태로 일반 버튼이나 아이콘 버튼을 클릭했을 때 일어나는 이벤트를 정의

## Drawer
- Drawer 클래스는 안드로이드 좌측상단버튼을 클릭하면 나타나는 화면을 의미한다.
