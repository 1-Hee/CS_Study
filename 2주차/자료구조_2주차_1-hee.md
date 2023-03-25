

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
- LinkedList와 ArrayDeque 등을사용


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

## Chapter 4. Priority Queue, Heap
### Chatpter 4-1. 우선순위 큐(Priority Queue)
`우선순위 큐의 선언`

```java
import java.util.PriorityQueue;  
import java.util.Collections;  
  
//낮은 숫자가 우선 순위인 int 형 우선순위 큐 선언 
PriorityQueue<Integer> priorityQueueLowest = new PriorityQueue<>();  
  
//높은 숫자가 우선 순위인 int 형 우선순위 큐 선언 
PriorityQueue<Integer> priorityQueueHighest = new PriorityQueue<>(Collections.reverseOrder());  
  
// 우선순위 큐의 데이터 추가
// add method를 사용하면, 우선순위 큐에 자료가 성공적으로 추가되었을 경우 true를 리턴한다.  
priorityQueueHighest.add(1); priorityQueueHighest.add(10);  
priorityQueueHighest.offer(100); // PQ 또한 offer로 데이터 추가 가능!
```  
  
### **우선순위 큐(Priority Queue)의 특징**  
1. 큐(Queue)와 같이 선입선출(FIFO)의 특징을 갖는 자료구조  
2. 다만, 데이터가 들어온 순서대로 나가는 것이 아니라 우선순위가 높은 순서대로 데이터가 나가는 특징을 갖는 자료구조  
3. 따라서 ProrityQueue를 사용할 때는 반드시 우선순위를 설정이 필수적이다.  
4. 우선순위를 설정하는 방법은 ① 우선순위 큐에 들어갈 자료구조를 Comparable 인터페이스를 구현(implements) 하여 사용하거나, ② Priority Queue를 선언할 때 생성자에 Comparator를 구현 하여 우선순위를 설정해주어야 한다.  
5. 이때 우선순위를 결정하는 기준은 PriorityQueue에 저장될 자료구조가 reference type이라면 객체로부터 얻을 수 있는 숫자형 자료구조(int 등)의 대소 비교를 통해 결정하게 된다.  
6. 그러므로 Comparable를 구현하거나 Comparator를 생성할 때 어떤 방법이든 두 자료형의 대소를 비교하는 compareTo 메서드를 Override 해야한다.  
7. Priority Queue안에 저장되는 데이터들은 Heap으로 관리되며 완전 이진트리의 일종이다.  
8. Priority Queue는 시간 복잡도는 O(NLogN)이다.  
  
  
### Chatpter 4-2. 힙(Heap)
```java
// 힙의 구현, 블로그 참조
// https://st-lab.tistory.com/205

package com.java.j0325;

import java.util.Arrays;
import java.util.Comparator;
import java.util.NoSuchElementException;

public class Heap<E> {
 
	private final Comparator<? super E> comparator;
	private static final int DEFAULT_CAPACITY = 10;	// 최소(기본) 용적 크기 
    
	private int size;	// 요소 개수 
 
	private Object[] array;	// 요소를 담을 배열 
 
	// 생성자 Type 1 (초기 공간 할당 X)
	public Heap() {
		this(null);
	}
	
	public Heap(Comparator<? super E> comparator) {
		this.array = new Object[DEFAULT_CAPACITY];
		this.size = 0;
		this.comparator = comparator;
	}
    
	// 생성자 Type 2 (초기 공간 할당 O)
	public Heap(int capacity) {
		this(capacity, null);
	}
	
	public Heap(int capacity, Comparator<? super E> comparator) {
		this.array = new Object[capacity];
		this.size = 0;
		this.comparator = comparator;
	}
    
 
	// 받은 인덱스의 부모 노드 인덱스를 반환
	private int getParent(int index) {
		return index / 2;
	}
	
	// 받은 인덱스의 왼쪽 자식 노드 인덱스를 반환 
	private int getLeftChild(int index) {
		return index * 2;
	}
	
	// 받은 인덱스의 오른쪽 자식 노드 인덱스를 반환
	private int getRightChild(int index) {
		return index * 2 + 1;
	}
	
	
	/**
	 * @param newCapacity 새로운 용적 크기
	 */
	private void resize(int newCapacity) {
		
		// 새로 만들 배열
		Object[] newArray = new Object[newCapacity];
			
		// 새 배열에 기존에 있던 배열의 요소들을 모두 복사해준다.
		for(int i = 1; i <= size; i++) {
			newArray[i] = array[i];
		}
			
		/*
		 *  현재 배열은 GC 처리를 위해 null로 처리한 뒤, 
		 *  새 배열을 연결해준다.  
		 */
		this.array = null;
		this.array = newArray;
			
	}
	
	public void add(E value) {
		
		// 배열 용적이 꽉 차있을 경우 용적을 두 배로 늘려준다. 
		if(size + 1 == array.length) {
			resize(array.length * 2);
		}
			
		siftUp(size + 1, value);	// 가장 마지막에 추가 되는 위치와 넣을 값(타겟)을 넘겨줌
		size++;	// 정상적으로 재배치가 끝나면 사이즈를 증가
	}
		
	// 상향 선별
	/**
	 * @param idx	추가할 노드의 인덱스 
	 * @param target	재배치 할 노드
	 */
	private void siftUp(int idx, E target) {	
		// comparator가 존재할 경우 comparator 을 인자로 넘겨준다.
		if(comparator != null) {
			siftUpComparator(idx, target, comparator);
		}
		else {
			siftUpComparable(idx, target);
		}
	}
	 
	// Comparator을 이용한 sift-up
	@SuppressWarnings("unchecked")
	private void siftUpComparator(int idx, E target, Comparator<? super E> comp) {		
	 
		// root노드보다 클 때까지만 탐색한다.
		while(idx > 1) {
			int parent = getParent(idx);	// 삽입노드의 부모노드 인덱스 구하기
			Object parentVal = array[parent];	// 부모노드의 값
			
			// 타겟 노드 값이 부모노드보다 크면 반복문 종료
			if(comp.compare(target, (E) parentVal) >= 0) {
				break;
			}
				
			/*
			 * 부모노드가 타겟노드보다 크므로
			 * 현재 삽입 될 위치에 부모노드 값으로 교체해주고
			 * 타겟 노드의 위치를 부모노드의 위치로 변경해준다. 
			 */
			array[idx] = parentVal;
			idx = parent;
		}
			
		// 최종적으로 삽입될 위치에 타겟 노드 값을 저장해준다.
		array[idx] = target;
	}
	 
	// 삽입 할 객체의 Comparable을 이용한 sift-up
	@SuppressWarnings("unchecked")
	private void siftUpComparable(int idx, E target) {
			
		// 타겟노드가 비교 될 수 있도록 한 변수를 만든다. 
		Comparable<? super E> comp = (Comparable<? super E>) target;
			
		while(idx > 1) {
			int parent = getParent(idx);
			Object parentVal = array[parent];
				
			if(comp.compareTo((E)parentVal) >= 0) {
				break;
			}
			array[idx] = parentVal;
			idx = parent;
		}
		array[idx] = comp;
	}
	
	@SuppressWarnings("unchecked")
	public E remove() {
		if(array[1] == null) {	// 만약 root가 비어있을경우 예외를 던지도록 함
			throw new NoSuchElementException();
		}
	    
		E result = (E) array[1];	// 삭제된 요소를 반환하기 위한 임시 변수 
		E target = (E) array[size];	// 타겟이 될 요소
		array[size] = null;	// 타겟 노드를 비운다.
			
		// 삭제할 노드의 인덱스와 이후 재배치 할 타겟 노드를 넘겨준다.
		siftDown(1, target);	// 루트 노드가 삭제되므로 1을 넘겨준다.
			
		return result;
	}
		
		
	/**
	 * @param idx	삭제할 노드의 인덱스 
	 * @param target	재배치 할 노드
	 */
	private void siftDown(int idx, E target) {
		// comparator가 존재할 경우 comparator 을 인자로 넘겨준다.
		if(comparator != null) {
			siftDownComparator(idx, target, comparator);
		}
		else {
			siftDownComparable(idx, target);
		}
	}
		
	// Comparator을 이용한 sift-down
	@SuppressWarnings("unchecked")
	private void siftDownComparator(int idx, E target, Comparator<? super E> comp) {
			
		array[idx] = null;	// 삭제 할 인덱스의 노드를 삭제
		size--;	
				
		int parent = idx;	// 삭제노드부터 시작 할 부모를 가리키는 변수
		int child;	// 교환 될 자식을 가리키는 변수
			
		// 왼쪽 자식 노드의 인덱스가 요소의 개수보다 작을 때 까지 반복
		while((child = getLeftChild(parent)) <= size) {
				
			int right = getRightChild(parent);	// 오른쪽 자식 인덱스
				
			Object childVal = array[child];	// 왼쪽 자식의 값 (교환 될 값) 
				
			/*
			 *  오른쪽 자식 인덱스가 size를 넘지 않으면서
			 *  왼쪽 자식이 오른쪽 자식보다 큰 경우
			 *  재배치 할 노드는 작은 자식과 비교해야하므로 child와 childVal을
			 *  오른쪽 자식으로 바꿔준다. 
			 */
			if(right <= size && comp.compare((E) childVal, (E) array[right]) > 0) {
				child = right;
				childVal = array[child];
			}
				
			// 재배치 할 노드가 자식 노드보다 작을경우 반복문을 종료한다. 
			if(comp.compare(target ,(E) childVal) <= 0){
				break;
			}
				
			/*
			 *  현재 부모 인덱스에 자식 노드 값을 대체해주고 
			 *  부모 인덱스를 자식 인덱스로 교체
			 */
			array[parent] = childVal;
			parent = child;
		}
			
		// 최종적으로 재배치 되는 위치에 타겟이 된 값을 넣어준다.
		array[parent] = target;
			
		/*
		 *  용적의 사이즈가 최소 용적보다는 크면서 요소의 개수가 전체 용적의 1/4일경우 
		 *  용적을 반으로 줄임(단, 최소용적보단 커야함)
		 */
		if(array.length > DEFAULT_CAPACITY && size < array.length / 4) {
			resize(Math.max(DEFAULT_CAPACITY, array.length / 2));
		}
	 
	}
		
	// Comparable을 이용한 sift-down
	@SuppressWarnings("unchecked")
	private void siftDownComparable(int idx, E target) {
			
		Comparable<? super E> comp = (Comparable<? super E>) target;
			
		array[idx] = null;
		size--;
			
		int parent = idx;
		int child;
	 
		while((child = getLeftChild(parent)) <= size) {
				
			int right = getRightChild(parent);
				
			Object childVal = array[child];
			
			if(right <= size && ((Comparable<? super E>)childVal).compareTo((E)array[right]) > 0) {
				child = right;
				childVal = array[child];
			}
				
			if(comp.compareTo((E) childVal) <= 0){
				break;
			}
			array[parent] = childVal;
			parent = child;
				
		}
		array[parent] = comp;
			
		if(array.length > DEFAULT_CAPACITY && size < array.length / 4) {
			resize(Math.max(DEFAULT_CAPACITY, array.length / 2));
		}
			
	}
	
	public int size() {
		return this.size;
	}
		
	@SuppressWarnings("unchecked")
	public E peek() {
		if(array[1] == null) {
			throw new NoSuchElementException();
		}		
		return (E)array[1];
	}
	 
	public boolean isEmpty() {
		return size == 0;
	}
	 
	public Object[] toArray() {
		return Arrays.copyOf(array, size + 1);
	}
}
```
    
