{
  "category": "Java Collections",
  "format": "Markdown inside JSON",
  "questions": [
    {
      "id": 1,
      "section": "Basic Level",
      "question": "What is the Java Collection Framework?",
      "difficulty": "Easy",
      "tags": ["collections", "java", "basics"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Java Collection Framework\n\nThe **Java Collection Framework (JCF)** is a set of classes and interfaces that provide a unified architecture to store and manipulate groups of objects.\n\n**Key Interfaces:**\n- List\n- Set\n- Queue\n- Map\n\n**Benefits:**\n- Reduces programming effort\n- Increases performance\n- Provides standard data structures"
    },
    {
      "id": 2,
      "section": "Basic Level",
      "question": "Difference between Collection and Collections?",
      "difficulty": "Easy",
      "tags": ["collections", "java"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Collection**\n\n  * It is an **interface** in Java (`java.util.Collection`)\n  * Represents a **group of objects** (elements)\n  * Root interface of List, Set, and Queue\n  * Used to **store and manipulate data**\n  * Example: `List`, `Set`, `Queue`\n\n* **Collections**\n\n  * It is a **utility class** in Java (`java.util.Collections`)\n  * Provides **static helper methods** to work with collections\n  * Used for **sorting, searching, reversing, synchronizing**, etc.\n  * Does **not store data** itself\n  * Example methods: `sort()`, `reverse()`, `shuffle()`, `synchronizedList()`\n"
    },
    {
      "id": 3,
      "section": "Basic Level",
      "question": "Difference between List, Set, and Map?",
      "difficulty": "Easy",
      "tags": ["list", "set", "map"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **List**\n\n  * Allows **duplicate elements**\n  * Maintains **insertion order**\n  * Elements are accessed using an **index**\n  * Common implementations: `ArrayList`, `LinkedList`\n  * Example: `[A, B, A]`\n\n* **Set**\n\n  * Does **not allow duplicates**\n  * Does **not guarantee order** (except `LinkedHashSet`)\n  * No index-based access\n  * Common implementations: `HashSet`, `LinkedHashSet`, `TreeSet`\n  * Example: `[A, B]`\n\n* **Map**\n\n  * Stores data as **key–value pairs**\n  * **Keys must be unique**, values can be duplicate\n  * No direct relationship to Collection interface\n  * Accessed using **keys**\n  * Common implementations: `HashMap`, `LinkedHashMap`, `TreeMap`\n  * Example: `{1=A, 2=B}`\n"
    },
    {
      "id": 4,
      "section": "Basic Level",
      "question": "Difference between Array and ArrayList?",
      "difficulty": "Easy",
      "tags": ["array", "arraylist"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Array**\n\n  * Fixed size (cannot grow or shrink)\n  * Can store **primitive types and objects**\n  * Faster access due to direct memory allocation\n  * Length is accessed using `array.length`\n  * Part of core language (not in Collections framework)\n  * Example: `int[] arr = new int[5]`\n\n* **ArrayList**\n\n  * Dynamic size (grows and shrinks automatically)\n  * Stores **objects only** (primitives via wrapper classes)\n  * Slightly slower than arrays due to resizing overhead\n  * Size is accessed using `arrayList.size()`\n  * Part of **Collections framework**\n  * Example: `ArrayList<Integer> list = new ArrayList<>()`\n"
    },
    {
      "id": 5,
      "section": "Basic Level",
      "question": "Difference between ArrayList and LinkedList?",
      "difficulty": "Easy",
      "tags": ["arraylist", "linkedlist"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **ArrayList**\n\n  * Uses a **dynamic array** internally\n  * Faster **random access** (`get(index)`)\n  * Slower **insertion/deletion** in the middle (shifting needed)\n  * Better for **read-heavy** operations\n  * More memory-efficient than LinkedList\n  * Implements `List` interface\n\n* **LinkedList**\n\n  * Uses a **doubly linked list** internally\n  * Slower **random access** (must traverse nodes)\n  * Faster **insertion/deletion** (no shifting)\n  * Better for **insert/delete-heavy** operations\n  * Uses more memory (stores node pointers)\n  * Implements `List` and `Deque` interfaces\n"
    },
    {
      "id": 6,
      "section": "Basic Level",
      "question": "Difference between HashSet and TreeSet?",
      "difficulty": "Easy",
      "tags": ["hashset", "treeset"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **HashSet**\n\n    * Stores elements using a **hash table**\n    * Does **not maintain any order**\n    * Faster performance for add, remove, and search (O(1) average)\n    * Allows **one null** element\n    * Uses `hashCode()` and `equals()`\n    * Example: `[C, A, B]`\n\n* **TreeSet**\n\n    * Stores elements in a **sorted tree (Red-Black Tree)**\n    * Maintains **sorted order** (natural or comparator)\n    * Slower than HashSet (O(log n))\n    * Does **not allow null** elements\n    * Uses `compareTo()` or `Comparator`\n    * Example: `[A, B, C]`"
    },
    {
      "id": 7,
      "section": "Basic Level",
      "question": "Difference between HashMap and Hashtable?",
      "difficulty": "Easy",
      "tags": ["hashmap", "hashtable"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **HashMap**\n\n    * Stores data as **key–value pairs** using a **hash table**\n    * **Not synchronized** (not thread-safe)\n    * Faster performance due to **no locking**\n    * Allows **one null key** and **multiple null values**\n    * Uses **fail-fast iterator**\n    * Part of **Java Collections Framework**\n    * Preferred in **modern applications**\n\n* **Hashtable**\n\n    * Stores data as **key–value pairs** using a **hash table**\n    * **Synchronized** (thread-safe by default)\n    * Slower due to **synchronization overhead**\n    * Does **not allow null key or null value**\n    * Uses **Enumeration** (not fail-fast)\n    * **Legacy class** (introduced in Java 1.0)\n    * Mainly used for **legacy code**"
    },
    {
      "id": 8,
      "section": "Basic Level",
      "question": "Difference between HashMap and ConcurrentHashMap?",
      "difficulty": "Medium",
      "tags": ["hashmap", "concurrency"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **HashMap**\n\n    * Stores data as **key–value pairs** using a hash table\n    * **Not thread-safe**\n    * Faster in **single-threaded** environments\n    * Allows **one null key** and **multiple null values**\n    * Uses **fail-fast iterator**\n    * Not suitable for concurrent access without external synchronization\n    * Commonly used in **non-concurrent applications**\n\n* **ConcurrentHashMap**\n\n    * Stores data as **key–value pairs** using a hash table\n    * **Thread-safe** for concurrent access\n    * High performance using **fine-grained locking / lock-free techniques**\n    * Does **not allow null keys or null values**\n    * Uses **weakly consistent iterator** (no `ConcurrentModificationException`)\n    * Supports **concurrent read and write operations**\n    * Preferred for **multi-threaded and concurrent applications**"
    },
    {
      "id": 9,
      "section": "Basic Level",
      "question": "Difference between Iterator and ListIterator?",
      "difficulty": "Easy",
      "tags": ["iterator"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Iterator**\n\n    * Used to traverse elements in a **Collection**\n    * Supports **forward direction only**\n    * Works with **all collection types** (List, Set, etc.)\n    * Allows **remove()** operation\n    * Cannot **add or replace** elements\n    * Available via `iterator()`\n    * Suitable for **simple iteration**\n\n* **ListIterator**\n\n    * Used to traverse elements in a **List**\n    * Supports **both forward and backward traversal**\n    * Works **only with List implementations**\n    * Allows **add(), remove(), and set()** operations\n    * Provides index-based methods like `nextIndex()` and `previousIndex()`\n    * Available via `listIterator()`\n    * Useful when **modifying a list during iteration**"
    },
    {
      "id": 10,
      "section": "Basic Level",
      "question": "What is Generics in Collections?",
      "difficulty": "Easy",
      "tags": ["generics"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Generics**\n\n    * Allow defining **type-safe collections**\n    * Specify the **type of objects** a collection can store\n    * Introduced in **Java 5**\n    * Eliminates the need for **explicit type casting**\n    * Errors are caught at **compile time**, not runtime\n    * Improve **code readability and safety**\n\n* **Generics in Collections**\n\n    * Used with collections like `List<T>`, `Set<T>`, `Map<K, V>`\n    * Prevent storing **wrong object types**\n    * Enable **reusable and flexible code**\n    * Work with **wrapper classes** (not primitives)\n    * Example:\n\n      ```java\n      List<String> names = new ArrayList<>();\n      ```\n\n    * Only `String` objects are allowed*"
    },
    {
      "id": 11,
      "section": "Intermediate Level",
      "question": "Difference between fail-fast and fail-safe iterators?",
      "difficulty": "Medium",
      "tags": ["iterator", "concurrency"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Fail-fast Iterator**\n\n    * Throws **ConcurrentModificationException**\n    * Detects **structural modification** during iteration\n    * Works on the **original collection**\n    * Stops iteration immediately on modification\n    * Used in collections like **ArrayList, HashMap**\n    * Ensures **data consistency**\n    * Faster and lightweight\n\n* **Fail-safe Iterator**\n\n    * Does **not throw** ConcurrentModificationException\n    * Allows **modification during iteration**\n    * Works on a **copy of the collection**\n    * Iteration continues safely\n    * Used in **Concurrent collections** like `ConcurrentHashMap`\n    * May not reflect **latest changes**\n    * Slightly more memory overhead"
    },
    {
      "id": 12,
      "section": "Intermediate Level",
      "question": "What is ConcurrentModificationException? When does it occur?",
      "difficulty": "Medium",
      "tags": ["exception", "collections"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "**ConcurrentModificationException (Little Longer):**\n\n* A **runtime exception** in Java thrown by **fail-fast iterators**\n* Occurs when a collection is **structurally modified during iteration**\n* Common when using **for-each loops** and calling `add()` or `remove()`\n* Seen with non-thread-safe collections like **ArrayList** and **HashMap**\n* Can happen in **multi-threaded environments** without proper synchronization\n* Prevented by using **Iterator.remove()**, synchronization, or **concurrent collections** like `ConcurrentHashMap`\n"
    },
    {
      "id": 13,
      "section": "Intermediate Level",
      "question": "How does HashMap work internally?",
      "difficulty": "Medium",
      "tags": ["hashmap"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1.5 min",
      "markdown": "* `HashMap` stores data in an **array of buckets**.\n* Each bucket holds **Node objects** containing `key`, `value`, `hash`, and `next`.\n* When `put(key, value)` is called:\n\n    * `hashCode()` of the key is generated.\n    * Bucket index is calculated using `(capacity - 1) & hash`.\n* If the bucket is empty, the entry is stored directly.\n* If a **collision** occurs:\n\n    * Keys are compared using `equals()`.\n    * New entries are stored in a **LinkedList**.\n    * If entries exceed **8**, it converts to a **Red-Black Tree** (Java 8+).\n* `get(key)` uses the same hash and index to find the value.\n* Uses a **load factor (0.75)** to decide resizing.\n* When threshold is crossed, capacity **doubles** and entries are rehashed.\n* Allows **one null key** and **multiple null values**.\n* Average time complexity for `get()` and `put()` is **O(1)**."
    },
    {
      "id": 14,
      "section": "Intermediate Level",
      "question": "Difference between HashMap and LinkedHashMap?",
      "difficulty": "Medium",
      "tags": ["hashmap", "linkedhashmap"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **HashMap**\n\n    * Stores key–value pairs using a **hash table**\n    * Does **not maintain any order**\n    * Faster than LinkedHashMap\n    * Allows **one null key** and **multiple null values**\n    * Uses **hashing only**\n    * Iteration order is **unpredictable**\n    * Uses **less memory**\n\n* **LinkedHashMap**\n\n    * Stores key–value pairs using **hash table + doubly linked list**\n    * Maintains **insertion order** (or access order if enabled)\n    * Slightly slower due to extra linked list\n    * Allows **one null key** and **multiple null values**\n    * Iteration order is **predictable**\n    * Uses **more memory**\n    * Useful for **LRU cache implementations**"
    },
    {
      "id": 15,
      "section": "Intermediate Level",
      "question": "Difference between TreeMap and HashMap?",
      "difficulty": "Medium",
      "tags": ["treemap", "hashmap"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **HashMap**\n\n    * Stores key–value pairs using a **hash table**\n    * Does **not maintain any order**\n    * Faster for `get()` and `put()` (O(1) average)\n    * Allows **one null key** and **multiple null values**\n    * Uses `hashCode()` and `equals()`\n    * Suitable for **high-performance lookups**\n    * Not sorted\n\n* **TreeMap**\n\n    * Stores key–value pairs using a **Red-Black Tree**\n    * Maintains **sorted order** (natural or Comparator)\n    * Slower than HashMap (O(log n))\n    * Does **not allow null keys** (allows null values)\n    * Uses `compareTo()` or `Comparator`\n    * Useful when **sorted data** is required\n    * Implements `NavigableMap`"
    },
    {
      "id": 16,
      "section": "Intermediate Level",
      "question": "Time complexity of common operations in collections?",
      "difficulty": "Medium",
      "tags": ["complexity"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Array / ArrayList**\n\n    * Access → **O(1)**\n    * Add (end) → **O(1)** amortized\n    * Insert / Remove → **O(n)**\n\n* **LinkedList**\n\n    * Access → **O(n)**\n    * Add / Remove (ends) → **O(1)**\n    * Search → **O(n)**\n\n* **HashMap / HashSet**\n\n    * Put / Get / Remove → **O(1)** average\n    * Worst case → **O(n)** (or **O(log n)** in Java 8+)\n\n* **TreeMap / TreeSet**\n\n    * Put / Get / Remove → **O(log n)**\n\n* **Queue / Deque**\n\n    * Add / Remove / Peek → **O(1)**"
    },
    {
      "id": 17,
      "section": "Intermediate Level",
      "question": "How does equals() and hashCode() affect HashMap?",
      "difficulty": "Medium",
      "tags": ["hashcode", "equals"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* `hashCode()` is used to **decide the bucket index** where the key is stored.\n* `equals()` is used to **identify the exact key** within that bucket.\n* When inserting (`put`):\n\n    * HashMap first checks **hashCode()**\n    * If hash matches, it then checks **equals()**\n    * If `equals()` returns `true`, the **value is replaced**\n* When retrieving (`get`):\n\n    * Same `hashCode()` finds the bucket\n    * `equals()` finds the matching key\n* If `hashCode()` is not overridden properly:\n\n    * Keys may go to wrong buckets → **poor performance**\n* If `equals()` is not overridden:\n\n    * Duplicate keys may be stored → **data inconsistency**\n* **Contract rule**:\n\n    * If `equals()` is `true`, `hashCode()` **must be same**\n\n**In short:**\n\n> `hashCode()` decides *where* the key goes, `equals()` decides *which* key it is."
    },
    {
      "id": 18,
      "section": "Intermediate Level",
      "question": "Difference between Comparable and Comparator?",
      "difficulty": "Medium",
      "tags": ["comparable", "comparator"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* **Comparable**\n\n    * Used to define **natural sorting order**\n    * Implemented by the **class itself**\n    * Has only **one sorting logic**\n    * Method: `compareTo(Object o)`\n    * Modifies the **original class**\n    * Located in `java.lang`\n    * Used by default in sorting methods\n\n* **Comparator**\n\n    * Used to define **custom sorting order**\n    * Implemented as a **separate class or lambda**\n    * Allows **multiple sorting logics**\n    * Method: `compare(Object o1, Object o2)`\n    * Does **not modify** the original class\n    * Located in `java.util`\n    * Used when custom sorting is required\n\n**One-line interview tip:**\n\n> Comparable is for natural ordering, Comparator is for custom ordering."
    },
    {
      "id": 19,
      "section": "Intermediate Level",
      "question": "How do you make a collection thread-safe?",
      "difficulty": "Medium",
      "tags": ["threadsafe"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "* Use **synchronized collections**:\n\n    * `Collections.synchronizedList()`\n    * `Collections.synchronizedSet()`\n    * `Collections.synchronizedMap()`\n* Use **concurrent collections**:\n\n    * `ConcurrentHashMap`\n    * `CopyOnWriteArrayList`\n    * `CopyOnWriteArraySet`\n* Use **legacy thread-safe classes**:\n\n    * `Vector`, `Hashtable` (not recommended now)\n* Apply **manual synchronization**:\n\n    * Use `synchronized` blocks while accessing collections\n* Prefer **concurrent collections** for better performance in multi-threaded apps\n\n**Note:**\n\n> Use concurrent collections instead of synchronizing normal collections for better scalability.\n"
    },
    {
      "id": 20,
      "section": "Intermediate Level",
      "question": "Difference between Collections.synchronizedList() and CopyOnWriteArrayList?",
      "difficulty": "Hard",
      "tags": ["concurrency"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1.5 min",
      "markdown": "* **Collections.synchronizedList()**\n\n    * Makes a list **thread-safe using synchronization**\n    * Uses a **single lock** for all operations\n    * Read and write operations **block each other**\n    * Iterator is **fail-fast** (needs manual synchronization)\n    * Better when **writes are frequent**\n    * Lower memory overhead\n\n* **CopyOnWriteArrayList**\n\n    * Thread-safe using **copy-on-write mechanism**\n    * No locking for **read operations**\n    * Write operations create a **new copy of the array**\n    * Iterator is **fail-safe**\n    * Best when **reads are frequent and writes are rare**\n    * Higher memory overhead\n\n**Note:**\n\n> `synchronizedList` locks everything, `CopyOnWriteArrayList` optimizes for concurrent reads.\n"
    }
  ]
}
