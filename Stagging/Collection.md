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
"markdown": "### Collection vs Collections\n\n| Collection | Collections |\n|----------|-----------|\n| Interface | Utility class |\n| Represents a group of objects | Provides static utility methods |\n| Example: List, Set | Example: sort(), reverse(), synchronizedList() |\n\n```java\nCollection<String> list = new ArrayList<>();\nCollections.sort(list);\n```"
},
{
"id": 3,
"section": "Basic Level",
"question": "Difference between List, Set, and Map?",
"difficulty": "Easy",
"tags": ["list", "set", "map"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### List vs Set vs Map\n\n| Feature | List | Set | Map |\n|--------|------|-----|-----|\n| Duplicates | Allowed | Not Allowed | Keys not allowed |\n| Order | Maintained | Not guaranteed | Depends on implementation |\n| Index-based | Yes | No | No |\n\nExamples: ArrayList, HashSet, HashMap"
},
{
"id": 4,
"section": "Basic Level",
"question": "Difference between Array and ArrayList?",
"difficulty": "Easy",
"tags": ["array", "arraylist"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Array vs ArrayList\n\n| Array | ArrayList |\n|------|---------|\n| Fixed size | Dynamic size |\n| Primitive + Objects | Objects only |\n| Faster | Slightly slower |\n\n```java\nint[] arr = new int[5];\nArrayList<Integer> list = new ArrayList<>();\n```"
},
{
"id": 5,
"section": "Basic Level",
"question": "Difference between ArrayList and LinkedList?",
"difficulty": "Easy",
"tags": ["arraylist", "linkedlist"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### ArrayList vs LinkedList\n\n| Feature | ArrayList | LinkedList |\n|--------|----------|-----------|\n| Data Structure | Dynamic Array | Doubly Linked List |\n| Access | Fast (O(1)) | Slow (O(n)) |\n| Insert/Delete | Slow | Fast |\n\nUse ArrayList for search, LinkedList for insert/delete."
},
{
"id": 6,
"section": "Basic Level",
"question": "Difference between HashSet and TreeSet?",
"difficulty": "Easy",
"tags": ["hashset", "treeset"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### HashSet vs TreeSet\n\n| HashSet | TreeSet |\n|--------|--------|\n| No ordering | Sorted order |\n| Faster | Slower |\n| Uses HashMap | Uses Red-Black Tree |\n\nTime Complexity: O(1) vs O(log n)"
},
{
"id": 7,
"section": "Basic Level",
"question": "Difference between HashMap and Hashtable?",
"difficulty": "Easy",
"tags": ["hashmap", "hashtable"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### HashMap vs Hashtable\n\n| HashMap | Hashtable |\n|--------|---------|\n| Not synchronized | Synchronized |\n| Allows null key/value | No null allowed |\n| Faster | Slower |\n\nHashtable is legacy, HashMap is preferred."
},
{
"id": 8,
"section": "Basic Level",
"question": "Difference between HashMap and ConcurrentHashMap?",
"difficulty": "Medium",
"tags": ["hashmap", "concurrency"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### HashMap vs ConcurrentHashMap\n\n| HashMap | ConcurrentHashMap |\n|--------|------------------|\n| Not thread-safe | Thread-safe |\n| Can cause race conditions | Uses segment-level locking |\n| Faster | Slightly slower but safe |\n\nUsed in multithreaded environments."
},
{
"id": 9,
"section": "Basic Level",
"question": "Difference between Iterator and ListIterator?",
"difficulty": "Easy",
"tags": ["iterator"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Iterator vs ListIterator\n\n| Iterator | ListIterator |\n|---------|-------------|\n| Forward only | Forward & backward |\n| Works on all collections | Works only on List |\n| Can remove elements | Can add, update, remove |\n"
},
{
"id": 10,
"section": "Basic Level",
"question": "What is Generics in Collections?",
"difficulty": "Easy",
"tags": ["generics"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Generics in Collections\n\nGenerics provide **type safety** and eliminate runtime ClassCastException.\n\n```java\nList<String> list = new ArrayList<>();\n```\n- Ensures only String objects are stored."
},
{
"id": 11,
"section": "Intermediate Level",
"question": "Difference between fail-fast and fail-safe iterators?",
"difficulty": "Medium",
"tags": ["iterator", "concurrency"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Fail-fast vs Fail-safe\n\n| Fail-fast | Fail-safe |\n|----------|----------|\n| Throws ConcurrentModificationException | No exception |\n| Works on original collection | Works on copy |\n| Example: ArrayList | Example: CopyOnWriteArrayList |\n"
},
{
"id": 12,
"section": "Intermediate Level",
"question": "What is ConcurrentModificationException? When does it occur?",
"difficulty": "Medium",
"tags": ["exception", "collections"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### ConcurrentModificationException\n\nOccurs when a collection is modified while iterating using Iterator.\n\n```java\nfor(String s : list) {\n  list.add(\"x\"); // throws exception\n}\n```"
},
{
"id": 13,
"section": "Intermediate Level",
"question": "How does HashMap work internally?",
"difficulty": "Medium",
"tags": ["hashmap"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### HashMap Internal Working\n\n- Uses array of buckets\n- Hash function → index\n- Collision handling → LinkedList / Tree (Red-Black Tree after Java 8)\n\nSteps:\n1. Compute hashCode\n2. Find bucket index\n3. Store entry"
},
{
"id": 14,
"section": "Intermediate Level",
"question": "Difference between HashMap and LinkedHashMap?",
"difficulty": "Medium",
"tags": ["hashmap", "linkedhashmap"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### HashMap vs LinkedHashMap\n\n| HashMap | LinkedHashMap |\n|--------|-------------|\n| No order | Maintains insertion order |\n| Faster | Slightly slower |\n"
},
{
"id": 15,
"section": "Intermediate Level",
"question": "Difference between TreeMap and HashMap?",
"difficulty": "Medium",
"tags": ["treemap", "hashmap"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### TreeMap vs HashMap\n\n| TreeMap | HashMap |\n|--------|--------|\n| Sorted order | No order |\n| O(log n) | O(1) average |\n| Uses Red-Black Tree | Uses Hashing |\n"
},
{
"id": 16,
"section": "Intermediate Level",
"question": "Time complexity of common operations in collections?",
"difficulty": "Medium",
"tags": ["complexity"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Time Complexity\n\n- ArrayList get() → O(1)\n- LinkedList get() → O(n)\n- HashMap put() → O(1) average\n- HashSet search() → O(1) average"
},
{
"id": 17,
"section": "Intermediate Level",
"question": "How does equals() and hashCode() affect HashMap?",
"difficulty": "Medium",
"tags": ["hashcode", "equals"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### equals() & hashCode() in HashMap\n\n- hashCode → bucket selection\n- equals → key comparison\n\nIf overridden incorrectly → HashMap fails to retrieve values."
},
{
"id": 18,
"section": "Intermediate Level",
"question": "Difference between Comparable and Comparator?",
"difficulty": "Medium",
"tags": ["comparable", "comparator"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Comparable vs Comparator\n\n| Comparable | Comparator |\n|----------|----------|\n| compareTo() method | compare() method |\n| Natural ordering | Custom ordering |\n| Implemented by class | Separate class |\n"
},
{
"id": 19,
"section": "Intermediate Level",
"question": "How do you make a collection thread-safe?",
"difficulty": "Medium",
"tags": ["threadsafe"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Making Collections Thread-safe\n\nMethods:\n- Collections.synchronizedList()\n- Concurrent Collections (ConcurrentHashMap)\n- CopyOnWriteArrayList\n"
},
{
"id": 20,
"section": "Intermediate Level",
"question": "Difference between Collections.synchronizedList() and CopyOnWriteArrayList?",
"difficulty": "Hard",
"tags": ["concurrency"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### synchronizedList vs CopyOnWriteArrayList\n\n| synchronizedList | CopyOnWriteArrayList |\n|-----------------|---------------------|\n| Locks entire list | Creates copy on write |\n| Better for frequent writes | Better for frequent reads |\n| Blocking | Non-blocking reads |\n"
},
    {
      "id": 1,
      "section": "Java & Android Collections",
      "question": "Why is SparseArray preferred over HashMap in Android?",
      "difficulty": "Medium",
      "tags": ["android", "sparsearray", "hashmap"],
      "expectedReadTime": "1 min",
      "markdown": "### SparseArray vs HashMap\n\nSparseArray is preferred when keys are integers.\n\n**Reasons:**\n- Avoids auto-boxing of Integer objects\n- More memory efficient\n- Faster than HashMap<Integer, Object>\n\n👉 Best for Android memory optimization."
    },
    {
      "id": 2,
      "section": "Java & Android Collections",
      "question": "Difference between WeakHashMap and HashMap? Use case in Android.",
      "difficulty": "Medium",
      "tags": ["weakhashmap", "hashmap"],
      "expectedReadTime": "1 min",
      "markdown": "### WeakHashMap vs HashMap\n\n| HashMap | WeakHashMap |\n|--------|-----------|\n| Strong references | Weak references |\n| Entries not GC collected | Entries GC collected |\n| Risk of memory leaks | Prevents memory leaks |\n\n**Android Use Case:**\n- Caching objects without memory leaks (e.g., Context-related caches)."
    },
    {
      "id": 3,
      "section": "Java & Android Collections",
      "question": "Explain LRU Cache implementation using Collections.",
      "difficulty": "Hard",
      "tags": ["lru", "cache"],
      "expectedReadTime": "1.5 min",
      "markdown": "### LRU Cache Implementation\n\nLRU (Least Recently Used) cache removes the least recently accessed item.\n\n```java\nclass LRUCache<K,V> extends LinkedHashMap<K,V> {\n  private final int capacity;\n  LRUCache(int capacity) {\n    super(capacity, 0.75f, true);\n    this.capacity = capacity;\n  }\n  protected boolean removeEldestEntry(Map.Entry<K,V> eldest) {\n    return size() > capacity;\n  }\n}\n```\n\n👉 Used in Android image caching (Glide, Picasso)."
    },
    {
      "id": 4,
      "section": "Java & Android Collections",
      "question": "Why is ArrayList not thread-safe?",
      "difficulty": "Easy",
      "tags": ["arraylist", "threading"],
      "expectedReadTime": "1 min",
      "markdown": "### ArrayList Thread Safety\n\nArrayList is not thread-safe because:\n- No synchronization\n- Multiple threads can modify it simultaneously\n- Leads to race conditions\n\n👉 Use Collections.synchronizedList() or CopyOnWriteArrayList."
    },
    {
      "id": 5,
      "section": "Java & Android Collections",
      "question": "How does CopyOnWriteArrayList work internally?",
      "difficulty": "Hard",
      "tags": ["copyonwritearraylist"],
      "expectedReadTime": "1.5 min",
      "markdown": "### CopyOnWriteArrayList Internals\n\n- Creates a new copy of the array on every write operation.\n- Read operations are lock-free.\n\n**Pros:**\n- Thread-safe\n- Best for read-heavy scenarios\n\n**Cons:**\n- High memory usage for frequent writes."
    },
    {
      "id": 6,
      "section": "Java & Android Collections",
      "question": "Difference between Queue, Deque, and Stack?",
      "difficulty": "Easy",
      "tags": ["queue", "deque", "stack"],
      "expectedReadTime": "1 min",
      "markdown": "### Queue vs Deque vs Stack\n\n| Structure | Principle |\n|---------|---------|\n| Queue | FIFO |\n| Stack | LIFO |\n| Deque | Double-ended queue |\n\nExamples:\n- Queue: LinkedList, PriorityQueue\n- Stack: Stack, ArrayDeque"
    },
    {
      "id": 7,
      "section": "Java & Android Collections",
      "question": "What happens if you modify a collection while iterating?",
      "difficulty": "Medium",
      "tags": ["iterator"],
      "expectedReadTime": "1 min",
      "markdown": "### Modifying Collection During Iteration\n\n- Causes ConcurrentModificationException (fail-fast).\n\n**Solution:**\n- Use Iterator.remove()\n- Use concurrent collections like CopyOnWriteArrayList."
    },
    {
      "id": 8,
      "section": "Java & Android Collections",
      "question": "How to prevent memory leaks caused by collections in Android?",
      "difficulty": "Hard",
      "tags": ["memory-leak"],
      "expectedReadTime": "1.5 min",
      "markdown": "### Preventing Memory Leaks\n\n- Avoid static collections holding Context\n- Use WeakReference / WeakHashMap\n- Clear collections in onDestroy()\n- Avoid long-lived caches with Activity references\n\n👉 Common leak: static List<Activity>."
    },
    {
      "id": 9,
      "section": "Java & Android Collections",
      "question": "How does ConcurrentHashMap achieve thread safety without locking the whole map?",
      "difficulty": "Hard",
      "tags": ["concurrenthashmap"],
      "expectedReadTime": "1.5 min",
      "markdown": "### ConcurrentHashMap Internals\n\n- Uses bucket-level locking (Java 7)\n- Uses CAS (Compare-And-Swap) + synchronized blocks (Java 8)\n- Allows concurrent reads and writes\n\n👉 Better performance than Hashtable."
    },
    {
      "id": 10,
      "section": "Java & Android Collections",
      "question": "Can HashMap store null keys and values?",
      "difficulty": "Easy",
      "tags": ["hashmap"],
      "expectedReadTime": "1 min",
      "markdown": "### HashMap Null Handling\n\n- Allows 1 null key\n- Allows multiple null values\n\nHashtable does NOT allow null keys or values."
    },
    {
      "id": 11,
      "section": "Kotlin Collections - Basics",
      "question": "Difference between List, MutableList, and ArrayList in Kotlin?",
      "difficulty": "Easy",
      "tags": ["kotlin", "collections"],
      "expectedReadTime": "1 min",
      "markdown": "### List vs MutableList vs ArrayList\n\n| Type | Mutable? |\n|------|--------|\n| List | ❌ No |\n| MutableList | ✅ Yes |\n| ArrayList | ✅ Yes (Java-based) |\n\n```kotlin\nval list: List<Int> = listOf(1,2)\nval mutable = mutableListOf(1,2)\n```"
    },
    {
      "id": 12,
      "section": "Kotlin Collections - Basics",
      "question": "Difference between List and Set in Kotlin?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "expectedReadTime": "1 min",
      "markdown": "### List vs Set\n\n| List | Set |\n|------|-----|\n| Allows duplicates | No duplicates |\n| Ordered | Unordered (usually) |\n"
    },
    {
      "id": 13,
      "section": "Kotlin Collections - Basics",
      "question": "Difference between Map and MutableMap?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "expectedReadTime": "1 min",
      "markdown": "### Map vs MutableMap\n\n| Map | MutableMap |\n|-----|-----------|\n| Read-only | Read + Write |\n\n```kotlin\nval map = mapOf(\"a\" to 1)\nval mutable = mutableMapOf(\"a\" to 1)\n```"
    },
    {
      "id": 14,
      "section": "Kotlin Collections - Basics",
      "question": "Difference between val and var in collections?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "expectedReadTime": "1 min",
      "markdown": "### val vs var in Collections\n\n- val → reference cannot change\n- var → reference can change\n\n⚠️ val does NOT mean collection is immutable.\n\n```kotlin\nval list = mutableListOf(1)\nlist.add(2) // allowed\n```"
    },
    {
      "id": 15,
      "section": "Kotlin Collections - Basics",
      "question": "Difference between immutable and mutable collections?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "expectedReadTime": "1 min",
      "markdown": "### Immutable vs Mutable Collections\n\n| Immutable | Mutable |\n|----------|--------|\n| Cannot modify | Can modify |\n| listOf() | mutableListOf() |\n| mapOf() | mutableMapOf() |\n"
    },
    {
      "id": 16,
      "section": "Kotlin Collections - Basics",
      "question": "How do you create List, MutableList, Set, and Map in Kotlin?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "expectedReadTime": "1 min",
      "markdown": "### Creating Collections in Kotlin\n\n```kotlin\nval list = listOf(1,2,3)\nval mutableList = mutableListOf(1,2)\nval set = setOf(1,2)\nval map = mapOf(\"a\" to 1)\n```"
    },
    {
      "id": 17,
      "section": "Kotlin Collections - Basics",
      "question": "Difference between arrayOf() and listOf()?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "expectedReadTime": "1 min",
      "markdown": "### arrayOf vs listOf\n\n| arrayOf() | listOf() |\n|----------|--------|\n| Creates Array | Creates List |\n| Mutable | Immutable |\n| Primitive support | Object-based |\n\n```kotlin\nval arr = arrayOf(1,2)\nval list = listOf(1,2)\n```"
    },
    {
      "id": 1,
      "section": "Kotlin Collection Functions",
      "question": "Difference between map(), flatMap(), and filter()?",
      "difficulty": "Easy",
      "tags": ["kotlin", "collections"],
      "markdown": "### map vs flatMap vs filter\n\n| Function | Purpose |\n|---------|--------|\n| map() | Transforms each element |\n| flatMap() | Transforms + flattens nested collections |\n| filter() | Filters elements by condition |\n\n```kotlin\nval list = listOf(1,2,3)\nlist.map { it * 2 } // [2,4,6]\nlist.filter { it > 1 } // [2,3]\nlistOf(listOf(1,2)).flatMap { it } // [1,2]\n```"
    },
    {
      "id": 2,
      "section": "Kotlin Collection Functions",
      "question": "Difference between forEach and map?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "markdown": "### forEach vs map\n\n| forEach | map |\n|--------|-----|\n| Performs action | Returns transformed list |\n| Returns Unit | Returns new collection |\n\n👉 Use map when you need a result, forEach for side-effects."
    },
    {
      "id": 3,
      "section": "Kotlin Collections",
      "question": "Difference between Sequence and List in Kotlin?",
      "difficulty": "Medium",
      "tags": ["kotlin", "performance"],
      "markdown": "### Sequence vs List\n\n| List | Sequence |\n|------|--------|\n| Eager evaluation | Lazy evaluation |\n| Creates intermediate collections | No intermediate collections |\n| Faster for small data | Better for large data |\n\n👉 Sequence improves performance for chained operations."
    },
    {
      "id": 4,
      "section": "Kotlin Collections",
      "question": "Explain lazy evaluation in Kotlin collections.",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### Lazy Evaluation\n\nLazy evaluation means operations are executed only when needed.\n\n```kotlin\nval seq = listOf(1,2,3).asSequence()\n  .map { it * 2 }\n  .filter { it > 2 }\n```\n\n👉 Improves performance by avoiding unnecessary computations."
    },
    {
      "id": 5,
      "section": "Kotlin Collections",
      "question": "Difference between associateBy() and groupBy()?",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### associateBy vs groupBy\n\n| associateBy | groupBy |\n|------------|--------|\n| One value per key | Multiple values per key |\n\n```kotlin\nlist.associateBy { it.id }\nlist.groupBy { it.type }\n```"
    },
    {
      "id": 6,
      "section": "Kotlin Collections",
      "question": "What is fold() vs reduce()?",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### fold vs reduce\n\n| fold | reduce |\n|------|-------|\n| Has initial value | No initial value |\n| Safe for empty lists | Throws exception on empty list |\n\n```kotlin\nlist.fold(0) { acc, i -> acc + i }\nlist.reduce { acc, i -> acc + i }\n```"
    },
    {
      "id": 7,
      "section": "Kotlin Collections",
      "question": "Difference between sortedBy and sortBy?",
      "difficulty": "Easy",
      "tags": ["kotlin"],
      "markdown": "### sortedBy vs sortBy\n\n| sortedBy | sortBy |\n|---------|-------|\n| Returns new sorted list | Sorts mutable list in-place |\n\n👉 sortedBy is immutable, sortBy is mutable."
    },
    {
      "id": 8,
      "section": "Kotlin Collections",
      "question": "How does Kotlin handle null safety in collections?",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### Null Safety in Collections\n\nKotlin distinguishes nullable and non-nullable collections.\n\n```kotlin\nval list: List<String?> = listOf(\"a\", null)\nval safeList: List<String> = list.filterNotNull()\n```"
    },
    {
      "id": 9,
      "section": "Kotlin Collections",
      "question": "Difference between first(), firstOrNull(), single(), singleOrNull()?",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### first vs single\n\n| Function | Behavior |\n|---------|--------|\n| first() | Returns first element or throws exception |\n| firstOrNull() | Returns null if empty |\n| single() | Requires exactly one element |\n| singleOrNull() | Returns null if not exactly one |\n"
    },
    {
      "id": 10,
      "section": "Advanced Android Level",
      "question": "Why are Kotlin immutable collections preferred in Android?",
      "difficulty": "Hard",
      "tags": ["android", "kotlin"],
      "markdown": "### Immutable Collections in Android\n\n**Benefits:**\n- Thread safety\n- Predictable state\n- Avoids accidental mutations\n- Works well with MVVM & Compose\n\n👉 Reduces bugs in multi-threaded apps."
    },
    {
      "id": 11,
      "section": "Advanced Android Level",
      "question": "Difference between Java Collections and Kotlin Collections?",
      "difficulty": "Medium",
      "tags": ["java", "kotlin"],
      "markdown": "### Java vs Kotlin Collections\n\n| Java | Kotlin |\n|------|-------|\n| Mutable by default | Immutable by default |\n| Verbose API | Functional API |\n| Null unsafe | Null safe |\n"
    },
    {
      "id": 12,
      "section": "Advanced Android Level",
      "question": "How does Kotlin convert Java collections internally?",
      "difficulty": "Hard",
      "tags": ["kotlin"],
      "markdown": "### Kotlin-Java Collection Interop\n\n- Kotlin wraps Java collections with read-only interfaces.\n- No real immutability, only restricted access.\n\n👉 Kotlin List can still be modified if underlying Java list is mutable."
    },
    {
      "id": 13,
      "section": "Advanced Android Level",
      "question": "Performance difference between List and Sequence?",
      "difficulty": "Hard",
      "tags": ["performance"],
      "markdown": "### Performance: List vs Sequence\n\n- List → eager evaluation → faster for small datasets\n- Sequence → lazy evaluation → faster for large datasets\n\n👉 Sequence avoids intermediate object creation."
    },
    {
      "id": 14,
      "section": "Advanced Android Level",
      "question": "How do you avoid unnecessary object creation using Kotlin collections?",
      "difficulty": "Hard",
      "tags": ["performance"],
      "markdown": "### Avoid Object Creation\n\n- Use Sequence instead of List\n- Avoid chained map/filter on large lists\n- Use inline functions\n- Prefer mutable operations when needed\n\n👉 Improves memory & CPU performance."
    },
    {
      "id": 15,
      "section": "Advanced Android Level",
      "question": "Difference between MutableList and CopyOnWriteArrayList?",
      "difficulty": "Hard",
      "tags": ["threading"],
      "markdown": "### MutableList vs CopyOnWriteArrayList\n\n| MutableList | CopyOnWriteArrayList |\n|-----------|--------------------|\n| Not thread-safe | Thread-safe |\n| Fast writes | Slow writes |\n| Single-thread use | Multi-thread use |\n"
    },
    {
      "id": 16,
      "section": "Advanced Android Level",
      "question": "How to optimize RecyclerView data using Kotlin collections?",
      "difficulty": "Hard",
      "tags": ["android", "recyclerview"],
      "markdown": "### RecyclerView Optimization\n\n- Use DiffUtil instead of notifyDataSetChanged()\n- Use immutable lists with submitList()\n- Avoid heavy transformations in UI thread\n\n👉 Improves UI performance."
    },
    {
      "id": 17,
      "section": "Advanced Android Level",
      "question": "Difference between chunked(), windowed(), and zip()?",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### chunked vs windowed vs zip\n\n| Function | Purpose |\n|---------|--------|\n| chunked() | Splits list into fixed-size chunks |\n| windowed() | Creates sliding windows |\n| zip() | Combines two collections |\n"
    },
    {
      "id": 18,
      "section": "Advanced Android Level",
      "question": "How does Kotlin handle collection transformations internally?",
      "difficulty": "Hard",
      "tags": ["kotlin"],
      "markdown": "### Internal Transformations\n\n- Each transformation creates a new collection (List)\n- Sequence avoids intermediate collections\n\n👉 This affects performance in large data processing."
    },
    {
      "id": 19,
      "section": "Real Interview Trick Questions",
      "question": "Why is ArrayList faster than LinkedList for random access?",
      "difficulty": "Medium",
      "tags": ["java"],
      "markdown": "### ArrayList vs LinkedList\n\n- ArrayList uses index-based access (O(1))\n- LinkedList requires traversal (O(n))\n\n👉 ArrayList is better for random access."
    },
    {
      "id": 20,
      "section": "Real Interview Trick Questions",
      "question": "Why is HashMap faster than TreeMap?",
      "difficulty": "Medium",
      "tags": ["java"],
      "markdown": "### HashMap vs TreeMap\n\n- HashMap → O(1) average time\n- TreeMap → O(log n) (Red-Black Tree)\n\n👉 HashMap is faster but unordered."
    },
    {
      "id": 21,
      "section": "Real Interview Trick Questions",
      "question": "When should you use LinkedHashMap in Android?",
      "difficulty": "Medium",
      "tags": ["android"],
      "markdown": "### LinkedHashMap Use Case\n\n- Maintains insertion order\n- Useful for LRU Cache\n\n👉 Used in caching mechanisms."
    },
    {
      "id": 22,
      "section": "Real Interview Trick Questions",
      "question": "What happens if hashCode() always returns the same value?",
      "difficulty": "Hard",
      "tags": ["java"],
      "markdown": "### hashCode Collision\n\n- HashMap becomes LinkedList internally\n- Performance degrades to O(n)\n\n👉 Bad hashCode kills performance."
    },
    {
      "id": 23,
      "section": "Real Interview Trick Questions",
      "question": "Why is MutableList dangerous in multi-threaded Android apps?",
      "difficulty": "Hard",
      "tags": ["android", "threading"],
      "markdown": "### MutableList in Multi-threading\n\n- Not thread-safe\n- Causes race conditions\n- Leads to crashes\n\n👉 Prefer immutable collections or concurrent collections."
    },
    {
      "id": 24,
      "section": "Real Interview Trick Questions",
      "question": "Can Kotlin List be modified? Why or why not?",
      "difficulty": "Medium",
      "tags": ["kotlin"],
      "markdown": "### Kotlin List Mutability\n\n- Kotlin List is read-only interface\n- Underlying collection may still be mutable\n\n👉 Kotlin immutability is not strict."
    },
    {
      "id": 25,
      "section": "Real Interview Trick Questions",
      "question": "Why does SparseArray exist when we already have HashMap?",
      "difficulty": "Medium",
      "tags": ["android"],
      "markdown": "### SparseArray Purpose\n\n- Optimized for integer keys\n- Avoids boxing of Integer\n- Uses less memory than HashMap\n\n👉 Designed for Android performance."
    }
]
}