**힙(Heap)의 특징**  
1. 완전 이진트리 방식을 통해 자료구조를 구현한다.  
2. 중복된 값이 존재할 수 있다. (최대, 최소 값 출력에 유리함)  
3. 보통 힙의 구현은 배열(Array)로 이루어진다.  
4. 힙은 최대값, 최소값 검색에 대해 logN의 굉장히 빠른 속도를 가진다. (루트만 반환, 삭제하면 됨)  
5. 데이터를 삽입할 때 우선순위를 기준으로 최대 힙 혹은 최소 힙을 구성하고 데이터를 꺼낼 때 루트 노드를 얻어낸 뒤 루트 노드를 삭제할 때는 빈 루트 노드 위치에 맨 마지막 
6. 노드를 삽입한 후 아래로 내려가면서 적절한 자리를 찾아 옮기는 방식으로 구현한다.
---
<br>

## Chapter 5. Hash
`Hash의 선언`
```java
import java.util.HashMap;
import java.util.HashSet;
import java.util.Hashtable;

public class Hash {
	
	public static void main(String[] args) {
		Hashtable<Integer, String> htable = new Hashtable<>();
		HashMap<Integer, String> hmap = new HashMap<>();
		HashSet<Integer> hset = new HashSet<>();
		
		htable.put(1, "hello");
		hmap.put(1, "world");
		hset.add(3);
		
		System.out.println(htable.toString()); // {1=hello}
		System.out.println(hmap.toString()); // {1=world}
		System.out.println(hset.toString()); // [3]

	}

}
```
### Hash의 특징
1. Hash는 내부적으로 배열을 사용하여 데이터를 저장하기 때문에 빠른 검색속도를 갖는다.  
2. 그리고 데이터 추가/삭제시 기존 데이터를 밀어내거나 당기는 작업이 필요없도록 특별한 알고리즘을 이용하여 데이터와 연관된 고유한 숫자를 만들어 낸 뒤 이를 인덱스로 사용한다.  
3.  특정 데이터가 저장되는 인덱스를 그 데이터만의 고유한 위치로 정하여서 데이터 추가/삭제시 데이터의 이동이 없도록 만들어진 구조이다.

