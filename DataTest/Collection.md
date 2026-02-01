## **1. What is the Java Collections Framework?**

**Java Collections Framework (JCF)** provides a set of interfaces, classes, and algorithms to store and manipulate groups of objects.

**Key Points:**

* Provides **standard data structures**: List, Set, Queue, Map
* Reduces **boilerplate code**
* Supports **algorithms**: sorting, searching
* Part of `java.util` package

**Hierarchy:**

```
Collection (Interface)
├─ List
├─ Set
├─ Queue
Map (Interface)
```

---

## **2. Difference between List, Set, and Map**

| Interface | Description                           | Example Classes                 | Key Points              |
| --------- | ------------------------------------- | ------------------------------- | ----------------------- |
| List      | Ordered collection, allows duplicates | ArrayList, LinkedList           | Indexed access          |
| Set       | Unordered, no duplicates              | HashSet, TreeSet, LinkedHashSet | Unique elements         |
| Map       | Key-value pairs, unique keys          | HashMap, TreeMap, LinkedHashMap | Value can be duplicated |

---

## **3. Difference between ArrayList and LinkedList**

| Feature            | ArrayList             | LinkedList             |
| ------------------ | --------------------- | ---------------------- |
| Data structure     | Dynamic array         | Doubly-linked list     |
| Access time        | O(1) (by index)       | O(n)                   |
| Insertion/Deletion | Slow (shift elements) | Fast (adjust pointers) |
| Memory overhead    | Low                   | High (extra pointers)  |

**Example:**

```java
List<String> list = new ArrayList<>();
list.add("A");
list.add("B");
```

---

## **4. Difference between HashSet, LinkedHashSet, and TreeSet**

| Feature     | HashSet     | LinkedHashSet   | TreeSet           |
| ----------- | ----------- | --------------- | ----------------- |
| Order       | No          | Insertion order | Sorted order      |
| Duplicates  | Not allowed | Not allowed     | Not allowed       |
| Performance | Fast        | Slightly slower | Slower (O(log n)) |

---

## **5. Difference between HashMap, LinkedHashMap, and TreeMap**

| Feature        | HashMap                          | LinkedHashMap                    | TreeMap                                   |
| -------------- | -------------------------------- | -------------------------------- | ----------------------------------------- |
| Order          | No                               | Insertion order                  | Sorted by key                             |
| Null key/value | 1 null key, multiple null values | 1 null key, multiple null values | No null key, multiple null values allowed |
| Performance    | Fast (O(1))                      | Slightly slower                  | Slower (O(log n))                         |

---

## **6. Difference between fail-fast and fail-safe iterators**

| Type      | Description                                                                      | Example Classes                         |
| --------- | -------------------------------------------------------------------------------- | --------------------------------------- |
| Fail-fast | Throws `ConcurrentModificationException` if collection modified during iteration | ArrayList, HashMap                      |
| Fail-safe | Does **not** throw exception; works on copy of data                              | ConcurrentHashMap, CopyOnWriteArrayList |

**Example:**

```java
List<String> list = new ArrayList<>();
for(String s : list) { list.add("new"); }  // Fail-fast → exception
```

---

## **7. Difference between Comparable and Comparator**

| Interface  | Description                          | Method                |
| ---------- | ------------------------------------ | --------------------- |
| Comparable | Defines natural ordering for objects | `compareTo(T o)`      |
| Comparator | Defines custom ordering externally   | `compare(T o1, T o2)` |

**Example (Comparable):**

```java
class Student implements Comparable<Student> {
    int age;
    public int compareTo(Student s) { return this.age - s.age; }
}
```

**Example (Comparator):**

```java
Comparator<Student> comp = (s1, s2) -> s1.age - s2.age;
```

---

## **8. Difference between Queue, Deque, and PriorityQueue**

| Interface/Class | Description                                  | Example                |
| --------------- | -------------------------------------------- | ---------------------- |
| Queue           | FIFO (first in, first out)                   | LinkedList, ArrayDeque |
| Deque           | Double-ended queue (insert/remove both ends) | ArrayDeque             |
| PriorityQueue   | Elements ordered by priority                 | PriorityQueue          |

**Example:**

```java
Queue<Integer> pq = new PriorityQueue<>();
pq.add(10);
pq.add(5);
System.out.println(pq.poll()); // 5 (lowest priority first)
```

---

## **9. What is the difference between Iterator, ListIterator, and Enumeration?**

| Interface    | Description                    | Features                      |
| ------------ | ------------------------------ | ----------------------------- |
| Iterator     | Iterates over collection       | Forward only, fail-fast       |
| ListIterator | Iterates lists bidirectionally | Forward/backward, modify list |
| Enumeration  | Legacy interface               | Forward only, not fail-fast   |

**Example:**

```java
Iterator<String> it = list.iterator();
while(it.hasNext()) { System.out.println(it.next()); }
```

---

## **10. Difference between synchronized and concurrent collections**

| Type                     | Description                                            | Example Classes                         |
| ------------------------ | ------------------------------------------------------ | --------------------------------------- |
| Synchronized Collections | Thread-safe wrapper for legacy collections             | `Collections.synchronizedList()`        |
| Concurrent Collections   | Modern thread-safe collections with better performance | ConcurrentHashMap, CopyOnWriteArrayList |

**Key Point:**

* Use **Concurrent collections** for better **performance in multithreaded apps**.

