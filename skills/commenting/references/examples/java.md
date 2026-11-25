# Java 예시

## 클래스

```java
/**
 * 테스트 클래스입니다.
 * 집에 가고 싶습니다.
 */
public class TestClass {
}
```

## 메서드

```java
/**
 * a와 b를 더합니다.
 *
 * @param a 첫번째 값
 * @param b 두번째 값
 * @return a와 b의 합
 * @throws IllegalArgumentException a 혹은 b가 0 미만일 때 발생합니다.
 */
public int add(int a, int b) {
    if (a < 0 || b < 0) {
        throw new IllegalArgumentException("< 0");
    }
    return a + b;
}
```

## 필드

```java
/**
 * 특정한 수의 합입니다.
 */
int sum = 0;
```