### `조회: 평균 O(1) / 최악 O(N)`

#### 해시 충돌(Hash Collision)
- 두 개 이상의 키(해시 함수의 입력값)가 해시 테이블의 동일한 인덱스(해시 함수의 출력값)에 매핑되는 현상

#### 왜 일어나는가?
① **비둘기집 원리** : n+1개의 물건을 n개의 상자에 넣을 때 적어도 어느 한 상자에는 두 개 이상의 물건이 들어 있다는 원리
②  **생일 문제** : 여러 사람이 모였을 때 생일이 같은 2명이 존재할 확률은? (23명 -> 50%, 57명 -> 99%)

**✅ 충돌은 생각보다 쉽게 일어남**

### 📚 해결 방법
1. Chaining : 해시 테이블의 인덱스가 해당 인덱스에 연결된 항목들을 담은 연결리스트를 가리키게 한다. (java)
2. Open Addressing : 충돌 발생 시 탐사를 통해 다음 빈 공간을 찾는다 (Python)

### Java의 Hash 자료구조 : HashMap,  HashTable,  HashSet
→  **Key(키) - Value(값) 매핑**이 가능한 자료구조

---
<br>

## Chapter 6. Graph
`Graph의 예시 -> graph 구조를 통한 bfs, dfs 탐색`
```java
import java.util.Scanner;

public class Graph {	
	static class Node{
		int to;
		Node next;
		public Node(int to, Node next) {
			super();
			this.to = to;
			this.next = next;
		}		
	}
	
	static Node[] adjList;
	static boolean[] visited;
	static int N;
	
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		N = sc.nextInt();
		int E = sc.nextInt();
		
		adjList = new Node[N];
		visited = new boolean[N];
		
		for (int i = 0; i < E ; i++) { // 간선 정보에 해당하는 부분만 덮어쓰기.
			int from = sc.nextInt();
			int to = sc.nextInt();					
			adjList[from] = new Node(to, adjList[from]);
			adjList[to] = new Node(from, adjList[to]);
		}		
		dfs(0);
	}

	private static void dfs(int cur) {
		visited[cur] = true;
		System.out.print((char)(cur+'A'));
		
		// 현재 정점의 인접 정점들을 큐에 넣어서 나중에 탐색하도록 만들기		
		for (Node temp = adjList[cur]; temp != null; temp = temp.next) {
			if(!visited[temp.to]) { // 방문가능하고 && 인접한 경우
				dfs(temp.to);
			}
		}
	}
}
```

