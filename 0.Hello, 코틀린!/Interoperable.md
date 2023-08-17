# Interoperable
- [Java와 100% 호환](#java와-100-호환)
___
코틀린의 특징 중 하는 상호운용성(Interoperable)이다.
### Java와 100% 호환
Kotlin은 JVM을 사용하여 Java와 100% 호환된다. 이유는 다음과 같다.
- 코틀린 컴파일러는 자바 중간코드 (ByteCode) 생성
- 이미 존재하는 자바 라이브러리를 그대로 이용
- Java와 Kotlin은 섞어서 써도 된다.

왜 호환이 되는 지 살펴보자.

![Alt text](참조%20이미지/자바와%20코틀린의%20상호운용성.png)

이미지를 살펴보면 알 수 있다. 코틀린 확장자 파일이 컴파일러를 만나서 기계어로 번역되어야 한다. 하지만 이 중간에 Byte Code 즉, 중간 코드로 변하게 된다. 여기서 자바 확장자 파일의 접근할 수 있다. 반대로 자바도 마찬가지이다. 즉, Java와 Kotlin을 섞어 사용해도 무관하다.
> 코틀린 코드를 작성할 때, 이미 자바  라이브러리를 많이 사용한다.

예시 코드로 알아보자.
- 자바 코드
```java
public class MyClass {
    public void callKotlin() {
        System.out.println(HelloKt.world("안녕", "하세요"));
    }
}
```
- 코틀린 코드
```kotlin
// 파일명 : Hello.kt
fun world(a: String, b: String): String {
    return "$a $b Kotlin!"
}
```

자 여기서 주목해야 할 부분은 자바는 클래스 기반으로 변수와 함수를 정의한다. 하지만 코틀린은 함수를 정의해서 코드를 작성하게 된다. 그렇다면 기존 자바에서 클래스 기반 OOP 프로그래밍을 어떻게 따르는가?
```JAVA
HelloKt.world()
```
위 코드를 주목해야 한다.

코틀린에서 `fun world()` 를 만든 파일의 이름은 `Hello.kt` 이다. 이 부분을 클래스로 정의해서 사용할 수 있는 것이다. 즉, `HelloKt.world()`를 사용하는 것이다.
___

