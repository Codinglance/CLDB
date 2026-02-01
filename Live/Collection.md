{
"category": "Java",
"format": "Markdown inside JSON",
"questions": [
{
"id": 1,
"section": "Java Collections Framework",
"question": "What is the Java Collections Framework?",
"difficulty": "Easy",
"tags": ["collections", "basics"],
"askedIn": ["Google", "Amazon", "Microsoft"],
"expectedReadTime": "1 min",
"markdown": "### Java Collections Framework (JCF)\n\nJava Collections Framework provides a **set of interfaces, classes, and algorithms** to store and manipulate groups of objects.\n\n**Key Points:**\n- Provides standard data structures: **List, Set, Queue, Map**\n- Reduces boilerplate code\n- Supports algorithms like sorting and searching\n- Part of `java.util` package\n\n**Hierarchy:**\n```\nCollection (Interface)\n├─ List\n├─ Set\n├─ Queue\nMap (Interface)\n```"
},
{
"id": 2,
"section": "Java Collections Framework",
"question": "Difference between List, Set, and Map",
"difficulty": "Easy",
"tags": ["collections", "list", "set", "map"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### List vs Set vs Map\n\n| Interface | Description | Example Classes | Key Points |\n|---------|-------------|----------------|-----------|\n| List | Ordered, allows duplicates | ArrayList, LinkedList | Indexed access |\n| Set | Unordered, no duplicates | HashSet, TreeSet | Unique elements |\n| Map | Key-value pairs | HashMap, TreeMap | Keys are unique |"
},
{
"id": 3,
"section": "List Implementations",
"question": "Difference between ArrayList and LinkedList",
"difficulty": "Easy",
"tags": ["arraylist", "linkedlist"],
"askedIn": ["Amazon", "Flipkart"],
"expectedReadTime": "1 min",
"markdown": "### ArrayList vs LinkedList\n\n| Feature | ArrayList | LinkedList |\n|------|-----------|------------|\n| Data structure | Dynamic array | Doubly linked list |\n| Access time | O(1) | O(n) |\n| Insert/Delete | Slow | Fast |\n| Memory | Low | High |\n\n```java\nList<String> list = new ArrayList<>();\nlist.add(\"A\");\nlist.add(\"B\");\n```"
},
{
"id": 4,
"section": "Set Implementations",
"question": "Difference between HashSet, LinkedHashSet, and TreeSet",
"difficulty": "Easy",
"tags": ["hashset", "treeset", "linkedhashset"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### HashSet vs LinkedHashSet vs TreeSet\n\n| Feature | HashSet | LinkedHashSet | TreeSet |\n|------|--------|---------------|---------|\n| Order | No | Insertion order | Sorted |\n| Duplicates | Not allowed | Not allowed | Not allowed |\n| Performance | Fast | Medium | Slow (O(log n)) |"
},
{
"id": 5,
"section": "Map Implementations",
"question": "Difference between HashMap, LinkedHashMap, and TreeMap",
"difficulty": "Easy",
"tags": ["hashmap", "treemap", "linkedhashmap"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### HashMap vs LinkedHashMap vs TreeMap\n\n| Feature | HashMap | LinkedHashMap | TreeMap |\n|------|--------|---------------|---------|\n| Order | No | Insertion order | Sorted by key |\n| Null keys | 1 allowed | 1 allowed | Not allowed |\n| Performance | O(1) | Slightly slower | O(log n) |"
},
{
"id": 6,
"section": "Iterators",
"question": "Difference between fail-fast and fail-safe iterators",
"difficulty": "Medium",
"tags": ["iterator", "concurrency"],
"askedIn": ["Amazon", "Microsoft"],
"expectedReadTime": "1 min",
"markdown": "### Fail-Fast vs Fail-Safe Iterators\n\n| Type | Description | Examples |\n|----|-------------|----------|\n| Fail-fast | Throws exception on modification | ArrayList, HashMap |\n| Fail-safe | Works on copy, no exception | ConcurrentHashMap |\n\n```java\nfor(String s : list) {\n  list.add(\"new\"); // ConcurrentModificationException\n}\n```"
},
{
"id": 7,
"section": "Sorting",
"question": "Difference between Comparable and Comparator",
"difficulty": "Medium",
"tags": ["comparable", "comparator"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Comparable vs Comparator\n\n| Interface | Purpose | Method |\n|---------|---------|--------|\n| Comparable | Natural ordering | compareTo() |\n| Comparator | Custom ordering | compare() |\n\n```java\nclass Student implements Comparable<Student> {\n  public int compareTo(Student s) {\n    return this.age - s.age;\n  }\n}\n```"
},
{
"id": 8,
"section": "Queue",
"question": "Difference between Queue, Deque, and PriorityQueue",
"difficulty": "Easy",
"tags": ["queue", "deque", "priorityqueue"],
"askedIn": ["Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Queue vs Deque vs PriorityQueue\n\n| Type | Description |\n|----|-------------|\n| Queue | FIFO order |\n| Deque | Insert/remove from both ends |\n| PriorityQueue | Sorted by priority |\n\n```java\nQueue<Integer> pq = new PriorityQueue<>();\npq.add(10);\npq.add(5);\npq.poll(); // 5\n```"
},
{
"id": 9,
"section": "Iteration",
"question": "Difference between Iterator, ListIterator, and Enumeration",
"difficulty": "Easy",
"tags": ["iterator", "enumeration"],
"askedIn": ["Amazon", "TCS"],
"expectedReadTime": "1 min",
"markdown": "### Iterator vs ListIterator vs Enumeration\n\n| Type | Features |\n|----|----------|\n| Iterator | Forward only, fail-fast |\n| ListIterator | Forward + backward |\n| Enumeration | Legacy, not fail-fast |\n\n```java\nIterator<String> it = list.iterator();\nwhile(it.hasNext()) {\n  System.out.println(it.next());\n}\n```"
},
{
"id": 10,
"section": "Concurrency",
"question": "Difference between synchronized and concurrent collections",
"difficulty": "Medium",
"tags": ["concurrency", "thread-safety"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Synchronized vs Concurrent Collections\n\n| Type | Description | Examples |\n|----|-------------|----------|\n| Synchronized | Thread-safe wrappers | Collections.synchronizedList() |\n| Concurrent | High-performance thread-safe | ConcurrentHashMap |\n\n**Key Point:**\n👉 Prefer **Concurrent collections** for multithreaded applications."
}
]
}
