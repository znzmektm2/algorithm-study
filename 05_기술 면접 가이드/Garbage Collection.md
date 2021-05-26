# Garbage Collection이 필요한 이유

자바 프로그램은 메모리를 명시적으로 지정해서 해제하지 않기 때문에, 가비지 컬렉션 메커니즘 을 통해, 경우에 따라 더이상 필요 없는 객체를 찾아 지우는 작업을 수행한다.

# Garbage Collection 동작 방식

JVM은 운영체제로부터 할당 받은 메모리 영역을 **메소드 영역, 스택 영역, 힙 영역**으로 분리한다.

## 힙 영역

- YOUNG Generation
- OLD Generation
- Permanent Generation

## YOUNG Generation

- eden
- S0
- S1 (Survivor space)

새롭게 생성된 객체는 YOUNG Generation의 edan에 들어가고, edan이 다 차면 minor GC가 발생한다. GC가 발생하면 GC를 실행하는 스레드 외 다른 스레드는 멈춘다.
불필요한 객체는 삭제되고 아직 필요한 객체는 S0으로 이동하고 S0에 있었던 객체는 S1로 이동한다.
S1이 다 차면 S1에 필요한 객체는 OLD Generation으로 이동하고 OLD Generation은 크기가 크므로 다 차는 경우는 자주 발생하지 않지만 이 영역을 삭제할 때 major GC 혹은 full GC가 발생한다. 이 영역은 크기 때문에 프로그램 중지 시간이 minor GC보다 길기 때문에 문제가 생길 수 있다.
minor GC는 자주 발생하지만 YOUNG 영역은 OLD 영역보다 작기 때문에 프로그램 중지 시간은 짧다.
