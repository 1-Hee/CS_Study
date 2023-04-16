# 1. Array, Vector, Linked List

## Array (배열)

- 개념: 동일한 자료형을 가진 데이터를 인덱스를 통해 연속적으로 메모리에 할당한 자료구조
- 시간복잡도: 검색, 삽입, 삭제 모두 O(1)의 시간 복잡도를 가지지만, 중간 삽입/삭제는 데이터 이동이 필요하기 때문에 O(n)의 시간 복잡도를 가짐.
- 장점: 인덱스를 통한 빠른 검색이 가능하고, 메모리 공간을 연속적으로 할당하기 때문에 캐시 히트율이 높아 빠른 속도로 데이터를 처리할 수 있음.
- 단점: 크기가 고정되어 있기 때문에 중간 삽입/삭제가 어려우며, 크기가 큰 경우 메모리 낭비가 발생할 수 있음.
- 사용되는 경우: 데이터의 크기가 고정되어 있고, 검색이 자주 일어나는 경우

## Vector (동적 배열)

- 개념: 배열과 유사하지만 크기가 동적으로 변화할 수 있는 자료구조
- 시간복잡도: 검색, 삽입, 삭제 모두 O(1)의 시간 복잡도를 가지지만, 중간 삽입/삭제는 배열과 마찬가지로 데이터 이동이 필요하기 때문에 O(n)의 시간 복잡도를 가짐.
- 장점: 크기가 동적으로 변화하며, 중간 삽입/삭제가 가능하기 때문에 유연하게 데이터를 처리할 수 있음
- 단점: 메모리 할당 및 복사 과정에서 오버헤드가 발생할 수 있음
- 사용되는 경우: 크기가 변할 수 있는 데이터를 처리할 때, 중간 삽입/삭제가 자주 일어나는 경우

## Linked List (연결리스트)

- 개념: 데이터와 포인터로 구성된 노드(Node)들이 연결된 자료구조
- 시간복잡도: 검색은 O(n), 삽입/삭제는 O(1)의 시간 복잡도를 가짐.
- 장점: 중간 삽입/삭제가 용이하며, 크기가 동적으로 변화할 수 있기 때문에 메모리를 효율적으로 사용할 수 있음
- 단점: 인덱스를 통한 검색이 불가능하며, 메모리에 불연속적으로 할당되기 때문에 캐시 히트율이 낮아 처리 속도가 느릴 수 있음
- 사용되는 경우: 데이터의 크기가 동적으로 변할 수 있는 경우, 중간 삽입/삭제가 자주 일어나는 경우, 메모리 공간이 제한적인 경우

### 캐시 히트율?
캐시 히트율(Cache hit rate)은 캐시(Cache)라는 고속 메모리에 데이터를 저장하는 경우, 해당 데이터를 찾는데 성공하는 확률을 의미한다. 예를 들어, 배열(Array)은 메모리에 연속적으로 할당되기 때문에 캐시 히트율이 높아 처리 속도가 빠르다. 반면에 연결 리스트(Linked List)는 메모리에 불연속적으로 할당되기 때문에 캐시 히트율이 낮아 처리 속도가 느릴 수 있다. 따라서 자료구조를 선택할 때 캐시 히트율을 고려하는 것이 중요하다.

## 예상질문

### 질문1. Array와 Linked List의 차이점은 무엇인가요?
Array는 메모리 상에 연속적으로 할당된 공간을 사용하며 인덱스를 통해 빠르게 검색이 가능합니다. 반면 Linked List는 불연속적으로 분산된 노드들이 포인터를 통해 연결된 구조를 가지며, 검색이 느리지만 중간 삽입/삭제가 용이하고 크기가 동적으로 변화할 수 있습니다.

### 질문2. Vector와 ArrayList의 차이점은 무엇인가요?
Vector와 ArrayList는 기본적으로 동일한 자료구조입니다. Vector는 Java 1.0에서부터 제공되던 자료구조로, 모든 메서드에 synchronized 키워드가 포함되어 있어 스레드 안전성을 보장합니다. 반면 ArrayList는 Java 1.2부터 추가된 자료구조로, 동기화를 지원하지 않아 스레드 안전성을 보장하지 않습니다. 따라서 멀티스레드 환경에서 Vector를 사용하는 것이 안전합니다.

### 질문3. Vector와 Linked List의 장단점은 무엇인가요?
Vector는 배열과 유사한 구조로 인덱스를 통해 빠르게 검색이 가능하며, 크기가 동적으로 변화할 수 있는 장점이 있습니다. 반면 Linked List는 중간 삽입/삭제가 용이하며 메모리를 효율적으로 사용할 수 있는 장점이 있습니다. 하지만 검색이 느리고 포인터를 유지해야 하므로 추가적인 메모리 공간이 필요합니다.

### 질문4. Vector와 ArrayList의 시간복잡도에 대해 설명해주세요.
Vector와 ArrayList 모두 검색은 O(1)이며, 삽입/삭제는 O(n)의 시간 복잡도를 가집니다. 따라서 데이터의 검색이 빈번하지 않고, 중간 삽입/삭제가 많은 경우 Linked List를 사용하는 것이 유리합니다.

### 질문5. Linked List에서의 검색 시간복잡도는 어떻게 되나요?
Linked List에서 검색은 노드를 하나씩 찾아야 하므로 O(n)의 시간 복잡도를 가집니다. 따라서 데이터 검색이 빈번한 경우에는 검색 속도가 느리므로 Array나 Vector를 사용하는 것이 더 효율적입니다.

### 질문6. Array의 크기를 동적으로 변경할 수 있나요?
기본적으로 Array의 크기는 고정되어 있으며, 동적으로 변경하려면 새로운 Array를 할당하고 기존의 데이터를 복사해야 합니다. 이는 매우 비효율적이므로, 크기가 동적으로 변화해야 하는 경우에는 Vector나 ArrayList를 사용하는 것이 좋습니다.

### 질문7. Vector에서 어떤 경우에 동기화가 필요한가요?

Vector는 모든 메서드에 synchronized 키워드가 포함되어 있어 스레드 안전성을 보장합니다. 따라서 멀티스레드 환경에서 Vector를 사용하는 경우에는 동기화가 필요합니다.

### 질문8. Linked List에서 중간 노드를 삭제하는 과정을 설명해주세요.
삭제하려는 노드의 이전 노드의 포인터를 삭제하려는 노드의 다음 노드를 가리키도록 변경하면 됩니다. 이후 삭제하려는 노드의 포인터를 null로 설정하여 메모리를 해제합니다.

### 질문9. Array와 Linked List 중에서 어느 상황에서 어떤 어떤 자료구조를 사용해야 할지 설명해주세요.
Array는 크기가 고정되어 있으며 중간 삽입/삭제가 어려운 단점이 있지만, 검색 속도가 빠르므로 데이터 검색이 빈번한 경우에는 유용합니다. 반면 Linked List는 크기가 동적으로 변화하며 중간 삽입/삭제가 용이하나 검색이 느리므로, 중간 삽입/삭제가 빈번하고 데이터 검색이 적은 경우에는 유용합니다.

