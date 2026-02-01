
## **1. Reverse an Array**

**Problem:** Reverse the elements of an array.

```java
public class ReverseArray {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        for (int i = arr.length - 1; i >= 0; i--) {
            System.out.print(arr[i] + " ");
        }
    }
}
```

**Output:**

```
5 4 3 2 1
```

---

## **2. Find Maximum and Minimum in an Array**

```java
public class MaxMinArray {
    public static void main(String[] args) {
        int[] arr = {5, 2, 9, 1, 7};
        int max = arr[0], min = arr[0];
        for (int num : arr) {
            if (num > max) max = num;
            if (num < min) min = num;
        }
        System.out.println("Max: " + max);
        System.out.println("Min: " + min);
    }
}
```

**Output:**

```
Max: 9
Min: 1
```

---

## **3. Reverse a Linked List (Singly)**

```java
class Node {
    int data;
    Node next;
    Node(int data) { this.data = data; }
}

public class ReverseLinkedList {
    public static Node reverse(Node head) {
        Node prev = null, curr = head;
        while (curr != null) {
            Node next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        return prev;
    }

    public static void printList(Node head) {
        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head = reverse(head);
        printList(head);
    }
}
```

**Output:**

```
3 2 1
```

---

## **4. Check if a String is Palindrome**

```java
public class PalindromeString {
    public static void main(String[] args) {
        String str = "level";
        String reversed = new StringBuilder(str).reverse().toString();
        if (str.equals(reversed)) {
            System.out.println(str + " is a palindrome");
        } else {
            System.out.println(str + " is not a palindrome");
        }
    }
}
```

**Output:**

```
level is a palindrome
```

---

## **5. Find Factorial using Recursion**

```java
public class Factorial {
    public static int factorial(int n) {
        if (n == 0 || n == 1) return 1;
        return n * factorial(n - 1);
    }

    public static void main(String[] args) {
        int num = 5;
        System.out.println("Factorial of " + num + " is " + factorial(num));
    }
}
```

**Output:**

```
Factorial of 5 is 120
```

---

## **6. Fibonacci Series using Iteration**

```java
public class Fibonacci {
    public static void main(String[] args) {
        int n = 10, a = 0, b = 1;
        System.out.print(a + " " + b + " ");
        for (int i = 2; i < n; i++) {
            int c = a + b;
            System.out.print(c + " ");
            a = b;
            b = c;
        }
    }
}
```

**Output:**

```
0 1 1 2 3 5 8 13 21 34
```

---

## **7. Implement Stack using Array**

```java
class Stack {
    int[] arr;
    int top = -1;
    int capacity;

    Stack(int size) {
        arr = new int[size];
        capacity = size;
    }

    void push(int x) {
        if (top == capacity - 1) {
            System.out.println("Stack Overflow");
            return;
        }
        arr[++top] = x;
    }

    int pop() {
        if (top == -1) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return arr[top--];
    }

    public static void main(String[] args) {
        Stack stack = new Stack(5);
        stack.push(10);
        stack.push(20);
        System.out.println(stack.pop()); // 20
        System.out.println(stack.pop()); // 10
    }
}
```

---

## **8. Implement Queue using Array**

```java
class Queue {
    int[] arr;
    int front = 0, rear = 0, capacity;

    Queue(int size) { arr = new int[size]; capacity = size; }

    void enqueue(int x) {
        if (rear == capacity) { System.out.println("Queue Full"); return; }
        arr[rear++] = x;
    }

    int dequeue() {
        if (front == rear) { System.out.println("Queue Empty"); return -1; }
        return arr[front++];
    }

    public static void main(String[] args) {
        Queue q = new Queue(5);
        q.enqueue(10); q.enqueue(20);
        System.out.println(q.dequeue()); // 10
        System.out.println(q.dequeue()); // 20
    }
}
```

---

## **9. Binary Search in a Sorted Array**

```java
public class BinarySearch {
    public static int binarySearch(int[] arr, int target) {
        int left = 0, right = arr.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (arr[mid] == target) return mid;
            else if (arr[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9};
        System.out.println(binarySearch(arr, 5)); // 2
        System.out.println(binarySearch(arr, 8)); // -1
    }
}
```

---

## **10. Detect Cycle in a Linked List (Floyd’s Algorithm)**

```java
class Node {
    int data; Node next;
    Node(int data) { this.data = data; }
}

public class CycleDetection {
    public static boolean hasCycle(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = head; // cycle
        System.out.println(hasCycle(head)); // true
    }
}
```

