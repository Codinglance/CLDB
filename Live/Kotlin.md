{
  "category": "Kotlin",
  "format": "Markdown inside JSON",
  "questions": [
    {
      "id": 1,
      "section": "Core Kotlin",
      "question": "What is the difference between val and var?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "In Kotlin, `val` and `var` are used to declare variables, but they differ in **mutability**.  \n\n- **`val` (Immutable)**  \n  - The value **cannot be changed** once assigned.  \n  - Helps write safer, predictable code.  \n  - Example:  \n    ```kotlin\n    val name = \"Aasim\"\n    // name = \"John\" // ❌ Error\n    ```\n\n- **`var` (Mutable)**  \n  - The value **can be reassigned** anytime.  \n  - Useful when the variable needs to change during program execution.  \n  - Example:  \n    ```kotlin\n    var age = 25\n    age = 26 // ✅ Allowed\n    ```"
    },
    {
      "id": 2,
      "section": "Core Kotlin",
      "question": "What is the advantage of using const in Kotlin?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "In Kotlin, `const` is used to declare **compile-time constants**. These are immutable values known at compile time, offering several advantages:\n\n#### \uD83D\uDD39 Advantages\n\n- **Performance** – Since values are determined at compile time, accessing them is faster than regular `val`.  \n- **Immutability** – Ensures the value cannot be changed anywhere in the code.  \n- **Global Access** – Can be used at the **top level** or in `object` declarations, making them accessible without creating an instance.  \n- **Cleaner Code** – Ideal for defining constants like URLs, keys, or fixed numbers.\n\n---\n\n#### \uD83D\uDD39 Example\n```kotlin\nconst val BASE_URL = \"https://api.example.com/\"\nconst val MAX_RETRY = 3\n````"
    },
    {
      "id": 3,
      "section": "Core Kotlin",
      "question": "When to use lateinit and how to check if it has been initialized?",
      "difficulty": "Medium",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "`lateinit` is used to **declare non-null variables without initializing them immediately**. It is commonly used for **dependencies or properties** that will be initialized later, like Android views or injected objects.\n\n\n#### \uD83D\uDD39 When to Use `lateinit`\n- For **non-null `var` properties** that cannot be initialized in the constructor.  \n- Common in Android for views:  \n```kotlin\nlateinit var textView: TextView\n````\n\n#### \uD83D\uDD39 How to Check Initialization\n\n* Use `::variableName.isInitialized` to verify before accessing it:\n\n```kotlin\nif (::textView.isInitialized) {\n    textView.text = \"Hello\"\n}\n```"
    },
    {
      "id": 4,
      "section": "Core Kotlin",
      "question": "How to do lazy initialization of variables in Kotlin?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "Lazy initialization allows you to **initialize a variable only when it is accessed for the first time**, improving performance and saving resources.\n\n#### \uD83D\uDD39 How to Use `lazy`\n- Use the `lazy` delegate for **read-only (`val`) properties**.  \n```kotlin\nval name: String by lazy {\n    println(\"Initializing name\")\n    \"Aasim\"\n}\n````\n* The block runs **only once**, on the first access of `name`.\n\n#### \uD83D\uDD39 Key Points\n\n* `lazy` is **thread-safe** by default.\n* Ideal for **expensive operations** or values not needed immediately.\n* Only works with **`val`**, not `var`."
    },
    {
      "id": 5,
      "section": "Core Kotlin",
      "question": "What is an init block in Kotlin?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "The `init` block in Kotlin is an **initializer block** that runs **when an instance of a class is created**. It is used to execute code or initialize properties during object creation.\n\n---\n\n#### \uD83D\uDD39 Key Points\n- Can have **multiple `init` blocks**; they execute in the order defined.  \n- Runs **after primary constructor parameters are passed**.  \n- Often used for **validation, logging, or complex property initialization**.\n\n---\n\n#### \uD83D\uDD39 Example\n```kotlin\nclass User(val name: String) {\n    init {\n        println(\"User $name is being created\")\n    }\n}\n\nval user = User(\"Aasim\")\n// Output: User Aasim is being created\n````"
    },
    {
      "id": 6,
      "section": "Core Kotlin",
      "question": "Explain the difference between == and === in Kotlin.",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "In Kotlin, `==` and `===` are used for **comparison**, but they check **different things**.\n\n#### \uD83D\uDD39 `==` (Structural Equality)\n- Checks if **values are equal**.  \n- Calls the `equals()` method internally.  \n- Example:  \n```kotlin\nval a = \"Hello\"\nval b = \"Hello\"\nprintln(a == b) // ✅ true\n````\n#### \uD83D\uDD39 `===` (Referential Equality)\n\n* Checks if **both references point to the same object** in memory.\n* Example:\n\n```kotlin\nval a = \"Hello\"\nval b = \"Hello\"\nprintln(a === b) // ✅ true or false depending on memory reference\n```"
    },
    {
      "id": 7,
      "section": "Core Kotlin",
      "question": "What are companion objects in Kotlin?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "A **companion object** is a singleton inside a class that holds **class-level members**, similar to Java’s `static`.\n\n#### \uD83D\uDD39 Key Points\n- Declared with `companion object` inside a class.  \n- Can contain **constants, factory methods, utilities**.  \n- Accessed **without creating an instance**.  \n\n\n#### \uD83D\uDD39 Example\n```kotlin\nclass MyClass {\n    companion object {\n        const val VERSION = 1\n        fun create() = MyClass()\n    }\n}\nval version = MyClass.VERSION\nval obj = MyClass.create()\n````"
    },
    {
      "id": 8,
      "section": "Core Kotlin",
      "question": "What is the equivalent of Java static methods in Kotlin?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "Kotlin doesn’t have `static` methods. You can achieve similar functionality using:\n\n- **Companion Object** – Class-level functions accessed without an instance:  \n```kotlin\nclass MyClass {\n    companion object {\n        fun greet() = println(\"Hello\")\n    }\n}\nMyClass.greet()\n````\n\n* **Top-Level Functions** – Functions outside a class, accessible directly:\n\n```kotlin\nfun greet() = println(\"Hello\")\ngreet()\n```"
    },
    {
      "id": 9,
      "section": "Core Kotlin",
      "question": "How to create a Singleton class in Kotlin?",
      "difficulty": "Medium",
      "tags": ["basics", "kotlin", "singleton"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "In Kotlin, creating a singleton is simple using the `object` keyword. This ensures **only one instance** of the class exists.\n#### \uD83D\uDD39 Example\n```kotlin\nobject MySingleton {\n    fun greet() = println(\"Hello from Singleton\")\n}\n\n// Usage\nMySingleton.greet()\n````\n\n#### \uD83D\uDD39 Key Points\n\n* `object` creates a **thread-safe singleton** automatically.\n* No need for `private constructor` or `getInstance()` like in Java.\n* Can contain **properties, methods, and initialization code**."
    },
    {
      "id": 10,
      "section": "Core Kotlin",
      "question": "Explain open, abstract, final, internal, public, and private keywords in Kotlin.",
      "difficulty": "Medium",
      "tags": ["core", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "- **`open`** – Class or function **can be inherited or overridden**.  \n- **`abstract`** – Class or function **must be implemented** in a subclass; cannot be instantiated.  \n- **`final`** – Default modifier; **cannot be inherited or overridden**.  \n- **`public`** – Default visibility; accessible **from anywhere**.  \n- **`private`** – Accessible **within the same class only**.  \n- **`internal`** – Accessible **within the same module**."
    },
    {
      "id": 11,
      "section": "Core Kotlin",
      "question": "What is a data class in Kotlin and what methods are auto-generated?",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin", "data-class"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "A **data class** in Kotlin is a class designed to **hold data**. It automatically generates useful methods, reducing boilerplate code.\n\n#### \uD83D\uDD39 Auto-Generated Methods\n- `equals()` – Checks equality based on property values.  \n- `hashCode()` – Generates hash code based on properties.  \n- `toString()` – Returns a string representation of the object.  \n- `copy()` – Creates a copy of the object with optional property changes.  \n- `componentN()` – Functions for **destructuring declarations**.\n\n#### \uD83D\uDD39 Example\n```kotlin\ndata class User(val name: String, val age: Int)\n\nval user1 = User(\"Aasim\", 25)\nval user2 = user1.copy(age = 26)\nprintln(user1) // Output: User(name=Aasim, age=25)\n````"
    },
    {
      "id": 12,
      "section": "Advanced Kotlin",
      "question": "Explain inline classes (value classes) in Kotlin.",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "inline-class"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "Inline classes (value classes) **wrap a single value** without creating an extra object at runtime, improving performance.\n\n#### \uD83D\uDD39 Key Points\n- Declared with `@JvmInline value class`.  \n- Can have **one property** and methods.  \n- Implements interfaces if needed.  \n\n\n#### \uD83D\uDD39 Example\n```kotlin\n@JvmInline\nvalue class UserId(val id: String)\n\nfun printId(userId: UserId) {\n    println(userId.id)\n}\n\nprintId(UserId(\"123\")) // Output: 123\n`"
    },
    {
      "id": 13,
      "section": "Advanced Kotlin",
      "question": "What is the purpose of inline, noinline, crossinline, and reified keywords?",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "functions"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### `inline`, `noinline`, `crossinline`, and `reified` in Kotlin\n\n- **`inline`** – Inlines the function at the call site to reduce lambda overhead.  \n- **`noinline`** – Prevents a lambda parameter of an inline function from being inlined.  \n- **`crossinline`** – Prevents non-local returns in a lambda passed to an inline function.  \n- **`reified`** – Allows access to a generic type at runtime in an inline function.  \n\n#### Example\n```kotlin\ninline fun <reified T> printType(value: Any) {\n    if (value is T) println(\"Value is of type ${T::class}\")\n}\n\nprintType<String>(\"Hello\") // Output: Value is of type class kotlin.String\n```"
    },
    {
      "id": 14,
      "section": "Advanced Kotlin",
      "question": "What are higher-order functions and how do you return a function from a function?",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "functions"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "A **higher-order function** takes a function as a parameter or returns a function.\n\n---\n\n#### \uD83D\uDD39 Example: Passing a Function\n```kotlin\nfun operate(a: Int, b: Int, op: (Int, Int) -> Int) = op(a, b)\nval sum = operate(5, 3) { x, y -> x + y } // 8\n````\n\n#### \uD83D\uDD39 Example: Returning a Function\n\n```kotlin\nfun multiplier(factor: Int): (Int) -> Int = { it * factor }\nval double = multiplier(2)\nprintln(double(5)) // 10\n```"
    },
    {
      "id": 15,
      "section": "Advanced Kotlin",
      "question": "What are lambda expressions in Kotlin?",
      "difficulty": "Easy",
      "tags": ["advanced", "kotlin", "lambda"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "A **lambda expression** is an anonymous function that can be assigned, passed, or returned.\n\n#### \uD83D\uDD39 Examples\n```kotlin\nval sum: (Int, Int) -> Int = { a, b -> a + b }\nprintln(sum(5, 3)) // 8\n\nval square: (Int) -> Int = { it * it }\nprintln(square(4)) // 16\n````"
    },
    {
      "id": 16,
      "section": "Advanced Kotlin",
      "question": "What are extension functions and how do you use them?",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "extension"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "**Extension functions** allow you to **add new functions** to existing classes **without inheriting or modifying them**.\n\n\n#### \uD83D\uDD39 How to Define\n```kotlin\nfun String.addExclamation(): String {\n    return this + \"!\"\n}\n\nval message = \"Hello\".addExclamation()\nprintln(message) // Output: Hello!\n```\n#### \uD83D\uDD39 Key Points\n\n* Can be called like **regular methods** on the class.\n* Does **not actually modify** the original class.\n* Useful for **enhancing library or built-in classes** safely."
    },
    {
      "id": 17,
      "section": "Advanced Kotlin",
      "question": "Explain scope functions (let, apply, run, with, also) and their use-cases.",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "scope-functions"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "Scope functions provide a **temporary scope** for an object, improving readability and conciseness.\n\n- **`let`** – `it` as context; good for **null checks or chaining**.  \n```kotlin\nname?.let { println(it.length) }\n```\n\n- **`run`** – `this` as context; returns **lambda result**; for **computations**.\n```kotlin\nval result = \"Hello\".run { length + 5 }\n```\n\n- **`with`** – `this` as context; called on object; for **grouping operations**.\n```kotlin\nwith(builder) { append(\"Hello\"); append(\"World\") }\n```\n\n- **`apply`** – `this` as context; returns **object**; for **object initialization**.\n```kotlin\nval person = Person().apply { name=\"Aasim\"; age=25 }\n```\n\n- **`also`** – `it` as context; returns **object**; for **side-effects**.\n```kotlin\nval numbers = mutableListOf(1,2,3).also { println(it) }\n```"
    },
    {
      "id": 18,
      "section": "Advanced Kotlin",
      "question": "Difference between apply and with, and when to use each.",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "scope-functions"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Difference Between `apply` and `with`\n\n- **`apply`**  \n  - Called on an object, returns **the object**.  \n  - Use for **object initialization**.  \n```kotlin\nval person = Person().apply { name=\"Aasim\"; age=25 }\n````\n\n* **`with`**\n\n    * Takes an object as parameter, returns **lambda result**.\n    * Use for **grouping operations or computing values**.\n\n```kotlin\nval length = with(\"Hello\") { println(this); length }\n```"
    },
    {
      "id": 19,
      "section": "Advanced Kotlin",
      "question": "What are labels in Kotlin and how do you use them?",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "labels"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "Labels let you **control flow in nested loops or lambdas** using `break`, `continue`, or `return`.\n\n#### \uD83D\uDD39 Example\n```kotlin\nouter@ for (i in 1..3) {\n    for (j in 1..3) {\n        if (i * j > 4) break@outer\n        println(\"$i, $j\")\n    }\n}\n\n```\n* `break@label` – exit a specific loop\n* `continue@label` – continue a specific loop\n* `return@label` – return from a lambda or function"
    },
    {
      "id": 20,
      "section": "Advanced Kotlin",
      "question": "Explain sealed classes and common use-cases in Android.",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "sealed"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "Sealed classes represent **restricted class hierarchies** where all possible subclasses are known at compile time.\n\n\n#### \uD83D\uDD39 Key Points\n- Declared using `sealed class`.\n- All subclasses must be defined in the same file.\n- Useful with `when` expressions because it ensures **exhaustive checks** (no `else` needed).\n\n\n#### \uD83D\uDD39 Common Android Use-Cases\n- **UI State Handling** – Loading, Success, Error states.\n- **API Response Wrappers** – Success, Failure, Loading results.\n- **Navigation Events** – Different navigation actions.\n- **ViewModel State Management** – Represent screen states clearly.\n\n\n#### \uD83D\uDD39 Example\n```kotlin\nsealed class UiState {\n    object Loading : UiState()\n    data class Success(val data: String) : UiState()\n    data class Error(val message: String) : UiState()\n}\n````"
    },
    {
      "id": 21,
      "section": "Core Kotlin",
      "question": "Difference between List and Array types in Kotlin.",
      "difficulty": "Easy",
      "tags": ["basics", "kotlin", "collections"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "\uD83D\uDD39 **List**\n\n* Part of Kotlin Collections.\n* Usually **immutable** (`listOf()`).\n* Dynamic size.\n* Provides many built-in utility functions.\n\n\uD83D\uDD39 **Array**\n\n* Fixed size once created.\n* Mutable (elements can be changed).\n* Created using `arrayOf()`.\n* Closer to low-level memory structure.\n\n✅ **Use List** → When you need flexible, collection-based operations.\n✅ **Use Array** → When size is fixed or performance/memory control is needed."
    },
    {
      "id": 22,
      "section": "Core Kotlin",
      "question": "How to remove duplicates from an array or collection in Kotlin?",
      "difficulty": "Easy",
      "tags": ["collections", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "* Use `distinct()` → Returns list with unique elements.\n\n```kotlin\nval list = listOf(1, 2, 2, 3, 3)\nval unique = list.distinct()\n```\n\n* Use `toSet()` → Removes duplicates by converting to Set.\n\n```kotlin\nval unique = list.toSet()\n```\n\n* For Array\n\n```kotlin\nval arr = arrayOf(1, 2, 2, 3)\nval unique = arr.distinct()\n```\n\n✅ `distinct()` keeps order\n✅ `toSet()` removes duplicates but may not guarantee order"
    },
    {
      "id": 23,
      "section": "Advanced Kotlin",
      "question": "Explain Delegates (lazy, observable, vetoable) in Kotlin.",
      "difficulty": "Medium",
      "tags": ["advanced", "kotlin", "delegates"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "Delegates allow you to delegate property behavior to another object.\n\n* **`lazy`**\n\n    * Initializes value **only when accessed first time**.\n    * Useful for expensive object creation.\n\n  ```kotlin\n  val data by lazy { loadData() }\n  ```\n\n* **`observable`**\n\n    * Triggers callback **after value changes**.\n    * Useful for tracking or updating UI.\n\n  ```kotlin\n  var name by Delegates.observable(\"A\") { _, old, new ->\n      println(\"$old -> $new\")\n  }\n  ```\n\n* **`vetoable`**\n\n    * Allows **validation before value changes**.\n    * Change happens only if condition returns `true`.\n\n  ```kotlin\n  var age by Delegates.vetoable(18) { _, _, new ->\n      new >= 18\n  }\n  ```"
    },
    {
      "id": 1,
      "section": "Basics",
      "question": "What are coroutines in Kotlin?",
      "difficulty": "Easy",
      "tags": ["coroutines", "async", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "**Coroutines** are a lightweight concurrency feature in Kotlin used to perform **asynchronous and non-blocking tasks** in a simple and efficient way.\n\n\n#### \uD83D\uDD39 Key Points\n\n* Help run **background tasks** like API calls, database operations, etc.\n* More efficient than traditional threads.\n* Use **suspend functions** to pause and resume execution without blocking the main thread.\n* Work with **CoroutineScope**, **Dispatchers**, and **Jobs** for lifecycle and threading control.\n\n\n#### \uD83D\uDD39 Example\n\n```kotlin\nCoroutineScope(Dispatchers.IO).launch {\n    val data = fetchData()\n    withContext(Dispatchers.Main) {\n        updateUI(data)\n    }\n}\n```"
    },
    {
      "id": 2,
      "section": "Basics",
      "question": "Difference between suspending and blocking functions.",
      "difficulty": "Medium",
      "tags": ["coroutines", "async"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "#### \uD83D\uDD39 Suspending Functions\n\n* Use the `suspend` keyword.\n* **Pause execution without blocking the thread**.\n* Allow other tasks to run while waiting (efficient).\n* Mainly used with **coroutines**.\n\n**Example**\n\n```kotlin\nsuspend fun fetchData() {\n    delay(1000) // Non-blocking delay\n}\n```\n\n\n#### \uD83D\uDD39 Blocking Functions\n\n* **Block the current thread** until the task finishes.\n* Prevent other tasks from running on that thread.\n* Can cause UI freezes if used on the main thread.\n\n**Example**\n\n```kotlin\nfun fetchData() {\n    Thread.sleep(1000) // Blocks thread\n}"
    }
  ]
}