### 질문 10. Vector와 ArrayList 중에서 어느 상황에서 어떤 어떤 자료구조를 사용해야 할지 설명해주세요.
Vector와 ArrayList는 모두 크기가 동적으로 변화할 수 있는 자료구조입니다. 하지만 Vector는 모든 메서드에 synchronized 키워드가 포함되어 있어 스레드 안전성을 보장하므로, 멀티스레드 환경에서는 Vector를 사용하는 것이 좋습니다. 반면 단일 스레드 환경에서는 ArrayList를 사용하는 것이 더 효율적입니다.

# 2. Stack, Queue

## Stack

- 개념 : 후입선출(LIFO, Last In First Out) 구조를 가지는 자료구조이다. 새로운 요소는 항상 가장 상위(top)에 추가되고, 요소의 삭제도 가장 상위에서 일어난다
- 시간복잡도 : 스택에서 삽입, 삭제, 검색 모두 O(1)이다.
- 장점 : 구현이 쉽고, 적은 메모리 용량으로 구현이 가능하다.
- 단점 : 중간 요소의 삭제가 어렵다.
- 사용되는 경우 : 함수 호출, 괄호 검사, 수식 계산 등에서 사용된다.

## Queue

- 개념 : 선입선출(FIFO, First In First Out) 구조를 가지는 자료구조이다. 새로운 요소는 항상 가장 뒤(rear)에 추가되고, 삭제는 항상 가장 앞(front)에서 이루어진다.
- 시간복잡도 : 큐에서 삽입, 삭제, 검색 모두 O(1)이다.
- 장점 : 스택과 마찬가지로 구현이 쉽고, 적은 메모리 용량으로 구현이 가능하다.
- 단점 : 스택과 마찬가지로 중간 요소의 삭제가 어렵다.
- 사용되는 경우 : 작업 예약, 프로세스 관리, 네트워크 프로그래밍 등에서 사용된다.

## Stack, Queue 구현방법
- 배열(Array)을 이용한 스택/큐 구현 : 일반적으로 가장 간단한 방법이며, 인덱스를 이용하여 요소에 접근한다. 하지만 크기가 고정되어 있어 크기가 변경되면 메모리 재할당과 복사가 필요하다.
- 연결 리스트(Linked List)를 이용한 스택/큐 구현 : 동적 메모리 할당을 이용하여 요소를 추가하고 삭제할 수 있다. 하지만 포인터를 이용하기 때문에 메모리 사용량이 더 크다.

## 예상질문 

### 질문1. 스택(Stack) 자료구조란 무엇인가요?
스택은 데이터를 저장하는 자료구조로, 가장 마지막에 삽입된 데이터가 가장 먼저 삭제됩니다. 이를 LIFO(Last In First Out) 구조라고 합니다. 스택에 데이터를 삽입하는 것을 push, 삭제하는 것을 pop이라고 합니다.

### 질문2. 스택의 구현 방법에는 어떤 것들이 있나요?
스택은 배열(Array)과 연결 리스트(Linked List)를 이용하여 구현할 수 있습니다. 배열을 이용한 구현 방법은 구현이 간단하고 빠르지만, 크기가 고정되어 있어 최대 크기를 넘을 경우에는 오버플로우(Overflow)가 발생합니다. 연결 리스트를 이용한 구현 방법은 크기가 동적으로 변화할 수 있어 최대 크기를 넘을 경우에도 자동으로 크기를 조정할 수 있지만, 포인터를 사용하기 때문에 메모리 사용량이 더 많습니다.

### 질문3. 큐(Queue) 자료구조란 무엇인가요?
큐는 데이터를 저장하는 자료구조로, 가장 처음에 삽입된 데이터가 가장 먼저 삭제됩니다. 이를 FIFO(First In First Out) 구조라고 합니다. 큐에 데이터를 삽입하는 것을 enqueue, 삭제하는 것을 dequeue이라고 합니다.

### 질문4. 큐의 구현 방법에는 어떤 것들이 있나요?
큐는 배열(Array)과 연결 리스트(Linked List)를 이용하여 구현할 수 있습니다. 배열을 이용한 구현 방법은 구현이 간단하고 빠르지만, 크기가 고정되어 있어 최대 크기를 넘을 경우에는 오버플로우(Overflow)가 발생합니다. 연결 리스트를 이용한 구현 방법은 크기가 동적으로 변화할 수 있어 최대 크기를 넘을 경우에도 자동으로 크기를 조정할 수 있지만, 포인터를 사용하기 때문에 메모리 사용량이 더 많습니다.

### 질문5. 스택과 큐의 차이점은 무엇인가요?
스택과 큐는 모두 데이터를 저장하는 자료구조이지만, 데이터의 삽입과 삭제에 대한 규칙이 다릅니다. 스택은 가장 마지막에 삽입된 데이터가 가장 먼저 삭제되는 반면, 큐는 가장 처음에 삽입된 데이터가 가장 먼저 삭제됩니다. 이를 LIFO와 FIFO 구조라고 합니다.

### 질문6. 스택과 큐는 어떤 경우에 사용되나요?
스택은 후입선출(Last In First Out, LIFO) 구조로 데이터를 저장하고 처리하는데 주로 사용됩니다. 스택은 함수의 호출과 반환, 수식의 괄호 검사, 역순 문자열 만들기 등의 작업에서 활용됩니다.
큐는 선입선출(First In First Out, FIFO) 구조로 데이터를 저장하고 처리하는데 주로 사용됩니다. 큐는 우선순위가 같은 작업 예약, 은행 업무, 티켓 예매 시스템 등에서 활용됩니다.

### 질문7. 스택과 큐의 시간복잡도는 어떻게 되나요?
스택과 큐는 모두 삽입(insert), 삭제(delete) 작업이 가능합니다.
스택의 경우, 삽입과 삭제가 모두 스택의 가장 위쪽에서 이루어지므로 시간복잡도는 O(1)입니다.
큐의 경우, 삽입은 큐의 끝(rear)에서, 삭제는 큐의 시작(front)에서 이루어지므로 삽입과 삭제 시간복잡도 모두 O(1)입니다.

### 질문8. 스택과 큐는 어떤 자료구조와 유사한가요?
스택은 배열(Array)과 유사한 자료구조입니다. 스택은 배열과 달리 크기가 가변적이지만, 마지막에 추가된 데이터가 가장 먼저 추출됩니다.
큐는 링크드 리스트(Linked List)와 유사한 자료구조입니다. 큐는 링크드 리스트와 달리 크기가 제한적이지만, 먼저 들어온 데이터가 먼저 처리됩니다.

### 질문9. 스택과 큐는 어떤 상황에서 사용하지 않는 것이 좋을까요?
스택과 큐는 각각의 구조를 이해하고 상황에 맞게 적절히 사용해야 합니다. 스택은 데이터의 삽입과 삭제가 모두 스택의 가장 위쪽에서 이루어지므로, 중간에 있는 데이터를 처리하기에는 적합하지 않습니다.
큐는 데이터의 삽입은 큐의 끝(rear)에서, 삭제는 큐의 시작(front)에서 이루어지므로, 데이터의 삽입과 삭제가 빈번하게 일어나는 상황에서는 성능이 떨어질 수 있습니다.

