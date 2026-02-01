{
"category": "kotlin",
"title": "Kotlin Interview Questions",
"level": "Beginner to Intermediate",
"items": [
{
"id": 1,
"question": "What are the main features of Kotlin?",
"answer": "**Kotlin** is a modern programming language fully interoperable with Java.\n\n**Key Features:**\n- Concise syntax (less boilerplate)\n- Null safety (avoids NullPointerException)\n- 100% interoperable with Java\n- Functional programming support\n- Extension functions\n- Smart casts\n- Coroutines for asynchronous programming"
},
{
"id": 2,
"question": "Difference between var, val, and const",
"answer": "| Keyword | Description | Use Case |\n|--------|-------------|----------|\n| `var` | Mutable variable | Can be reassigned |\n| `val` | Immutable variable | Read-only after initialization |\n| `const` | Compile-time constant (must be `val`) | Used at top-level or inside `object` |\n\n```kotlin\nvar name = \"Aasim\"\nval age = 25\nconst val PI = 3.14\n```"
},
{
"id": 3,
"question": "What is a Kotlin data class?",
"answer": "**Data class:** Used to hold data and automatically generates `toString()`, `equals()`, `hashCode()`, and `copy()`.\n\n```kotlin\ndata class User(val name: String, val age: Int)\n```\n\n**Advantages:**\n- Reduces boilerplate\n- Provides `componentN()` for destructuring\n- Ideal for DTOs and API models"
},
{
"id": 4,
"question": "Difference between `==` and `===` in Kotlin",
"answer": "| Operator | Meaning |\n|--------|---------|\n| `==` | Structural equality (value comparison) |\n| `===` | Referential equality (same object reference) |\n\n```kotlin\nval a = \"Hello\"\nval b = \"Hello\"\nprintln(a == b)\nprintln(a === b)\n```"
},
{
"id": 5,
"question": "What is Kotlin null safety?",
"answer": "**Null Safety:** Prevents NullPointerException by distinguishing nullable and non-nullable types.\n\n- Non-nullable: `val name: String = \"Aasim\"`\n- Nullable: `val name: String? = null`\n\n```kotlin\nval length = name?.length ?: 0\n```"
},
{
"id": 6,
"question": "What are Kotlin extension functions?",
"answer": "**Extension functions** add new functionality to existing classes without inheritance.\n\n```kotlin\nfun String.reverseText(): String = this.reversed()\n\nprintln(\"Kotlin\".reverseText())\n```\n\n**Use Case:**\n- Add utility/helper methods cleanly"
},
{
"id": 7,
"question": "Difference between open, abstract, and interface",
"answer": "| Keyword | Description |\n|-------|-------------|\n| `open` | Allows inheritance and overriding |\n| `abstract` | Cannot be instantiated; must override abstract methods |\n| `interface` | Defines a contract; no constructor; supports default methods |\n\n```kotlin\nopen class A\nabstract class B { abstract fun work() }\ninterface C { fun doWork() }\n```"
},
{
"id": 8,
"question": "What are Kotlin coroutines?",
"answer": "**Coroutines:** Lightweight threads for asynchronous, non-blocking programming.\n\n**Key Points:**\n- Efficient\n- Non-blocking\n- Uses `suspend` functions\n\n```kotlin\nGlobalScope.launch {\n  val data = fetchData()\n  println(data)\n}\n\nsuspend fun fetchData(): String {\n  delay(1000)\n  return \"Hello Coroutine\"\n}\n```"
},
{
"id": 9,
"question": "Difference between map, flatMap, and filter",
"answer": "| Function | Description | Example |\n|--------|-------------|---------|\n| `map` | Transforms elements | `[1,2,3].map { it * 2 }` → `[2,4,6]` |\n| `flatMap` | Flattens nested lists | `[[1,2],[3,4]].flatMap { it }` → `[1,2,3,4]` |\n| `filter` | Filters by condition | `[1,2,3,4].filter { it > 2 }` → `[3,4]` |"
},
{
"id": 10,
"question": "Difference between lateinit and lazy",
"answer": "| Keyword | Description |\n|-------|-------------|\n| `lateinit` | Used with `var`; initialized later; non-null only |\n| `lazy` | Used with `val`; initialized on first access |\n\n```kotlin\nlateinit var name: String\nval age: Int by lazy { computeAge() }\n```"
}
]
}
