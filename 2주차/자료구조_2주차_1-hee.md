
## Chapter 1. Array, Vector, Linked list

### Chatpter 1-1. 배열(Array)
`배열(Array)의 선언`
```java
int[] odds = {1, 3, 5, 7, 9};
// 자료형[] 변수명 = 값
```
### 배열의 특징
1. 배열이란 자료형의 종류가 아닌 자료형의 집합을 의미한다.
2. Java 에서 배열은 `정적 배열`을 지칭한다.
3. 배열의 길이는 고정되어 있다 → **크기를 지정하고 해당 크기만큼의 연속된 메모리 공간을 할당받는 자료형**
4. 배열 속 값에 접근하려면 인덱싱을 이용한다.
5. 배열의 길이는 `.length` 로 접근할 수 있다.
6. 한번 생성한 배열의 크기는 고정된다
7. 조회: O(1) / 탐색: O(N)
8. 삭제 / 삽입: O(N)

### Chatpter 1-2. 벡터(Vector)
`벡터(Vector)의 선언`
```java
Vector<Integer> vector = new Vector<Integer>(10); // 초기용량 = 10
vector.add(1); //값 추가
System.out.println(vector.size()); // Vector 자료 개수 = 1
System.out.println(vector.capacity()); //Vector 물리적크기 = 10
```

### 벡터의 특징
1. Vector란 Collection 프레임워크의 일부이며 java.util 패키지에 소속
2. ArrayList와 동일한 구조를 가지며 배열의 크기가 늘어나고, 줄어듬에 따라서 자동으로 크기가 조절

### 💡 벡터(Vector)와 ArrayList는 같은 것인가? → `아니다`
#### 벡터(Vector)와 ArrayList의 차이점
1. 벡터는 동기화(Synchronized)되지만 ArrayList는 동기화되지 않는다.
2. 데이터를 증가 시키는 방법

### `벡터를 사용 해야만 하는 요구 사항이 없는 경우 ArrayList를 사용하는 것이 권장됨`

### 동기화(Synchronization)
- **Java의 동기화(Synchronization)란 모든 공유 리소스에 대한 여러 스레드의 액세스를 제어하는 ​​기능**
- 요소(들)의 추가 또는 삭제할 때 동기화가 일어날 수 있다(?)


### 자료형의 크기 증가
- 내부적으로 ArrayList와 Vector는 모두 Array를 사용하여 내용을 유지함.
- 요소가 ArrayList 또는 Vector에 삽입될 때 공간이 부족한 경우 객체는 내부 배열을 확장해야 함 
- Vector는 기본적으로 배열 크기를 두 배로 늘리는 반면 ArrayList는 배열 크기를 50% 늘림.

### 💡 벡터(Vector)는 ArrayList의 부모 클래스인가?  → `그렇다`
- 정확히는 ArrayList는 java.util.Collection 클래스 자식 클래스이다.
- 그런 Collection 클래스의 부모 클래스가 Vector이므로 `Vector → Collection → ArrayList` 의 관계를 갖는다.
- Collection 클래스 외에도, Serializable, Cloneable, Iterable<E>, Collection<E>, List<E>, RandomAccess interfaces, Stack 등이 **Vector 클래스**의 자식 클래스이다.

###  Chatpter 1-3. 연결 리스트(Linked List)
`연결 리스트(Linked List)의 선언`
```java
LinkedList lklist = new LinkedList(); 
LinkedList<Integer> intLkList = new LinkedList<Integer>(); 
```
### 연결리스트의 데이터 추가(특징이 있음!)와 삭제
```java
lklist.add(Object) // add를 사용할 경우 LinkedList의 마지막에 데이터를 추가합니다
lklist.add(int Index, Object) // index를 사용하여 추가도 가능.
lklist.remove() // 첫번째, index = 0 을 제거
lklist.remove(1) // 인덱스에 해당하는 데이터 삭제, index = 1 을 제거
ll.removeFirst(); // 첫 번째 데이터 삭제 
ll.removeLast(); // 마지막 데이터 삭제
```

### 연결 리스트(Linked List)의 특징
1. LinkedList란 Collection 프레임워크의 일부, java.util 패키지에 소속
2. 데이터가 메모리 상에서 이웃한 주소에 위치하지 않아 포인터로 연결되어있다.
3. 각 데이터는 노드로 관리 되며 배열에서 자주 삽입, 삭제가 이루어지는 경우 용이하다.
4. 물리 메모리를 연속적으로 사용하지 않아 관리 용이
5. 그러나 ArrayList보다 검색에서 느리다는 단점이 있다.
6. 삽입/삭제: O(1) / 조회: O(N)

```java
class Node {
    int value;
    Node next;

    Node(int value, Node next) {
        this.value = value;
        this.next = next;
    }
}

Node head = new Node(1, new Node(2, new Node(3)));
```
---
<br>

## Chapter 2. Stack, Queue

### Chatpter 2-1. 스택(Stack)
`스택(Stack)의 선언`
```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.push(2);
stack.push(3);

System.out.println(stack); // Output: [3, 2, 1]
```

###  스택(Stack)의 특징
- LIFO (Last In First Out): 후입 선출
- 재귀, 메모리(스택 영역)에서 사용



### Chatpter 2-2. 큐(Queue)
`큐(Queue)의 선언`
```java
import java.util.LinkedList;

LinkedList<Integer> queue = new LinkedList<>();
queue.add(1);
queue.add(2);
queue.add(3);

System.out.println(queue); // Output: [1, 2, 3]
```

###  큐(Queue)의 특징
- **FIFO (First In First Out): 선입 선출**
- BFS, 스케줄링에 사용
- 인터페이스이므로 자료형으로써 사용 가능하나, 이를 상속받을 수 있는 다른 클래스를 사용해야함
- LinkedList와 ArrayDeque를 사용
- 
---
<br>

## Chapter 3. Deque

`Deque의 선언`
```java
import java.util.Deque;
import java.util.ArrayDeque;

Deque<Integer> deque = new ArrayDeque<>();

deque.addFirst(1);
deque.addFirst(2);
deque.addLast(3);
deque.addLast(4);

System.out.println(deque); // Output: [2, 1, 3, 4]

System.out.println(deque.removeFirst()); // Output: 2
System.out.println(deque.removeLast()); // Output: 4
System.out.println(deque); // Output: [1, 3]

System.out.println(deque.peekFirst()); // Output: 1
System.out.println(deque.peekLast()); // Output: 3
```

### Deque의 특징
- Double Ended Queue
- **양쪽 끝에서 원소의 삽입과 삭제가 가능한 자료형 (큐 + 스택)**


---
<br>

## Chapter 4. Priority Queue, Heap

### Chatpter 4-1. 스택(Priority Queue)

`의 선언`
```java
```

### 의 특징


### Chatpter 4-2. 힙(Heap)

`의 선언`
```java
```

### 의 특징


---
<br>

## Chapter 5. Hash


`의 선언`
```java
```

### 의 특징


---
<br>

## Chapter 6. Graph


`의 선언`
```java
```

### 의 특징

---
<br>

## Chapter 6. Tree


`의 선언`
```java
```

### 의 특징