# 3. Deque

- 개념 : Deque(덱)는 Double Ended Queue의 약어로, 양쪽 끝에서 삽입과 삭제가 모두 가능한 선형 자료구조
- 시간복잡도 
    - 삽입/삭제 연산 : O(1)
    - 탐색 연산 : O(n)
- 장점
    - 스택과 큐의 장점을 모두 가지고 있어서 양쪽에서 삽입/삭제가 가능하다.
    - 스택과 큐를 함께 사용할 때 매우 유용함.
- 단점
    - 배열을 이용한 구현 방법의 경우 메모리 사용량이 크다.
    - 구현이 복잡하다.
- 사용되는 경우 
    - 양쪽에서 삽입/삭제가 빈번하게 일어나는 경우
    - 스택과 큐를 함께 사용해야 할 경우
    - 회문(palindrome) 판별 문제와 같이 양쪽 끝에서 접근해야 하는 경우

## 예상질문

### 질문1. Deque(덱) 자료구조란 무엇인가요?
Deque는 양쪽 끝에서 삽입과 삭제가 모두 가능한 선형 자료구조.

### 질문2. Deque의 장점은 무엇인가요?
Deque는 양쪽 끝에서 삽입과 삭제가 가능하기 때문에 스택과 큐를 합쳐놓은 것과 같은 자료구조로 다양한 상황에서 유용하게 사용됨.

### 질문3. Deque의 시간복잡도는 어떻게 되나요?
- 삽입/삭제 : 양쪽 끝에서 O(1), 중간에 삽입/삭제 시 O(n)
- 탐색 : O(n)

### 질문4. Deque와 Queue의 차이점은 무엇인가요?
Deque는 양쪽 끝에서 삽입/삭제가 가능하지만, Queue는 한쪽 끝에서 삽입, 다른 한쪽 끝에서 삭제가 가능합니다.

### 질문5. Deque의 구현 방법에는 어떤 것이 있나요?
Deque는 배열을 이용한 구현과 연결리스트를 이용한 구현이 있습니다. 배열 기반 Deque는 인덱스를 이용하여 데이터에 접근하므로 빠른 탐색이 가능하며, 연결리스트 기반 Deque는 삽입/삭제 연산이 빈번하게 일어나는 경우 유용합니다.

# 4. Priority Queue, Heap

## Priority Queue

- 개념 : 우선순위를 가진 항목들을 저장하고, 우선순위가 가장 높은 항목이 가장 먼저 꺼내지는 자료구조
- 장점 : 우선순위가 중요한 알고리즘에서 빠른 시간 안에 최소값 또는 최대값을 찾을 수 있음.
- 단점 :  우선순위 큐와 힙은 데이터 삽입 시 우선순위를 기준으로 정렬하기 때문에, 데이터가 무작위로 들어오는 경우 정렬 알고리즘보다 성능이 떨어질 수 있음.
- 시간복잡도 : 삽입과 삭제 연산: O(log n), 탐색: O(n)

## Priority Queue 구현 방법

Java에서 Priority Queue는 Java Collection Framework의 일부로 제공된다.<br>
Priority Queue는 내부적으로 heap 데이터 구조를 사용하여 구현된다. <br>
Priority Queue는 java.util 패키지에서 제공되며, PriorityQueue 클래스를 통해 사용할 수 있다. <br>
아래는 Java에서 Priority Queue를 구현한 예제 코드.

```java
import java.util.PriorityQueue;

public class Main {
  public static void main(String[] args) {
    // Integer 타입의 Priority Queue 선언
    PriorityQueue<Integer> pq = new PriorityQueue<>();

    // Priority Queue에 원소 추가
    pq.add(5);
    pq.add(2);
    pq.add(8);
    pq.add(1);

    // Priority Queue에서 원소 제거
    while (!pq.isEmpty()) {
      System.out.print(pq.poll() + " ");
    }
  }
}

```
PriorityQueue 클래스는 자체적으로 원소를 우선순위에 따라 정렬하기 때문에, poll() 메소드를 호출하면 우선순위가 가장 높은 원소가 반환됨.

## Heap

- Heap은 Priority Queue를 구현하는 방법 중 하나로, 이진 트리(binary tree)를 기반으로 우선순위를 유지하는 자료구조.
- 장점 : Priority Queue와 마찬가지로 우선순위가 중요한 알고리즘에서 빠른 시간 안에 최소값 또는 최대값을 찾을 수 있음. Heap은 자동으로 정렬되므로 정렬된 데이터를 저장하고 검색하는데 유용함.
- 단점 : 우선순위 큐와 힙은 데이터 삽입 시 우선순위를 기준으로 정렬하기 때문에, 데이터가 무작위로 들어오는 경우 정렬 알고리즘보다 성능이 떨어질 수 있음.
- 시간복잡도 : 삽입과 삭제 연산: O(log n), 탐색: O(1)

## Heap 구현방법 

Java에서 Heap을 구현하는 방법에는 크게 2가지가 있음.

### 배열을 이용한 구현
배열을 이용한 Heap 구현은 가장 간단하고 직관적인 방법입니다. 먼저, 배열을 선언하고, 각 노드의 위치를 배열의 인덱스로 지정합니다. 그리고 노드의 부모와 자식 노드를 찾는 방법은 다음과 같습니다.

부모 노드: 현재 노드의 인덱스를 2로 나눈 몫
왼쪽 자식 노드: 현재 노드의 인덱스를 2로 곱한 값
오른쪽 자식 노드: 현재 노드의 인덱스를 2로 곱한 값에 1을 더한 값
이제 Heap의 삽입과 삭제를 구현하면 됩니다. 삽입은 가장 마지막 노드에 새로운 값을 넣은 후, 부모 노드와 비교하여 Heap의 성질을 만족하도록 재배치합니다. 삭제는 가장 우선순위가 높은 노드를 삭제하고, 마지막 노드를 루트 노드로 이동시킨 후, 자식 노드와 비교하여 Heap의 성질을 만족하도록 재배치합니다.

