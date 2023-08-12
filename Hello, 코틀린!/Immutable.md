# Immutable
코틀린에서는 상태를 바꾸지 않는 불변성을 제공한다. 

- `val` : Immutable (할당 후 변경 불가)
```kotlin
val one: Int = 1
one = 2 // error
```
- `var` : Mutable (언제든 변경 가능)
```kotlin
var two: Int = 4
two = 2 // 가능
```

### Collection

- `MutableList` : 리스트 내 요소를 변경가능하다.
```kotlin
val mutableList = mutableListOf<Int>(1,2,3,4)
```
`.add()` 나 `.remove()` 를 사용해서 추가 삭제 가능
- `List` : 리스트 내 요소를 변경 불가능하다.
```kotlin
val list = listOf<Int>(1,2,3,4)
```
`.add()` 나 `.remove()` 를 사용해서 추가 삭제 불가능