### Graph의 특징
1. 노드(node/vertex)와 간선(edge)으로 구성된 자료의 집합
2. 노드(Node): 정보의 단위, 간선(Edge): 노드 간의 관계
3. 인접리스트 / 인접행렬로 구현


## Chapter 6. Tree

### `Tree: 사이클이 없는 연결 그래프`

Tree 용어
-   노드(node): 트리를 구성하는 기본 원소    
    -   루트 노드(root node/root): 트리에서 부모가 없는 최상위 노드, 트리의 시작점
    -   부모 노드(parent node): 루트 노드 방향으로 직접 연결된 노드
    -   자식 노드(child node): 루트 노드 반대방향으로 직접 연결된 노드
    -   형제 노드(siblings node): 같은 부모 노드를 갖는 노드들
    -   리프 노드(leaf node/leaf): 루트 노드를 제외한 차수가 1인 정점 (자식이 없는 노드)
-   경로(path): 한 노드에서 다른 한 노드에 이르는 길 사이에 있는 노드들의 순서
    
-   길이(length): 출발 노드에서 도착 노드까지 거치는 간선의 개수
    
-   깊이(depth): 루트 경로의 길이
    
-   레벨(level): 루트 노드(level=0)부터 노드까지 연결된 간선 수의 합
    
-   높이(height): 가장 긴 루트 경로의 길이
    