배열로 Heap을 구현하는 예시코드는 아래와 같음.
```java
public class Heap {
    private int[] heap;
    private int size;

    public Heap(int capacity) {
        heap = new int[capacity];
    }

    /*
    insert 메서드는 새로운 값을 heap 배열에 추가하고, 
    fixHeapAbove 메서드를 호출하여 새로 추가된 값이 Heap 속성을 유지할 수 있도록 배열을 조정
    */
    public void insert(int value) {
        if (isFull()) {
            throw new IllegalStateException("Heap is full");
        }

        heap[size] = value;
        fixHeapAbove(size);
        size++;
    }

    /*
    delete 메서드는 지정된 인덱스에 해당하는 값을 삭제하고, 
    heap 배열의 끝에 있는 값을 지워진 값이 있던 인덱스 위치에 삽입함. 
    그리고 fixHeapBelow 또는 fixHeapAbove 메서드를 호출하여 Heap 속성을 유지함.
    */
    public int delete(int index) {
        if (isEmpty()) {
            throw new IllegalStateException("Heap is empty");
        }

        int parent = getParent(index);
        int deletedValue = heap[index];

        heap[index] = heap[size - 1];

        if (index == 0 || heap[index] < heap[parent]) {
            fixHeapBelow(index, size - 1);
        } else {
            fixHeapAbove(index);
        }

        size--;

        return deletedValue;
    }

    /*
    sort 메서드는 heap을 정렬함. 
    Heap에서 가장 큰 값을 가장 마지막 값과 교환하고, heap 크기를 하나 줄이고, 
    fixHeapBelow를 호출하여 Heap 속성을 만족하도록 배열을 조정한다. 
    이 작업을 heap의 크기가 1이 될 때까지 반복한다.
    */
    public void sort() {
        int lastHeapIndex = size - 1;
        for (int i = 0; i < lastHeapIndex; i++) {
            int temp = heap[0];
            heap[0] = heap[lastHeapIndex - i];
            heap[lastHeapIndex - i] = temp;

            fixHeapBelow(0, lastHeapIndex - i - 1);
        }
    }

    // printHeap 메서드는 heap 배열을 출력.
    public void printHeap() {
        for (int i = 0; i < size; i++) {
            System.out.print(heap[i]);
            System.out.print(", ");
        }
        System.out.println();
    }


    // isFull과 isEmpty 메서드는 heap 배열이 가득 찼는지 빈 배열인지 여부를 반환한다. 
    public boolean isFull() {
        return size == heap.length;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    /*
    fixHeapAbove 메서드는 주어진 인덱스의 값이 부모보다 크면 
    배열을 조정하여 Heap 속성을 만족한다.
    */
    private void fixHeapAbove(int index) {
        int newValue = heap[index];
        while (index > 0 && newValue > heap[getParent(index)]) {
            heap[index] = heap[getParent(index)];
            index = getParent(index);
        }

        heap[index] = newValue;
    }

    /* 
    fixHeapBelow 메서드는 지정된 인덱스에서 
    아래쪽으로 Heap 속성을 만족하도록 배열을 조정한다.
    */
    private void fixHeapBelow(int index, int lastHeapIndex) {
        int childToSwap;
        while (index <= lastHeapIndex) {
            int leftChild = getChild(index, true);
            int rightChild = getChild(index, false);

            if (leftChild <= lastHeapIndex) {
                if (rightChild > lastHeapIndex) {
                    childToSwap = leftChild;
                } else {
                    childToSwap = (heap[leftChild] > heap[rightChild]) ? leftChild : rightChild;
                }

                if (heap[index] < heap[childToSwap]) {
                    int tmp = heap[index];
                    heap[index] = heap[childToSwap];
                    heap[childToSwap] = tmp;
                } else {
                    break;
                }

                index = childToSwap;
            } else {
                break;
            }
        }
    }

    /*
    getParent와 getChild 메서드는 Heap 속성을 만족하는 노드 간의 관계를 계산한다. 
    getParent 메서드는 부모 노드의 인덱스를 계산하고, 
    getChild 메서드는 왼쪽 또는 오른쪽 자식 노드의 인덱스를 계산합니다.
    */
    private int getParent(int index) {
        return (index - 1) / 2;
    }

    private int getChild(int index, boolean left) {
        return 2 * index + (left ? 1 : 2);
    }
}
```

### Java에서 제공하는 PriorityQueue 클래스 이용

Java에서는 PriorityQueue 클래스를 제공하여 Heap을 쉽게 구현할 수 있음. PriorityQueue는 내부적으로 Heap을 이용하여 구현되어 있으며, 우선순위가 높은 값이 먼저 나오도록 정렬된다.

PriorityQueue 클래스를 이용하여 Heap을 구현하려면, 먼저 PriorityQueue 객체를 생성한다. 그리고 add() 메서드를 이용하여 값을 삽입하면 Heap의 성질을 만족하도록 자동으로 재배치된다. 삭제는 remove() 메서드를 이용하여 가장 우선순위가 높은 값을 삭제할 수 있다.

아래는 구현 예시 코드이다. 
```java
import java.util.PriorityQueue;

public class HeapExample {
    public static void main(String[] args) {
        // Heap 생성
        PriorityQueue<Integer> heap = new PriorityQueue<>();

        // Heap에 값 추가
        heap.add(5);
        heap.add(2);
        heap.add(10);

        // Heap에서 최소값 추출
        int min = heap.poll();

        System.out.println(min); // 2 출력
    }
}
```

## 예상질문

### 질문1. PriorityQueue와 Heap 자료구조의 차이점에 대해서 설명해주세요.
PriorityQueue는 우선순위를 가진 원소들을 저장하는 자료구조이며, Heap은 부모노드가 자식노드보다 우선순위가 높거나 같은 완전이진트리 형태의 자료구조.

### 질문2. PriorityQueue와 Heap의 시간복잡도는 어떻게 되나요?
PriorityQueue와 Heap의 삽입, 삭제 연산은 O(logN)의 시간복잡도를 가지며, 최소값/최대값 탐색은 O(1)의 시간복잡도를 가진다..

### 질문3. PriorityQueue와 Heap의 장점과 단점은 무엇인가요?
PriorityQueue와 Heap의 장점은 삽입, 삭제, 최소값/최대값 탐색이 빠르다. 단점으로는 원소의 개수가 많을 경우 메모리를 많이 차지한다는 것과, Heap의 경우 데이터의 중간 삽입, 삭제 연산이 어렵다.

### 질문4. PriorityQueue와 Heap는 어떤 경우에 사용될까요?
PriorityQueue는 우선순위 큐, 작업 스케줄링 등에서 사용된다. Heap은 다익스트라 알고리즘, 힙 정렬 등에서 사용된다.

### 질문5. PriorityQueue와 Heap의 구현 방법은 어떻게 되나요?
PriorityQueue는 Java에서 이미 구현된 우선순위 큐이며, Heap은 배열을 이용하여 구현할 수 있다. 위의 구현방법 참고.

# 5. Hash (HashSet / HashMap / HashTable / Dictionary)

## Hash

- 개념 : 키(key)와 값(value)을 저장하는 자료구조. 이는 해시 함수(hash function)을 사용하여 키를 값으로 매핑하여 값을 저장하고 검색한다. 즉, Hash 자료구조는 키를 해시 함수에 적용하여 값에 대한 고유한 인덱스를 생성한다.
- 장점
    - 빠른 검색 속도
    - 키와 값으로 구성되어 데이터를 쉽게 관리할 수 있다.
    - 대부분의 경우 평균적으로 O(1)의 상수 시간 복잡도를 가지므로 빠른 속도로 데이터를 검색할 수 있다.
- 단점
    - 최악의 경우(해시 충돌 발생) 선형 시간 복잡도(O(n))를 가질 수 있다.
    - 데이터의 삽입, 삭제, 검색의 순서가 일정하지 않을 수 있다.
    - 해시 충돌을 방지하기 위해 개별 체이닝, 오픈 어드레싱 등의 방법을 사용한다.
