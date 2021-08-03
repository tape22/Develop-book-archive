# Modern-in-Java-Study
YAPP 백엔드 스터디를 이어 자바 개념을 정리하는 공간입니다.

### 1장 자바의 흐름 [🔗](https://github.com/tape22/Modern-in-Java-Study/blob/main/01-java%EC%9D%98%20%ED%9D%90%EB%A6%84.md)

### 2장 동작 파라미터화 [🔗](https://github.com/tape22/Modern-in-Java-Study/blob/main/02-%EB%8F%99%EC%9E%91%20%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%ED%99%94.md)

### 3장 람다

### 4장 Stream [🔗](https://github.com/tape22/Modern-in-Java-Study/blob/main/04-스트림.md)
<details>
<summary>1. 스트림은 무엇이고, 왜 쓰는지?</summary>
<div markdown="1">       

스트림은 데이터의 흐름으로, 컬렉션의 저장 요소들을 연산 처리를 해주는 반복자입니다. for-each로 명시되던 반복 작업을 내부에서 처리하고, 병렬처리를 할 수 있다는 장점이 있어서 java 8부터 등장한 이래로 
널리 쓰이고 있습니다.

</div>
</details>


<details>
<summary>2. 컬렉션과 스트림의 차이점은 무엇일까요?</summary>
<div markdown="1">       
<br>
Collection과 Stream은 데이터를 계산하는 "시점"에 차이가 있습니다. <br>
stream은 요청할 때에 계산이 시작되고, collection은 자료구조가 포함하고 있는 모든 데이터를 메모리에 저장하는 구조이기 때문에, 컬렉션이 추가되기 전에 모두 계산이 되어있어야합니다.
<br>
  

https://bk-investing.tistory.com/42

</div>
</details>


<details>
<summary>3. 직렬화, 역직렬화에 대해 설명해주세요.</summary>
<div markdown="1">       

Serializable (직렬화)는 자바 내부에서 쓰이던 객체나 데이터를 외부에서도 사용할 수 있도록 바이트 형태로 변환하는 기술을 이야기합니다. 역직렬화는 이렇게 직렬화된 바이트 데이터를 다시 객체나 데이터 형태로 바꾸는
것을 의미합니다.

https://nesoy.github.io/articles/2018-04/Java-Serialize

</div>
</details>
