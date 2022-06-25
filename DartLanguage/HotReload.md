## Stateless Widget
- State가 변하지 않는 위젯
- Stateless Widget은 Rebuild만을 통해서 새로운 state를 적용할 수 있다.

## StatefulWidget
- State가 변하는 위젯

## State
- State는 데이터인가?
- State란 UI가 변경되도록 영향을 미치는 데이터이다.
- App 수준과 Widget 수준의 데이터가 있다.

# Hot Reload
- Flutter의 가장 큰 특징
- 순식간에 변경한 점을 결과로 보여준다.

- 우리가 알아야할 tree가 3가지가 있다
    - Widget tree
        - 우리가 작성한 코드에 근거해서 build 메서드가 생성한다.
        - flutter에게 UI를 그려달라고 요청하는 것
    - Element tree
        - 제일 중요한 것
        - Widget tree와 Render tree를 연결하고 있다.
        - 모든 위젯 하나하나가 Element tree와 link 되어있다.
    - Render tree
        - 실제로 우리가 보고있는 화면은 Render tree의 결과물이다.
- tree 구조
    - Widget이 생성되면 1:1로 대응되는 Element 가 생성된다.
    - Widget tree는 build 메서드가 호출될때마다 rebuld된다.
        - Reload
            - 프레임을 두고 부수적인것만 변경
        - Rebuild
            - 프레임을 아예 새것으로 변경
            - Text를 하나만 바꾸더라도 Hot reload되면서 Rebuild된다.
    - Reload의 문제점은 Element tree가 해결해준다.
        - 만약 Widget이 위치나 타입 속성등이 일치한다면 Element tree와 링크를 맞춰준다.
- Hot Reload 수행 순서
    - 위젯이 바뀌어서 Widget tree가 변경된다.
    - Hot reload가 실행된다.
    - build method가 실행된다.
    - Widget tree가 Rebuild된다.
    - WidgetTree와 위치나 타입 속성이 일치한다면 Element tree와 link를 업데이트 한다.
    - 위 과정을 수행 후, Element tree는 다시 렌더링이 필요한 위젯들에 대해서 Render tree에 렌더링 정보를 넘겨준다.
    - Render tree는 새롭게 렌더링해서 바뀐 정보를 화면에 출력해준다.