- 사용되는 경우
    - 검색이 빈번하게 일어나는 경우
    - 데이터를 삽입, 삭제하는 빈도가 적은 경우
    - 대용량 데이터를 다룰 때 적합.
- 구현방법
    - 자바에서는 HashSet, HashMap, HashTable 등의 클래스로 구현되어 있다.
    - 직접 구현하는 경우에는 배열과 해시 함수를 사용하여 구현한다. 
- HashSet, HashMap, HashTable, Dictionary는 모두 해시 테이블을 이용한 자료구조
    - HashSet: key가 없고 value만 가지는 자료구조입니다. 중복을 허용하지 않음
    - HashMap: key-value 쌍으로 데이터를 저장하는 자료구조. key는 중복을 허용하지 않음
    - HashTable: HashMap과 동일한 기능을 제공하지만, thread-safe하도록 구현되어 있음.
    - Dictionary: key-value 쌍으로 데이터를 저장하는 자료구조입니다. HashMap과 유사하지만, 더 이상 사용되지 않는 클래스이다.

### Hash bucket?

- 버킷(bucket)은 해시 함수에 의해 각 데이터가 저장될 위치를 나타내는 배열의 각 칸을 말한다.
- 버킷의 개수는 해시 테이블의 크기에 따라 결정되며, 각 버킷에는 하나 이상의 데이터를 저장할 수 있다. 
- 버킷의 크기는 저장 가능한 데이터의 수와 충돌 발생 빈도에 따라 결정된다.
- 각 데이터는 해시 함수에 의해 버킷의 인덱스로 변환되어 해당 버킷에 저장된다.
- 버킷의 크기가 작으면 충돌이 더 자주 발생하지만 저장 공간을 적게 사용하며, 반대로 버킷의 크기가 크면 충돌이 적게 발생하지만 더 많은 저장 공간이 필요하다.
- 따라서 적절한 버킷의 크기를 결정하는 것이 해시 테이블의 성능을 좌우하는 중요한 요소 중 하나다.

### Thread-safe

- Thread-safe란, 멀티 스레드 환경에서 여러 스레드가 동시에 접근해도 안전하게 동작하는 것을 말한다. 
- 즉, 한 스레드가 공유 자원을 사용하고 있을 때, 다른 스레드가 해당 자원에 접근해도 데이터의 일관성과 무결성을 보장해야 한다.
- 예를 들어, 여러 스레드에서 동시에 값을 변경하려는 경우 발생할 수 있는 race condition과 같은 문제를 해결하고, 동기화 메커니즘을 통해 안전하게 동작하도록 보장한다.

### 해시 충돌을 방지하기 위한 기법 : 개별 체이닝 (Separate Chaining)

해시 충돌: 서로 다른 두 개의 키가 동일한 해시값을 갖는 경우를 말한다. 

- 개별 체이닝은 해시 테이블의 각 버킷이 연결 리스트로 구성되어 있다. 
- 해시 충돌이 발생하면, 새로운 키-값 쌍은 해당 버킷의 연결 리스트에 추가된다. 
- 충돌이 발생한 경우에도 모든 데이터를 저장할 수 있습니다.
- 개별 체이닝 기법의 시간 복잡도는 해시 함수의 분포에 따라 달라지지만, 일반적으로 O(1 + α). 
- 여기서 α는 해시 충돌의 확률을 나타낸다.
- 장점: 해시 충돌이 발생해도 모든 데이터를 저장할 수 있다.
- 단점: 연결 리스트의 사용으로 인한 추가적인 메모리 공간이 필요하며, 링크드 리스트의 탐색시간이 길어질 수 있다.
- Java에서는 java.util.HashMap 클래스의 내부 구현에서 개별 체이닝 기법을 사용한다.

### 해시 충돌을 방지하기 위한 기법 : 오픈 어드레싱 (Open Addressing)

- 해시 테이블 내의 비어있는 다른 슬롯을 찾아 데이터를 저장하는 방법.
- 선형 탐사, 이차 탐사, 더블 해싱 등의 방법이 있다.

#### 1. 선형 조사 (Linear Probing)
- 해시 충돌이 발생하면, 선형 조사 기법은 바로 다음 슬롯에 데이터를 저장. 만약 그 슬롯이 이미 차 있다면, 또 다시 그 다음 슬롯을 검색하고 데이터를 저장하는 방식.
- 장점
    - 쉽고 간단한 구현이 가능하다.
    - 캐시 효율이 높다.
- 단점
    - 클러스터링이 발생할 수 있다. 
    - 선형 조사는 어느 정도의 클러스터링을 발생시킨다.
    - 삽입/삭제가 느려진다. 
    - 클러스터링으로 인해 이웃한 슬롯을 검색하는 시간이 증가한다.
    - 슬롯 사용률이 높아질수록 성능이 떨어진다.

#### 2. 제곱 조사 (Quadratic Probing)
- 해시 충돌이 발생하면, 제곱 조사 기법은 충돌 지점에서 일정 간격을 두고 다른 슬롯을 검색하여 데이터를 저장하는 방식
- 장점
    - 선형 조사와 같은 캐시 효율을 가짐.
    - 클러스터링이 발생할 가능성이 줄어든다.
- 단점
    - 클러스터링이 발생할 수 있다.
    - 선형 조사보다는 검색이 느리다.
    - 슬롯 사용률이 높아질수록 성능이 떨어진다.
#### 3. 이중 해싱 (Double Hashing)
- 이중 해싱 기법은 충돌이 발생하면, 해시 함수의 값에 따라 슬롯 간의 간격을 다르게 설정하여 다른 슬롯을 검색하여 데이터를 저장하는 방식.
- 장점
    - 클러스터링이 발생할 가능성이 매우 낮다.
    - 선형 조사와 비교할 때, 검색 속도가 더 빠르다.
- 단점
    - 구현이 복잡합니다.
    - 슬롯 사용률이 높아질수록 성능이 떨어진다.

## 예상질문

### 질문1. 해시 충돌(Collision)이란 무엇이며, 충돌이 발생하는 경우 어떻게 처리할 수 있을까요?

해시 충돌은 서로 다른 두 개의 키가 동일한 해시 값으로 매핑되어 충돌이 발생하는 경우를 말한다. 충돌을 방지하기 위한 기법으로는 개별 체이닝 기법과 오픈 어드레싱 기법이 있다. 개별 체이닝은 충돌이 발생한 버킷에 연결 리스트 형태로 데이터를 추가하는 방식이고, 오픈 어드레싱 기법은 다른 빈 버킷을 찾아서 데이터를 저장하는 방식이다.

### 질문2. HashSet의 내부 구조에 대해 설명해주세요.

HashSet은 내부적으로 HashMap을 사용한다. HashSet은 요소들을 추가할 때, 각 요소를 키로 사용하고 값으로는 더미 객체(Dummy Object)를 사용합니다. 이를 통해 중복된 요소를 제거할 수 있다.

### 질문3. Hash 자료구조의 검색 시간 복잡도는 어떻게 되나요?

