## 🌊 JAVA의 흐름

JAVA 8 : Stream, Method 코드 전달 기술, 인터페이스의 디폴트 메소드

keyword : `Stream` , `동적 파라미터화`, `병렬성`, `lamdba`

### 코드 넘겨주기

- Predicate 는 인자 값을 받아서 boolean 반환

```java
public static boolean isHeavy(Apple apple){ // 무게로 필터링하는 메소드
	return apple.getWeight() >  150;
}

public interface Predicate<T>{  // 어떤 테스트 메소드를 넣을 수 있음.
	boolean test(T t);
}

static List<Apple> filterApples(List<Apple> inventory, Predicate<Apple> p){
	List<Apple> result = new ArrayList<>;

	for (Apple apple: inventory){  // Apple 객체 리스트 하나 apple
		if (p.test(apple)){    // 
				result.add(apple);
		}
	}
}

// 호출
filterApples(inventory, Apple::isHeavy); <- Apple에 메서드를 넣으면...
filterApples(inventory, Apple::isGreen);
```

### 람다

메서드 넘기는 것도 편하지만, 한 두번만 쓰고 말 메소드라면 람다로 개편해서 넘겨보자.

```java
filterApples(inventory, (Apple a) -> GREEN.equals(a.getColor)));
filterApples(inventory, (Apple a) -> a.getWeight() > 150))); 

혹은 || 를 주어 두 개 조건을 붙일 수도 있다.
```

### 스트림

Collection(list, set, queue, map...등등) 를 내부 반복을 통해 처리할 수 있다.

```java
stream().filter((Transaction t) -> t.getPrice() > 1000) // 필터링
.collect(groupingBy(Transaction::getCurrency)); // 통화로 그룹핑
```

### 멀티쓰레딩

멀티쓰레드 환경에서는 동시공유 데이터에 접근하고 갱신할 수 있다. java 8에서는 스트림으로 '컬렉션 처리 시 반복되는 코드' 문제와 '멀티코어 활용' 어려움을 동시에 잡았다.

- 반복되는 패턴으로 주어지는 조건에 따라 `필터링` 하거나, 데이터를 `추출` 하거나, `그룹화` 하는 과정을 쉽게 병렬화할 수 있기 때문이다.
- Collection을 stream으로 바꾸고, 병렬 처리 한 다음, 다시 리스트로 복원하는 것.
- 이를 통해 병렬성을 공짜로 얻을 수 있다!

### 디폴트 메소드, Java 모듈

메소드 바디가 클래스 구현이 아니라 인터페이스의 일부로 포함된다. (구현하지 않아도 되는 메서드를 인터페이스에 추가할 수 있음)

### 함수형 프로그래밍

Optional<T> 로 NPE 방지
