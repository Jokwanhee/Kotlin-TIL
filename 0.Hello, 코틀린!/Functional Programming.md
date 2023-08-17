# Functional Programming
### 함수형 프로그래밍
- 함수의 유기적 연결을 통한 프로그래밍 방식
### 함수 = 일급 객체
- 함수가 일급 객체(First-class citizens)로 사용할 수 있게 된다.
    - 일등 시민 과 이등 시민 (비자가 없는) 일등 시민은 이등 시민보다 권한 없이 무엇이든 할 수 있다.

    ```kotlin
    fun add(a: Int, b: Int) = a + b
    fun subtract(a: Int, b: Int) = a - b

    fun main() {
        vla functions = mutableListOf(::add, ::substract)

        println(functions[0])
        println(functions[0](12, 30)) // 12 + 30
        println(functions[1](57, 15)) // 57 - 15
    }
    ```

    > 일급 객체는 함수의 인자, 반환값, 심지어 자료구조에도 넣을 수 있다.

### 람다식
- 람다식을 통해 선언되지 않고도 익명의 함수기능을 식에 전달할 수 있다.

    ```kotlin
    fun calculator(a: Int, b: Int, sum: (Int, Int) -> Int): Int {
        return a + b + sum(a, b)
    }

    fun main() {
        val out = calculator(11, 10, { a, b -> a + b }) // 11 + 10 + (11 + 10)
        // val out = calculator(11, 10) { a, b -> a + b} 코드와 동일
        println(out)
    }

    ```