Hash 자료구조는 평균적으로 O(1)의 검색 시간 복잡도를 가진다. 하지만, 최악의 경우 모든 데이터가 하나의 버킷에 저장되는 경우, 검색 시간 복잡도는 O(n)이 될 수 있습니다.

### 질문4. HashTable과 HashMap의 차이점은 무엇인가요?

HashTable과 HashMap 모두 해시맵 구조를 사용하지만, 동기화 여부에 따라 차이가 있다. HashTable은 스레드 안전을 보장하기 위해 동기화를 지원하고, HashMap은 동기화를 지원하지 않는다.

### 질문5. Hash 자료구조에서 충돌을 최소화하기 위해 해시 함수를 어떻게 설계해야 할까요?

해시 함수를 설계할 때는 다음을 고려해야 한다. 해시 값 분포를 균등하게 만들기 위해 입력 값의 여러 성질을 활용해야 하며, 해시 충돌을 최소화하기 위해 충돌이 발생할 확률이 적은 해시 함수를 선택해야 한다. 또한, 충돌 발생 시 다른 버킷에 데이터를 저장할 때 어떤 방식을 사용할지도 고려해야 한다.

# 6. Map

- 개념 : Map 자료구조는 key-value 쌍으로 이루어진 데이터를 저장하고 관리하는 자료구조다. Map은 각각의 key를 이용하여 value를 가져올 수 있기 때문에 검색 기능에 뛰어난 성능을 보인다.
- 장점 
    - 검색 기능에 뛰어난 성능을 보인다.
    - key와 value가 쌍으로 저장되기 때문에 데이터의 의미를 명확하게 전달할 수 있다. 
    - 키를 기반으로 중복을 허용하지 않기 때문에 중복된 데이터를 효과적으로 처리할 수 있다.
    - 대부분의 언어에서 Map은 내부적으로 해시 테이블을 사용하므로, 대용량 데이터를 빠르게 처리할 수 있다.
- 단점 
    - 순서를 보장하지 않기 때문에 데이터를 입력한 순서대로 순회하거나 정렬 등의 작업에는 적합하지 않다.
    - Map의 단점으로는 데이터를 저장할 때 키를 사용하므로, 키가 중복되는 경우 값이 덮어쓰여서 데이터가 손실될 수 있다는 점이 있다.
- 사용되는 경우 
    - key-value 쌍 데이터를 저장하고 검색하는 경우에 사용된다. 
    - 주로 대규모 데이터베이스의 인덱스 구현에 많이 사용된다. 
    - Map은 데이터를 키-값 쌍으로 저장하기 때문에, 키를 기반으로 데이터를 검색하거나 수정해야 하는 경우에 유용하다. 
    - 예를 들어, 사용자 정보를 저장하거나, 웹 사이트의 세션 정보를 관리하는 등의 경우에 Map을 사용할 수 있다. 
    - Map은 대부분의 프로그래밍 언어에서 지원되며, Java의 경우 HashMap, TreeMap, LinkedHashMap, WeakHashMap 등의 구현체가 제공된다.
- 시간복잡도 : key를 통한 검색 및 삽입/삭제의 시간 복잡도는 대부분 O(1)이다.

## Map 구현방법

대표적인 구현방법으로는 HashMap, TreeMap 등이 있다.

### Map 구현방법 : HashMap

HashMap은 내부적으로 해시 테이블을 사용하여 데이터를 저장하며, 시간 복잡도는 O(1)이다. 데이터를 추가하거나 검색할 때 키를 해싱하여 해시 값으로 변환하고, 이 값을 기반으로 적절한 버킷에 데이터를 저장하거나 검색한다. 하지만 해시 충돌이 발생할 경우 성능이 저하될 수 있다.

### Map 구현방법 : TreeMap

TreeMap은 레드-블랙 트리를 기반으로 데이터를 저장하며, 시간 복잡도는 O(log n)이다. 데이터를 추가하거나 검색할 때 키를 기반으로 이진 탐색을 수행하며, 데이터는 정렬된 상태로 저장된다. 따라서 정렬된 데이터에 빠르게 접근해야 하는 경우에 유용하다.

## 에상질문

### 질문1. Map 자료구조에 대해 설명해보세요. 어떤 메소드를 제공하나요?
Map은 Key-Value 쌍으로 이루어진 자료구조로, Key 값으로 Value 값을 찾아내는 용도로 사용된다. put(), get(), remove()와 같은 메소드를 제공한다.

### 질문2. HashMap과 HashTable의 차이점은 무엇인가요?
HashMap과 HashTable 모두 Key-Value 쌍으로 이루어진 Map 자료구조다. 그러나, HashMap은 동기화를 지원하지 않으며, null key와 null value를 허용한다. 반면, HashTable은 동기화를 지원하며, null key와 null value를 허용하지 않는다.

### 질문3. TreeMap 자료구조에 대해 설명해보세요. 어떤 특징이 있나요?
TreeMap은 Key 값으로 정렬된 순서를 유지한다. 이진 탐색 트리 구조로 구현되어 있으며, 검색, 추가, 삭제에 걸리는 시간 복잡도는 O(log n)입니다.

### 질문4. Map 자료구조를 어떤 상황에서 사용하면 좋을까요?
Map은 Key-Value 쌍으로 데이터를 저장하기 때문에, 데이터 검색이나 연관된 데이터를 빠르게 찾아내는데 적합합니다. 또한, 캐시나 인메모리 데이터베이스를 구현할 때도 사용된다.

### 질문5. Map 자료구조를 사용할 때 고려해야할 점은 무엇인가요?
Map을 사용할 때는 Key 값의 중복을 허용하지 않는다는 점을 주의해야 한다. Key 값의 중복을 방지하려면, 중복되는 Key 값을 처리하는 방법을 고민해야 한다. 또한, Map을 사용할 때는 데이터 양과 검색, 추가, 삭제 등의 작업에 걸리는 시간 복잡도를 고려해야 한다.

# 7. Graph

- 개념
    - 그래프는 노드(Node)와 간선(Edge)으로 이루어져 있다. 
    - 노드는 객체 또는 개체를 나타내며, 간선은 노드와 노드 사이의 연결을 나타낸다. 
    - 그래프는 방향성이 있는 방향 그래프(Directed Graph)와 방향성이 없는 무방향 그래프(Undirected Graph)로 나뉜다.
- 시간복잡도
    - 그래프 자료구조는 노드의 개수를 V, 간선의 개수를 E라고 할 때, 탐색 및 검색 작업의 시간 복잡도는 O(V+E)이다.
