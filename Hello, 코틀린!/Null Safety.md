# Null Safety
NPE를 방지할 수 있는 안전성이다.

주로 프로그래밍을 하다보면 NULL 값 때문에 Null Pointer Exception(NPE)이라는 에러를 자주 만나볼 수 있다. 

간단하게 설명하면 아래 그림을 살펴보자. null 이라는 것은 사과를 사러왔는데, 처음 탁자에 사과는 2개가 있다. 두 번째 탁자에는 사과가 0개 있다. 하지만 마지막 탁자에는 사과를 담는 박스조차 없다. 이것이 null 이라는 것이다. 없다. 아무 것도...

![Alt text](참조%20이미지/널%20참조.png)

그래서 코틀린에서는 Null을 구분하였다.
- 널이 가능한 자료형 (Nullable Type)
- 널이 불가능한 자료형 (Non-Null Type)

```kotlin
var nullable: String? = null
var nonNullable: String = "Non-Nullable"
```
```kotlin
nonNullable = null
```
에러가 발생한다! 이유는 `?` 키워드를 붙이지 않아서이다. 이 `?` 키워드를 자료형 뒤에 붙이면 널이 가능한 자료형(Nullable Type)이다.

### Safe Call
이름을 저장하는 변수의 길이를 가져오려면 변수를 확장해서 사용할 수 있다.
```kotlin
var name: String = "HELLO"
name.length // 5
```
하지만 널이 가능한 자료형은 어떻게 될까?
```kotlin
var name: String? = "HELLO"
name.length // error!
```
바로 컴파일 에러가 발생한다. 왜냐하면 Safe Call을 해주지 않아서 그렇다.

즉, 아래 코드처럼 `name.` 뒤에 `?` 키워드를 붙여주어야 한다.
```kotlin
var name: String? = "HELLO"
name?.length
```
null 이 아닐 경우에만 `length` 에 접근할 수 있다.