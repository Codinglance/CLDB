

## **1. What are the main features of Java?**

**Java** is a widely-used, platform-independent, object-oriented programming language.

**Key Features:**

* **Object-Oriented:** Encapsulation, inheritance, polymorphism, abstraction
* **Platform-independent:** Write once, run anywhere (JVM)
* **Robust & Secure:** Exception handling, type checking
* **Multithreaded:** Built-in support for threads
* **Automatic memory management:** Garbage collection
* **Rich API & Libraries:** Collections, I/O, Networking, etc.

---

## **2. Difference between JDK, JRE, and JVM**

| Component | Description                                                             |
| --------- | ----------------------------------------------------------------------- |
| **JVM**   | Java Virtual Machine; runs Java bytecode on any platform                |
| **JRE**   | Java Runtime Environment; includes JVM + libraries to run Java programs |
| **JDK**   | Java Development Kit; includes JRE + compiler + tools for development   |

---

## **3. Difference between `==` and `.equals()`**

| Operator / Method | Description                                                      |
| ----------------- | ---------------------------------------------------------------- |
| `==`              | Checks reference equality (whether objects point to same memory) |
| `.equals()`       | Checks structural equality (whether object contents are equal)   |

**Example:**

```java
String a = "Hello";
String b = new String("Hello");

System.out.println(a == b);       // false (different references)
System.out.println(a.equals(b));  // true (same content)
```

---

## **4. What is the difference between abstract class and interface?**

| Feature     | Abstract Class                   | Interface                              |
| ----------- | -------------------------------- | -------------------------------------- |
| Inheritance | Single / multiple via implements | Multiple inheritance possible          |
| Methods     | Abstract + concrete allowed      | Only abstract + default/static methods |
| Constructor | Can have constructor             | No constructor                         |
| Variables   | Instance variables allowed       | Only static final (constants)          |

---

## **5. What are Java access modifiers?**

**Access modifiers control visibility of classes, methods, and variables.**

| Modifier    | Visibility                  |
| ----------- | --------------------------- |
| `private`   | Only within class           |
| `default`   | Within package              |
| `protected` | Within package + subclasses |
| `public`    | Everywhere                  |

---

## **6. What is Java memory model (Heap & Stack)?**

**Memory areas in Java:**

* **Heap:** Stores objects and instance variables; managed by garbage collector
* **Stack:** Stores method call frames and local variables; auto cleaned after method ends
* **Method Area:** Stores class-level info (static variables, metadata)
* **PC Register & Native Area:** JVM internals

**Example:**

```java
void example() {
    int x = 5;            // stored in stack
    String s = new String("Hello"); // object in heap
}
```

---

## **7. What is the difference between `ArrayList` and `LinkedList`?**

| Feature            | ArrayList             | LinkedList             |
| ------------------ | --------------------- | ---------------------- |
| Underlying data    | Dynamic array         | Doubly-linked list     |
| Access time        | O(1) (by index)       | O(n)                   |
| Insertion/deletion | Slow (shift elements) | Fast (adjust pointers) |
| Memory usage       | Less                  | More (extra pointers)  |

---

## **8. What is a Java thread and how to create one?**

**Thread:** Lightweight process allowing concurrent execution.

**Creating Threads:**

1. **Extend Thread class**

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running");
    }
}
```

2. **Implement Runnable interface**

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable running");
    }
}
```

**Starting thread:**

```java
MyThread t = new MyThread();
t.start();
```

---

## **9. What is the difference between `throw` and `throws`?**

| Keyword  | Description                                                     |
| -------- | --------------------------------------------------------------- |
| `throw`  | Used inside method to throw a single exception object           |
| `throws` | Declares the exceptions a method might throw (method signature) |

**Example:**

```java
void check(int a) throws IOException {
    if(a < 0) throw new IOException("Negative value");
}
```

---

## **10. Difference between `final`, `finally`, and `finalize()`**

| Keyword / Method | Description                                                           |
| ---------------- | --------------------------------------------------------------------- |
| `final`          | Used with class/method/variable; prevents modification or inheritance |
| `finally`        | Block executed after try/catch; always runs                           |
| `finalize()`     | Method called by GC before object destruction                         |

**Example:**

```java
final int x = 10;      // cannot change
try { /* code */ } finally { System.out.println("Always runs"); }
protected void finalize() { System.out.println("Object GCed"); }
```