- 장점
    - Graph는 여러 가지 유형의 데이터와 관계를 표현할 수 있다
    - 빠른 탐색: Graph는 깊이 우선 탐색(DFS)과 너비 우선 탐색(BFS) 등 다양한 탐색 알고리즘을 사용할 수 있어, 데이터 검색 및 탐색에 용이하다.
    - 빠른 연산: Graph의 연산 시간 복잡도는 데이터의 크기에 비해 매우 빠르다. 이는 Graph가 대량의 데이터를 빠르게 처리하는 데 적합함.
    - 상호 연결성: Graph는 노드와 엣지의 상호 연결성을 강조하는 자료구조. 이는 다양한 유형의 데이터 및 관계를 구성할 수 있는 능력을 제공하며, 이러한 상호 연결성은 다른 자료구조에서 구현하기 어렵거나 불가능한 것들을 Graph에서는 쉽게 표현할 수 있음.
    - 분석과 예측: Graph는 네트워크 분석 및 예측에 매우 유용하다. 예를 들어, 소셜 네트워크에서 Graph를 사용하여 어떤 노드(사용자)가 다른 노드와의 관계를 맺을 가능성이 높은지 예측할 수 있다. 이러한 분석 및 예측 능력은 데이터 분석 분야에서 매우 중요하게 사용됨.
- 단점
    - 그래프는 간선의 개수에 따라 메모리를 많이 차지할 수 있다.
    - 그래프의 연산은 탐색과 검색이 주로 이루어지며, 이 때 시간 복잡도가 크기 때문에 대용량 데이터 처리에 적합하지 않을 수 있습니다.
- 사용되는 경우
    - 네트워크, 경로 찾기, 최단 경로 찾기 등과 같은 다양한 문제를 해결할 때 사용됩니다.

## Graph 구현

그래프 자료구조는 인접 리스트(Adjacency List)와 인접 행렬(Adjacency Matrix)로 구현할 수 있다.

### Graph 구현 : 인접행렬

- 인접 행렬은 2차원 배열을 사용하여 구현되며, 각 노드간의 연결 관계를 0과 1로 나타낸다. 
- (정점 i와 정점 j가 연결되어 있으면 matrix[i][j]의 값이 1이고, 연결되어 있지 않으면 0) 
- 가중치 그래프에서는 연결되어 있을 때 해당 가중치의 값을 넣어준다.. 
- 따라서 노드의 수가 많아질수록 메모리를 많이 차지하게 된다. 
- 연결 상태를 확인하는 시간 복잡도는 O(1)이다.
- 인접 행렬 방식의 시간 복잡도는 O(V^2)입니다.

```java
public class Graph {
    private int V;
    private int[][] matrix;

    public Graph(int V) {
        this.V = V;
        matrix = new int[V][V];
    }

    public void addEdge(int from, int to, int weight) {
        matrix[from][to] = weight;
    }

    public int getWeight(int from, int to) {
        return matrix[from][to];
    }
}
```

### Graph 구현 : 인접리스트

- 인접 리스트는 연결된 노드들을 각각 연결리스트 형태로 구현한다. 
- 따라서 각 노드마다 필요한 만큼의 메모리만 차지하므로, 인접 행렬보다 메모리 절약 효과가 있다.
- 연결 상태를 확인하는 시간 복잡도는 해당 노드와 인접한 모든 노드를 탐색해야 하므로 O(차수)이다.

```java
import java.util.*;

public class Graph {
    private int V;
    private Map<Integer, List<Edge>> adjList;

    public Graph(int V) {
        this.V = V;
        adjList = new HashMap<>();
        for (int i = 0; i < V; i++) {
            adjList.put(i, new ArrayList<>());
        }
    }

    public void addEdge(int from, int to, int weight) {
        adjList.get(from).add(new Edge(from, to, weight));
    }

    public List<Edge> getNeighbors(int vertex) {
        return adjList.get(vertex);
    }

    public class Edge {
        private int from;
        private int to;
        private int weight;

        public Edge(int from, int to, int weight) {
            this.from = from;
            this.to = to;
            this.weight = weight;
        }

        public int getFrom() {
            return from;
        }

        public int getTo() {
            return to;
        }

        public int getWeight() {
            return weight;
        }
    }
}
```

- 위의 코드에서는 인접 리스트를 Map을 이용해 구현. 
- 각 정점마다 인접한 정점들을 리스트로 저장하며, Edge 클래스는 간선의 정보를 저장함. 
- getNeighbors() 메소드를 통해 인접한 정점들의 리스트를 반환함.


## Graph 예상질문

### 질문1. Graph 자료구조란 무엇이며, 어떤 용도로 사용될까요?

Graph는 node와 edge로 이루어진 자료구조로, 다양한 현실세계의 문제를 모델링할 수 있다. 예를 들어, 지도에서 도로를 node, 도로간의 연결을 edge로 모델링할 수 있다. 또한, 소셜네트워크에서 사람들과 관계를 node와 edge로 모델링할 수 있다.

### 질문2. Graph 자료구조의 종류와 각각의 특징은 무엇인가요?

Graph는 Directed Graph와 Undirected Graph로 구분할 수 있으며, Directed Graph는 edge에 방향성이 있고, Undirected Graph는 edge에 방향성이 없다. 또한, Weighted Graph는 edge에 가중치가 있는 그래프이며, Unweighted Graph는 edge에 가중치가 없는 그래프이다.

### 질문3. Graph 자료구조에서 DFS와 BFS는 무엇이며, 어떤 차이가 있을까요?

DFS(Depth-First Search)는 깊이 우선 탐색으로, 한 방향으로 최대한 깊이 탐색한 후 다른 방향으로 이동한다. BFS(Breadth-First Search)는 너비 우선 탐색으로, 시작점으로부터 한 단계씩 모든 노드를 방문한다. DFS는 Stack 자료구조를 이용하여 구현하며, BFS는 Queue 자료구조를 이용하여 구현한다.


# 8. Tree

- 개념 : Tree 자료구조란 계층적인 구조를 가지며, 부모와 자식간의 연결로 이루어진 비순환적인 자료구조다. 그래프의 일종으로, 하나의 루트 노드를 갖고 있으며, 각 노드는 자식 노드를 여러 개 가질 수 있다. 이러한 구조로 인해 트리는 많은 분야에서 활용되고 있다
- 장점
    - 데이터를 계층적으로 구성하여 관리할 수 있어 구현이 쉬우며 유지보수도 용이함.
    - 이진 탐색 트리와 같은 트리 구조를 이용하여 빠르게 검색, 삽입, 삭제할 수 있다.
    - 트리 구조를 이용하면 자식 노드와 부모 노드 간의 참조만으로 모든 노드에 접근이 가능해지므로, 효율적인 탐색과 검색이 가능하다.
    - 이진 트리를 기반으로 한 이진 탐색 트리, 자료의 저장 및 탐색을 위한 B-tree, 신경망 알고리즘의 구현 등 다양한 분야에서 활용된다.
- 단점
    - 트리를 구현하기 위해서는 포인터를 사용해야 하기 때문에, 메모리 사용량이 많아질 수 있다.
    - 트리는 루트 노드에서부터 모든 노드를 순회하면서 작업을 수행하기 때문에, 탐색 시간이 길어질 수 있다.
- 시간복잡도 
    - 삽입, 삭제, 검색 : O(log n) (이진 탐색 트리에서 나오는 시간복잡도와 동일)