-   차수(degree): 각 노드의 자식의 개수
    
-   트리의 차수(degree of tree): 트리의 최대 차수
    
-   크기(size): 노드의 개수
    
### Tree vs Graph
- 트리는 순환구조를 갖지 않음

### [](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md#%EC%9D%B4%EC%A7%84%ED%8A%B8%EB%A6%AC-binary-tree)이진트리 (Binary Tree)

[![](https://github.com/Bluuubery/CS_interview_study/raw/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-08-23-54-22.png)](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-08-23-54-22.png)

- 모든 노드의 차수가 2 이하인 트리
- 다진 트리에 비해 훨씬 간결하고 알고리즘을 구현하기 쉬워서 많이 쓴다!
- 이진트리의 종류

### [](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md#%EC%9D%B4%EC%A7%84-%ED%83%90%EC%83%89-%ED%8A%B8%EB%A6%AC-binary-search-tree)이진 탐색 트리 (Binary Search Tree)

[![](https://github.com/Bluuubery/CS_interview_study/raw/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-08-23-57-39.png)](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-08-23-57-39.png)

- 노드의 왼쪽 가지에는 노드의 값보다 작은 값들만 있고, 오른쪽 가지에는 큰 값들만 있도록 구성된 이진트리
- (이상적인 상황에서) 탐색/삽입/삭제: O(logN)
-   최악의 경우(편향): O(N) (ex: 1~100)

### [](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md#%ED%8A%B8%EB%A6%AC%EC%9D%98-%EC%88%9C%ED%9A%8C)트리의 순회

[![](https://github.com/Bluuubery/CS_interview_study/raw/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-08-23-38-03.png)](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-08-23-38-03.png)

- 중위 순회(in-order traversal): 왼쪽 자손, 자신, 오른쪽 자손 순서로 방문하는 순회 방법
-  이진 탐색 트리 중위 순회 시 정렬된 결과 반환
-  전위 순회(pre-order traversal): 자신, 왼쪽 자손, 오른쪽 자손 순서로 방문하는 순회 방법
-  후위 순회(post-order traversal): 왼쪽 자손, 오른쪽 자손, 자신 순서로 방문하는 순회 방법
-   레벨 순서 순회(level-order traversal): 레벨 순서로 순회(BFS)

## 8. Advanced Tree

### [](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md#avl-tree)AVL Tree

[![avltree](https://camo.githubusercontent.com/12b1b2316c4993f91c6f1bce78d256da9570ea391dc55dee96c2f8c265bd23d4/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f662f66642f41564c5f547265655f4578616d706c652e676966)](https://camo.githubusercontent.com/12b1b2316c4993f91c6f1bce78d256da9570ea391dc55dee96c2f8c265bd23d4/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f662f66642f41564c5f547265655f4578616d706c652e676966)

-  **자가 균형 이진 탐색 트리** == `Advanced Tree`
- 일반적인 이진 탐색 트리의 편향성을 보완하기 위해 삽입/삭제 시마다 균형을 맞춰준다 (트리 회전)
- 오른쪽 트리와 왼쪽 트리의 높이 차가 1 이하
- 모든 상황에서 탐색/삽입/삭제: O(logN)

### [](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md#red-black-tree)Red-Black Tree

[![](https://github.com/Bluuubery/CS_interview_study/raw/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-09-00-17-55.png)](https://github.com/Bluuubery/CS_interview_study/blob/master/2_%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/assets/2%EC%A3%BC%EC%B0%A8_%EC%9C%A0%EC%84%A0%EC%A4%80.md/2023-02-09-00-17-55.png)

### 자가 균형 이진 탐색 트리란?
📌 전제 조건
1.  모든 노드는 red or black
2.  루트 노드는 black    
3.  자식이 없는 노드는 Null Leaf Node (NIL)라고 한다    
4.  모든 NIL은 black    
5.  red의 자식은 언제나 black -> red는 연속으로 나올 수 없다! (black은 가능)    
6.  임의의 한 노드에서 null leaf node까지 도달하는 모든 경로에는 null leaf node를 제외하고 항상 같은 수의 블랙 노드 존재
    
- 모든 상황에서 탐색/삽입/삭제: O(logN)
- 이진탐색트리 중에 가장 성능이 좋아 일반적으로 많이 사용!

## 9. union-find

### `서로소 집합(Disjoint Set)`
- 여러 개의 노드가 존재할 때, 임의의 두 노드가 같은 그래프에 속해있는지 판별

### Union & Find
**Find**   : 노드 x가 포함된 집합을 찾는 연산
```
def  find_parent(parent, current):
     if  parent[current] != current:
         return  find_parent(parent, parent[current])
     return  current
```
✔  **Union**  : 노드 x가 포함된 집합과 노드 y가 포함된 두 집합을 통합하는 연산
```
def  union_parent(parent, x, y):
     x = find_parent(parent, x)
     y = find_parent(parent, y)
     # 단순한 형태에서는 작은 쪽으로 합친다.
     if  x < y:
         parent[y] = x
     else:
         parent[x] = y
```
예제 코드
```python
# 노드와 간선(union 연산) 개수
node, edge = map(int, input().split())

# 0으로 부모 배열 초기화
parent = [0  for  _  in  range(node + 1)]

# 부모를 자기 자신으로 초기화
for  i  in  range(1, node + 1):
parent[i] = i

# union 연산
for  i  in  range(edge):
a, b = map(int, input().split())
union_parent(parent, a, b)

# 각 원소가 속해있는 집합 출력
for  i  in  range(1, node + 1):
print(find_parent(parent, i), end=' ')
print()

# 부모 테이블 출력
for  i  in  range(1, node + 1):
print(parent[i], end=' ')
```

### 최적화 : 경로 압축 (Path compression)

```python
# 경로 압축 -> 부모값 재귀적으로 갱신
def  find_parent_compression(parent, node):
    if  parent[node] != node:
        parent[node] = find_parent_compression(parent, parent[node])
    return  parent[node]
```
###  Rank 이용 (Union by Rank)

```python
# rank: 각 노드의 rank를 저장할 리스트
rank = [0 for _ in range(N + 1)]

# def union_parent_rank(x, y):
    x = find_parent(x)
    y = find_parent(y)
    if x == y:
        return
    # 랭크가 낮은 집합을 높은 집합으로 병합해준다
    if rank[x] > rank[y]:
        parent[y] = x
    else:
        parent[x] = y
        # 랭크가 동일할 경우
        if rank[x] == rank[y]:
            rank[y] += 1
```

### 📙  샘플 코드
```python
def find_parent(x):
    if parent[x] != x:
        parent[x] = find_parent(parent[x])
    return parent[x]

def union_parent(x, y):
    x = find_parent(x)
    y = find_parent(y)
    if x == y:
        return
    if rank[x] > rank[y]:
        parent[y] = x
    else:
        parent[x] = y
        if rank[x] == rank[y]:
            rank[y] += 1

# 노드와 간선(union 연산) 개수 
node, edge =  map(int,  input().split())  
# 0으로 부모 배열 초기화 
parent =  [0  for _ in  range(node +  1)]
# 1로 랭크 초기화
rank = [1 for _ in range(node + 1)]

# 부모를 자기 자신으로 초기화
for  i  in  range(1, node + 1):
    parent[i] = i

# union 연산
for  i  in  range(edge):
    a, b = map(int, input().split())
    union_parent(a, b)

# 각 원소가 속해있는 집합 출력
for  i  in  range(1, node + 1):
    print(find_parent(i), end=' ')
print()

# 부모 테이블 출력
for  i  in  range(1, node + 1):
    print(parent[i], end=' ')
```

### Weighted Union Find
- parent 배열이 음수일 경우 부모노드로서 음수의 절댓값이 size(rank)가 되고, 양수일 경우 부모노드를 가리킨다

```python
parent = [-1 for _ in range(N + 1)]

def find_parent(x):
    if parent[x] < 0:
        return x
    p = find(parent[x])
    parent[x] = p
    return p

def union_parent(x, y):
    x = find_parent(x)
    y = find_parent(y)

    if x == y:
        return

    if parent[x] < parent[y]:
        parent[x] += parent[y]
        parent[y] = x
    else:
        parent[y] += parent[x]
        parent[x] = y
```

---
### 💡 질문 
- Q1. 정적 배열 int[]와 컬렉션 프레임 워크이 일종인 ArrayList의 차이점은 무엇인가요?
- Q2. 벡터(Vector)와 ArrayList와의 차이점은 무엇인가요?
- Q3. 연결리스트의 특징에 대해 설명해주세요.
- Q4. 스택과 큐의 특징에 대해 설명해주세요.
- Q5. Heap이란 무엇인가요?
- Q6. 우선순위 큐의 특징은 무엇인가요?
- Q7. 해시 충돌(Hash Collision)이 일어나는 원인과 해결책을 설명해주세요.
- Q8. 그래프란 무엇이고 어떤 자료구조로 관리하나요?
- Q9. 그래프 자료구조에서 길이(length)란 무엇인가요?
- Q10. 그래프 자료구조에서 쓰이는 용어 3가지만 고르고 각 용어가 의미하는 바를 설명해보세요.