# interface

- 추상클래스는 추상메소드를 1개 이상 가지고 있는 클래스를 의미
- 기본 메소드 이외에 추상 메서드를 상속시켜서, 반드시 구현이 필요한 내용인 추상 메서드를 상속받은 클래스에서 구현시키는 것이 주목적
- 객체 생성X
- 추상 클래스를 상속받은 클래스의 객체 생성을 위해서는 추상 메서드를 구현해야 함

# abstract

- class와 유사하지만 class가 아니다.
- 객체 생성X
- implements하여 interface를 다중 상속 할 수 있고, 모든 메소드는 재정의해야 한다.
- interface의 모든 변수는 public static final이다.
- interface의 모든 메소드는 public abstract이다.
- 인터페이스끼리 상속 가능하지만 class는 상속받을 수 없다.
