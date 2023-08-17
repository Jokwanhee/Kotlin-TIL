# Concise
### 코드의 간결성
자바처럼 장황하지 않는 깔끔함, 보일러 플레이트 코드의 최소화
> 보일러 플레이트 코드는 계속해서 나타나는 코드를 생각하면 된다.

```java
public class Address {
    private String city;
    private Country country;

    public Address(String city, Country country) {
        this.city = city;
        this.country = country;
    }

    public String getCity() {
        return city;
    }

    public Country getCountry() {
        return country;
    }

    public void setCountry(Country country) {
        this.country = country
    }
}
```

우선 자바 코드를 살펴보자. 아직은 볼만하다. `city`와 `country` 라는 멤버 변수를 `Address` 생성자에서 초기화해주고, `getter`와 `setter` 접근자 함수를 만들어 사용하고 있다.

하지만 만약에 멤버 변수가 `apple`, `banana`, `egg` 등 수 많은 멤버 변수가 정의된다면 그 만큼 생성자에서 초기화해주고, 접근자 메서드를 추가해주어야 한다. 즉, 반복되는 코드가 생기고 깔끔하지 않다. 가시성도 떨어지고...

그래서! 코틀린에서는 더 간단하게 정의할 수 있다.

```kotlin
Class Address(val city: String, var country: Country) {}
```

추가적으로 `val`과 `var`로 프로퍼티가 나뉘었다. 이유는 무엇일까?

자바 코드를 보면서 유추할 수 있다.

자바에서의 `city` 멤버 변수는 `getter` 접근자 메서드만 정의하고 있다. 그러니 확인만 가능한 것이다. 하지만 `country` 멤버 변수는 `getter` 와 `setter` 접근자 메서드 둘 다 정의하고 있다. 그러므로 확인 및 수정이 가능한 것이다.

그래서 `city` 를 `val`로 정의하고, `country` 를 `var`로 정의한 것이다.