{
"category": "Java & Android",
"format": "Markdown inside JSON",
"questions": [
{
"id": 1,
"section": "Java Fundamentals",
"question": "Explain the difference between == and .equals(). How does it affect object comparison in Android apps?",
"difficulty": "Medium",
"tags": ["java", "comparison", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### == vs .equals()\n\n- `==` → compares **references** (memory address)\n- `.equals()` → compares **object content** (logical equality)\n\n**Example:**\n```java\nString a = new String(\"hi\");\nString b = new String(\"hi\");\nLog.d(\"Test\", (a == b) + \", \" + a.equals(b)); // false, true\n```\n**Android impact:** Using `==` instead of `.equals()` on Strings, Lists, or custom objects can lead to UI bugs or unexpected behavior."
},
{
"id": 2,
"section": "Java Fundamentals",
"question": "What is a Java memory leak? Give an example scenario in Android that could cause it.",
"difficulty": "Medium",
"tags": ["memory", "android", "java"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Java Memory Leak in Android\n\n- Memory leak → object is no longer needed but still referenced\n\n**Example:**\n```java\nclass MyActivity extends Activity {\n    static MyActivity instance;\n    void onCreate() {\n        instance = this; // Activity cannot be garbage collected\n    }\n}\n```\n- Retaining a reference to Activity or Context statically can leak memory."
},
{
"id": 3,
"section": "Java Fundamentals",
"question": "Difference between final, finally, and finalize(). How might you use final variables in Android?",
"difficulty": "Medium",
"tags": ["java", "keywords", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### final vs finally vs finalize()\n\n- `final` → constant value or cannot override method/class\n- `finally` → block always executed after try-catch\n- `finalize()` → called by GC before object is destroyed (deprecated)\n\n**Use in Android:**\n```java\nfinal int MAX_COUNT = 10; // Constant\nfinal class Utils {} // Cannot extend\n```"
},
{
"id": 4,
"section": "Java Fundamentals",
"question": "What is autoboxing and unboxing? Can it cause performance issues in Android lists like ArrayList<Integer>?",
"difficulty": "Medium",
"tags": ["java", "performance", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Autoboxing & Unboxing\n\n- **Autoboxing** → converting primitive to wrapper automatically (`int -> Integer`)\n- **Unboxing** → converting wrapper to primitive automatically (`Integer -> int`)\n\n**Performance impact:**\n```java\nArrayList<Integer> list = new ArrayList<>();\nfor(int i=0; i<1000; i++) list.add(i); // creates 1000 Integer objects\n```\n- Can cause **GC overhead** and memory usage. Prefer `IntArray` or primitive arrays when performance matters."
},
{
"id": 5,
"section": "Java Fundamentals",
"question": "Explain static vs instance variables. How does misuse of static variables cause memory leaks in Android?",
"difficulty": "Medium",
"tags": ["java", "android", "memory"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Static vs Instance Variables\n\n- **Static** → belongs to class, shared across instances\n- **Instance** → belongs to object, each object has its own\n\n**Android impact:**\n- Storing Activity/Context in a static variable can prevent GC → memory leak\n```java\nstatic Context ctx;\nvoid setCtx(Context c) { ctx = c; }\n```"
},
{
"id": 6,
"section": "OOP & Design Patterns",
"question": "Explain encapsulation, inheritance, and polymorphism with Android examples.",
"difficulty": "Medium",
"tags": ["oop", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### OOP Principles in Android\n\n- **Encapsulation:** Keep fields private, expose via getter/setter\n```java\nprivate String name; public String getName() { return name; }\n```\n- **Inheritance:** Subclass Activity or ViewModel\n```java\nclass MyActivity extends AppCompatActivity {}\n```\n- **Polymorphism:** Override methods, interface implementations\n```java\ninterface Clickable { void onClick(); }\nclass Button implements Clickable { @Override void onClick() {} }\n```"
},
{
"id": 7,
"section": "OOP & Design Patterns",
"question": "What is the Singleton pattern, and why should you be careful using it in Android (e.g., for Context)?",
"difficulty": "Medium",
"tags": ["singleton", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Singleton Pattern\n\n- Ensures only **one instance** exists\n```java\npublic class MySingleton {\n  private static MySingleton instance;\n  private MySingleton() {}\n  public static synchronized MySingleton getInstance() {\n    if(instance==null) instance = new MySingleton();\n    return instance;\n  }\n}\n```\n- **Android caution:** Avoid holding `Activity` or `Context` references in Singleton → memory leaks"
},
{
"id": 8,
"section": "OOP & Design Patterns",
"question": "How is Observer pattern implemented in Android? Give examples (LiveData, BroadcastReceiver).",
"difficulty": "Medium",
"tags": ["observer", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Observer Pattern in Android\n\n- Observer pattern → objects subscribe to updates\n\n**Examples:**\n- `LiveData.observe()` in MVVM\n- `BroadcastReceiver` listening to system events\n```kotlin\nliveData.observe(this) { data -> updateUI(data) }\n```\n- Observers get notified when state changes."
},
{
"id": 9,
"section": "OOP & Design Patterns",
"question": "Explain Factory pattern in Android. Can you give an example using Fragments or ViewModels?",
"difficulty": "Medium",
"tags": ["factory", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Factory Pattern\n\n- Provides **interface for creating objects** but lets subclasses decide implementation\n\n**Example: Fragment Factory**\n```kotlin\nclass FragmentFactory {\n  fun createFragment(type: String): Fragment {\n    return when(type) {\n      \"Home\" -> HomeFragment()\n      \"Profile\" -> ProfileFragment()\n      else -> DefaultFragment()\n    }\n  }\n}\n```"
},
{
"id": 10,
"section": "OOP & Design Patterns",
"question": "Difference between abstract class and interface. How do you choose between them in Android projects?",
"difficulty": "Medium",
"tags": ["oop", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Abstract Class vs Interface\n\n- **Abstract Class:** can have state and implemented methods, extends only once\n- **Interface:** only method signatures + default implementations, multiple inheritance allowed\n\n**Android:**\n- Use **interface** for callbacks/listeners\n- Use **abstract class** for base Activities/ViewModels with shared behavior"
},
{
"id": 11,
"section": "Multithreading & Concurrency",
"question": "Explain Thread, Runnable, HandlerThread, AsyncTask, Executors. Which is recommended for modern Android apps?",
"difficulty": "Medium",
"tags": ["multithreading", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### Threads & Executors in Android\n\n- **Thread** → basic thread\n- **Runnable** → task executed on a thread\n- **HandlerThread** → thread with Looper for handling messages\n- **AsyncTask** → deprecated, background tasks with UI update\n- **Executors** → thread pool management, preferred over manual threads\n\n**Modern Android:** Use **Executors** + Kotlin Coroutines (recommended)"
},
{
"id": 12,
"section": "Multithreading & Concurrency",
"question": "What are synchronized blocks and locks? How would you use them to prevent race conditions in Android?",
"difficulty": "Medium",
"tags": ["multithreading", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Synchronized Blocks & Locks\n\n- `synchronized` → ensures only one thread executes a block at a time\n```java\nsynchronized(this) { counter++; }\n```\n- Locks (`ReentrantLock`) → more advanced control\n- Prevents race conditions when accessing shared resources (e.g., updating shared preferences)"
},
{
"id": 13,
"section": "Multithreading & Concurrency",
"question": "Difference between ThreadPoolExecutor and single-thread Executor in Android context.",
"difficulty": "Medium",
"tags": ["executor", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### ThreadPoolExecutor vs SingleThreadExecutor\n\n- **ThreadPoolExecutor** → multiple threads, parallel execution, better for CPU-intensive tasks\n- **SingleThreadExecutor** → one thread sequential execution, useful for ordered tasks (e.g., logging, database writes)"
},
{
"id": 14,
"section": "Multithreading & Concurrency",
"question": "Explain volatile keyword. How can it help with multi-threaded operations in Android?",
"difficulty": "Medium",
"tags": ["multithreading", "android"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Volatile Keyword\n\n- Ensures **visibility** of changes to variables across threads\n- Avoids caching in CPU registers\n\n```java\nprivate volatile boolean isRunning = true;\n```\n- Use for flags or simple shared state (non-atomic operations still need synchronization)"
},
{
"id": 15,
"section": "Multithreading & Concurrency",
"question": "How does Looper and Handler work under the hood in Android main thread?",
"difficulty": "Medium",
"tags": ["android", "handler", "looper"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Looper & Handler in Android\n\n- **Looper** → processes a message queue on a thread\n- **Handler** → posts Runnable or Message to a Looper's queue\n- Main thread has default Looper → updates UI safely\n```java\nHandler handler = new Handler(Looper.getMainLooper());\nhandler.post(() -> textView.setText(\"Hello\"));\n```"
},
{
"id": 1,
"section": "Java & Android Integration",
"question": "Difference between Context.getApplicationContext() vs Activity context. Give examples where misuse can cause memory leaks.",
"difficulty": "Medium",
"tags": ["android", "context", "memory"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Application Context vs Activity Context\n\n- `getApplicationContext()` → lifecycle tied to the app\n- `Activity Context` → lifecycle tied to the Activity\n\n**Example misuse:**\n```java\nstatic ImageLoader loader;\nvoid onCreate() {\n    loader = new ImageLoader(this); // Activity context -> memory leak if Activity destroyed\n}\n```\n- Use `applicationContext` for singletons, services, or long-lived objects."
},
{
"id": 2,
"section": "Java & Android Integration",
"question": "How are inner classes handled in Android? Why can non-static inner classes lead to memory leaks?",
"difficulty": "Medium",
"tags": ["android", "memory", "innerclass"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Inner Classes in Android\n\n- **Non-static inner class** holds an implicit reference to the outer class\n- **Memory leak risk:** if inner class runs async tasks (Handler, Thread) and Activity is destroyed\n\n**Solution:** use `static` inner class + `WeakReference` to outer class\n```java\nstatic class MyHandler extends Handler {\n    private final WeakReference<Activity> activityRef;\n}\n```"
},
{
"id": 3,
"section": "Java & Android Integration",
"question": "Explain Parcelable vs Serializable in Java for Android. Which is more efficient and why?",
"difficulty": "Medium",
"tags": ["android", "serialization"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Parcelable vs Serializable\n\n- **Serializable** → standard Java interface, uses reflection, slower\n- **Parcelable** → Android specific, manual implementation, faster, less GC overhead\n\n**Recommendation:**\n- Use **Parcelable** for passing objects via Intent or Bundle\n```kotlin\ndata class User(val name: String, val age: Int) : Parcelable\n```"
},
{
"id": 4,
"section": "Java & Android Integration",
"question": "How does Java's Garbage Collector work in Android? How can improper use of static references affect it?",
"difficulty": "Medium",
"tags": ["android", "gc", "memory"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Garbage Collector in Android\n\n- Android JVM automatically frees objects **no longer referenced**\n- **Static references** keep objects alive → prevent GC → memory leaks\n\n**Example:**\n```java\nstatic Bitmap bitmap; // remains in memory even if Activity destroyed\n```\n- Always clear static references when not needed."
},
{
"id": 5,
"section": "Java & Android Integration",
"question": "Explain Java Reflection and a case where it can be used in Android (like dynamic View inflation).",
"difficulty": "Medium",
"tags": ["android", "reflection", "advanced"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Java Reflection in Android\n\n- **Reflection** → inspect/modify classes, fields, methods at runtime\n\n**Use-case example:**\n- Dynamic View inflation based on class name\n```java\nClass clazz = Class.forName(\"com.example.MyCustomView\");\nConstructor constructor = clazz.getConstructor(Context.class);\nView view = (View) constructor.newInstance(context);\n```\n- Useful for dynamic module loading, plugin architecture, or testing"
},
{
"id": 6,
"section": "Advanced/Tricky Questions",
"question": "How would you implement a thread-safe LRU cache in Android using Java?",
"difficulty": "Hard",
"tags": ["android", "cache", "multithreading"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### Thread-safe LRU Cache\n\n- Use **LinkedHashMap** with access-order + synchronized block\n```java\nclass LRUCache<K,V> {\n  private final LinkedHashMap<K,V> map;\n  LRUCache(int capacity) {\n    map = new LinkedHashMap<>(capacity, 0.75f, true) {\n      protected boolean removeEldestEntry(Map.Entry<K,V> eldest) {\n        return size() > capacity;\n      }\n    };\n  }\n  public synchronized V get(K key) { return map.get(key); }\n  public synchronized void put(K key, V value) { map.put(key,value); }\n}\n```"
},
{
"id": 7,
"section": "Advanced/Tricky Questions",
"question": "Explain the difference between SoftReference, WeakReference, and PhantomReference. How are they useful in Android?",
"difficulty": "Hard",
"tags": ["android", "memory", "references"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### Java References in Android\n\n- **WeakReference** → GC can collect when no strong refs exist (e.g., caching Views)\n- **SoftReference** → GC collects only if memory is low (e.g., memory-sensitive caches)\n- **PhantomReference** → used for cleanup before object is removed\n\n**Example:** Bitmap cache using WeakReference to avoid memory leaks"
},
{
"id": 8,
"section": "Advanced/Tricky Questions",
"question": "What happens if you call wait() on the main thread in Android?",
"difficulty": "Hard",
"tags": ["android", "multithreading"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### wait() on Main Thread\n\n- Blocks **UI thread** → app becomes unresponsive (ANR)\n- Always use background thread + Looper/Handler or coroutines\n```java\nnew Thread(() -> { synchronized(obj) { obj.wait(); } }).start();\n```"
},
{
"id": 9,
"section": "Advanced/Tricky Questions",
"question": "How does Java’s equals() and hashCode() contract affect HashMap caching in Android?",
"difficulty": "Medium",
"tags": ["android", "hashmap", "java"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### equals() & hashCode() Contract\n\n- `equals()` → logical equality\n- `hashCode()` → used by hash-based collections\n\n**Impact on HashMap:**\n- If two equal objects have different hashCodes → HashMap fails to retrieve value\n- Correctly override both when using custom objects as keys"
},
{
"id": 10,
"section": "Advanced/Tricky Questions",
"question": "Explain the concept of Deadlock and Livelock with Android examples (e.g., two threads accessing shared resources).",
"difficulty": "Hard",
"tags": ["android", "concurrency"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1.5 min",
"markdown": "### Deadlock & Livelock in Android\n\n- **Deadlock:** two threads wait for each other’s locks → never proceed\n```java\nThread1 locks A then B, Thread2 locks B then A → deadlock\n```\n- **Livelock:** threads active but cannot make progress (constantly yielding)\n- **Android example:** two threads updating shared DB rows or resources simultaneously\n- **Solution:** proper lock ordering, use `tryLock`, or higher-level constructs like Executors"
}


]
}
