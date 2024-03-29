# BloC
- Business Logic, Compnent의 줄임말으로 UI와 비즈니스 로직을 구분한 것이다.
- 구글에서 개발자가 권장하는 플러터 아키텍처

## Cubit
- Blocbase를 확장하는 클래스
- emit()이 호출되기 전 상태가 될 초기 상태가 필요하다.
- Cubit의 초기 상태는 getter를 통해 액세스할 수 있다.
- 새로운 상태로 업데이트해 Cubit의 상태를 업데이트 할 수 있다.

## BloC 사용법
- TextFieldBloc 패턴 예제
- 이벤트 정의
    ```Dart
    abstract class TextfieldBlocEvent {}

    // TextField가 값이 변경되었을 때 
    class TextfieldBlocChange extends TextfieldBlocEvent {
        final String text;

        TextfieldBlocChange(this.text);
    }

    class TextFieldButtonClicked extends TextfieldBlocEvent {}
    ```
- State 정의(RxDart 사용)
    ```Dart
    class TextBloc {
        final text = BehaviorSubject.seeded('');

        void updateText(String newText) {
            text.sink.add(newText);
        }

        void printText() {
            print(text.value);
        }
    }
    ```
- Bloc 클래스
    ```Dart
    class TextfieldBloc extends Bloc<TextfieldBlocEvent, TextBloc> {
        TextfieldBloc() : super(TextBloc()) {
            // TextField가 변경되었을 때
            on<TextfieldBlocChange>((event, emit) {
                state.updateText(event.text);
            });
            // TextFieldButton을 클릭했을 때
            on<TextFieldButtonClicked>((event, emit) {
                state.printText();
            });
        }
    }
    ```
- Widget에 적용
    ```Dart
    // BlocProvider를 사용해 하위 위젯에서 Bloc을 사용할 수 있도록 설정
    BlocProvider(
        create: (_) => TextfieldBloc(),
        child: MaterialApp(....);

    // 위젯에 전송
    TextField(
    // 변경사항을 State에 업데이트
    // state.updateText() 함수 실행
    onChanged: ((value) => context
        .read<TextfieldBloc>()
        .add(TextfieldBlocChange(value))),
    ),
    ElevatedButton(
        onPressed: () {
            // 현재 TextField값을 출력
            context.read<TextfieldBloc>().add(TextFieldButtonClicked());
        },
        child: const Text('버튼'),
    ),
    ```