- 사용되는 곳
    - 트리 자료구조는 데이터를 계층적으로 구성해야 할 때 유용하게 사용된다. 
    - 예를 들어, 디렉토리 구조나 상위 카테고리, 하위 카테고리와 같은 계층적인 구조를 나타내기 위해 사용된다. 
    - 또한, 데이터의 탐색이나 검색이 빈번하게 일어나는 애플리케이션에서도 효과적으로 사용된다.

## Tree 구현

이진 탐색 트리, AVL 트리, 레드-블랙 트리, B-tree 로 구현할 수 있다. 

아래는 이진탐색 트리로 구현한 코드다.
```java
public class Node {
    int data;
    Node left;
    Node right;

    public Node(int data) {
        this.data = data;
        this.left = null;
        this.right = null;
    }
}

public class BinaryTree {
    Node root;

    public BinaryTree() {
        this.root = null;
    }

    public void insert(int data) {
        Node newNode = new Node(data);

        if (root == null) {
            root = newNode;
            return;
        }

        Node current = root;
        Node parent = null;

        while (true) {
            parent = current;
            if (data < current.data) {
                current = current.left;
                if (current == null) {
                    parent.left = newNode;
                    return;
                }
            } else {
                current = current.right;
                if (current == null) {
                    parent.right = newNode;
                    return;
                }
            }
        }
    }

    public void inorderTraversal(Node node) {
        if (node == null) {
            return;
        }
        inorderTraversal(node.left);
        System.out.print(node.data + " ");
        inorderTraversal(node.right);
    }

    public void preorderTraversal(Node node) {
        if (node == null) {
            return;
        }

        System.out.print(node.val + " ");
        preorderTraversal(node.left);
        preorderTraversal(node.right);
    }

    public void postorderTraversal(Node node) {
        if (node == null) {
            return;
        }

        postorderTraversal(node.left);
        postorderTraversal(node.right);
        System.out.print(node.val + " ");
    }

    public static void main(String[] args) {
        BinaryTree tree = new BinaryTree();

        tree.insert(50);
        tree.insert(30);
        tree.insert(20);
        tree.insert(40);
        tree.insert(70);
        tree.insert(60);
        tree.insert(80);

        System.out.println("Inorder traversal of the binary tree:");
        tree.inorderTraversal(tree.root);

        System.out.println("Preorder traversal of the binary tree:");
        tree.preorderTraversal(tree.root);

        System.out.println("Postorder traversal of the binary tree:");
        tree.postorderTraversal(tree.root);
    }
}
```

이 코드를 실행하면 다음과 같은 출력이 나타난다.

```java
Inorder traversal of the binary tree:
20 30 40 50 60 70 80 
Preorder traversal of the binary tree:
50 30 20 40 70 60 80 
Postorder traversal of the binary tree:
20 40 30 60 80 70 50
```

- 중위 순회는 노드를 왼쪽 자식 노드, 자신, 오른쪽 자식 노드 순서로 출력합니다. 
- 전위 순회는 노드를 자신, 왼쪽 자식 노드, 오른쪽 자식 노드 순서로 출력합니다. 
- 후위 순회는 노드를 왼쪽 자식 노드, 오른쪽 자식 노드, 자신 순서로 출력합니다.

## 예상질문

### 질문1. Tree 자료구조란 무엇이며, 어떻게 구성되어 있는지 설명해주세요.
Tree는 하나의 루트 노드에서 여러 개의 자식 노드를 가진 계층적 자료구조다. 루트 노드는 트리의 가장 상위에 있으며, 각 노드는 하나의 값과 여러 개의 자식 노드를 가질 수 있다. Tree는 반드시 사이클을 형성하지 않으며, 즉 노드간에 순환하는 경로가 없어야 한다.

### 질문2. Tree 자료구조의 종류와 각각의 특징은 무엇인가요?
대표적인 Tree 자료구조로는 Binary Tree, Binary Search Tree, AVL Tree, Red-Black Tree 등이 있다. Binary Tree는 자식 노드를 최대 두 개까지만 가지는 트리이며, Binary Search Tree는 Binary Tree에서 부모 노드보다 작은 값을 왼쪽 자식 노드에, 큰 값을 오른쪽 자식 노드에 저장하는 트리다. AVL Tree와 Red-Black Tree는 모두 균형 잡힌 트리로, 불균형한 트리의 성능을 개선하기 위해 사용된다.

### 질문3. Tree 자료구조에서 깊이(Depth)와 높이(Height)는 무엇인가요?
Tree에서 깊이는 루트 노드에서 해당 노드까지의 경로의 길이를 의미한다. 높이는 해당 노드에서 가장 깊이 있는 리프 노드까지의 경로의 길이를 의미한다. 높이는 트리의 루트 노드에서 가장 먼 리프 노드의 깊이로 정의될 수도 있다.

### 질문4. Tree 자료구조에서 노드를 삽입하는 방법은 어떤 것이 있나요?
Tree 자료구조에서 노드를 삽입하는 방법으로는 이진 탐색 트리에서의 삽입 방법이 대표적이다. 이진 탐색 트리에서는 삽입할 값을 루트 노드부터 비교해가며, 작으면 왼쪽 자식 노드로, 크면 오른쪽 자식 노드로 이동하면서 삽입할 위치를 찾아 삽입한다.

### 질문5. Tree 자료구조에서 노드를 삭제하는 방법은 어떤 것이 있나요?

Tree 자료구조에서 노드를 삭제하는 방법은 크게 3가지가 있다. 

1. Leaf Node 삭제
    - 가장 쉬운 경우로, 삭제하려는 노드가 leaf node일 경우 해당 노드를 그냥 삭제하면 된다.

2. Child Node가 하나인 Node 삭제
    - 해당 노드를 삭제하고, 해당 노드의 부모 노드와 해당 노드의 자식 노드를 직접 연결하면 됩니다.

3. Child Node가 둘인 Node 삭제
    - 해당 노드를 삭제하고, 해당 노드의 자리를 대체할 노드를 정해야 합니다.
    - 일반적으로 삭제할 노드의 왼쪽 하위 트리에서 가장 큰 값을 가지는 노드(즉, 왼쪽 하위 트리에서 가장 오른쪽에 있는 노드)나, 오른쪽 하위 트리에서 가장 작은 값을 가지는 노드(즉, 오른쪽 하위 트리에서 가장 왼쪽에 있는 노드)를 선택하여 삭제할 노드의 자리를 대체한다.
    - 이 때, 대체할 노드가 자식 노드를 가지고 있다면, 이 자식 노드를 대체할 노드의 부모 노드와 연결해주어야 합니다.
    - 만약 대체할 노드가 오른쪽 하위 트리에서 가장 작은 값을 가지는 노드라면, 해당 노드와 오른쪽 하위 트리에서 가장 작은 값을 가지는 노드 사이의 모든 노드는 삭제할 노드의 왼쪽 하위 트리의 어떤 노드보다도 크고, 오른쪽 하위 트리의 어떤 노드보다도 작은 값을 가지므로, 삭제할 노드의 왼쪽 하위 트리와 오른쪽 하위 트리를 병합해야 한다.
    - 이러한 삭제 연산은 삭제할 노드가 루트 노드일 경우 특별한 처리가 필요하다.