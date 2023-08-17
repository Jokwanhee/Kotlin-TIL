# Extension Function

### 확장 함수
클래스 상속이나 디자인 패턴을 사용하지 않고도 새로운 기능 확장이 가능하다.
- 단, 너무 많은 사용은 기능들이 남발하게 되므로 가독성이 떨어진다.

```kotlin
class Original {
    fun onlyOneFunction() {
        println("Only One")
    }
}

fun Original.myExtension(): String {
    return "확장 함수 호출하기"
}

fun main() {
    val originalObj = Original()
    vla result = originalObj.myExtension()
    print(result)
}
```

### 유용하게 사용되는 상황, String 확장 함수 예제

String 이라는 클래스를 확장하여 확장 함수를 만들어보자.
```kotlin
fun String.lastChar() : Char = this.get(this.length - 1)
println("12345".lastChar())
```
- 수신 자료형(Receiver Type) : `lastChar()` 확장 함수를 확장해주는 주체인 `String` 이 수신 자료형이다.
    ```kotlin
    String.
    ```
- 수신 객체 (Receiver Object) : `String` 을 사용하기 위한 객체를 `this` 로 수신 객체라고 한다.
    ```kotlin
    this
    ```


