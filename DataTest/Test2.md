{
  "category": "Kotlin",
  "format": "Markdown inside JSON",
  "questions": [
    {
      "id": 1,
      "section": "Kotlin Basics",
      "question": "What is Kotlin?",
      "difficulty": "Easy",
      "tags": ["basics", "introduction"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "### Kotlin\n\nKotlin is a **modern, statically typed programming language** developed by JetBrains.\n\n- Official language for Android\n- Fully interoperable with Java\n- Concise and safe"
    },
    {
      "id": 2,
      "section": "Kotlin Basics",
      "question": "Why is Kotlin preferred over Java?",
      "difficulty": "Easy",
      "expectedReadTime": "1 min",
      "tags": ["basics"],
      "askedIn": ["Google", "Amazon"],
      "markdown": "### Kotlin vs Java\n\n- Less boilerplate\n- Null safety\n- Extension functions\n- Coroutines for async\n- Better readability"
    },
    {
      "id": 3,
      "section": "Kotlin Basics",
      "question": "Difference between val and var?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics"],
      "askedIn": ["Google"],
      "markdown": "### val vs var\n\n```kotlin\nval name = \"Aasim\" // immutable\nvar age = 25\nage = 26\n```\n\n👉 Prefer `val` whenever possible."
    },
    {
      "id": 4,
      "section": "Kotlin Basics",
      "question": "Explain Kotlin null safety.",
      "difficulty": "Easy",
      "expectedReadTime": "1 min",
      "tags": ["null-safety"],
      "askedIn": ["Google", "Amazon"],
      "markdown": "### Null Safety\n\nKotlin avoids `NullPointerException` by differentiating nullable and non-nullable types.\n\n```kotlin\nvar name: String? = null\n```\n\nOperators:\n- `?` nullable\n- `?.` safe call\n- `?:` Elvis\n- `!!` not-null assertion"
    },
    {
      "id": 5,
      "section": "Kotlin Basics",
      "question": "What is the Elvis operator?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["operators"],
      "askedIn": ["Google"],
      "markdown": "### Elvis Operator (?:)\n\nProvides a default value when expression is null.\n\n```kotlin\nval name = userName ?: \"Guest\"\n```"
    },
    {
      "id": 6,
      "section": "Classes & Objects",
      "question": "What are data classes?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["classes"],
      "askedIn": ["Google", "Amazon"],
      "markdown": "### Data Class\n\nUsed to hold data.\n\n```kotlin\ndata class User(val name: String, val age: Int)\n```\n\nAuto-generates:\n- `toString()`\n- `equals()`\n- `hashCode()`\n- `copy()`"
    },
    {
      "id": 7,
      "section": "Classes & Objects",
      "question": "Difference between == and ===?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["operators"],
      "askedIn": ["Amazon"],
      "markdown": "### Equality\n\n- `==` → Structural equality (value)\n- `===` → Referential equality (same memory reference)"
    },
    {
      "id": 8,
      "section": "Functions",
      "question": "What are higher-order functions?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["functions"],
      "askedIn": ["Google"],
      "markdown": "### Higher-Order Functions\n\nFunctions that **take functions as parameters** or **return functions**.\n\n```kotlin\nfun operate(a:Int, b:Int, op:(Int,Int)->Int) = op(a,b)\n```"
    },
    {
      "id": 9,
      "section": "Functions",
      "question": "What are lambda expressions?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["functions"],
      "askedIn": ["Google"],
      "markdown": "### Lambda\n\nAnonymous function.\n\n```kotlin\nval sum = { a:Int, b:Int -> a + b }\n```"
    },
    {
      "id": 10,
      "section": "Functions",
      "question": "Explain scope functions.",
      "difficulty": "Medium",
      "expectedReadTime": "2 min",
      "tags": ["scope-functions"],
      "askedIn": ["Google", "Amazon"],
      "markdown": "### Scope Functions\n\n- `let` → null safety\n- `apply` → configure object\n- `also` → side effects\n- `run` → object + result\n- `with` → operate without extension"
    },
    {
      "id": 11,
      "section": "Coroutines",
      "question": "What are coroutines?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["coroutines"],
      "askedIn": ["Google", "Amazon"],
      "markdown": "### Coroutines\n\nLightweight concurrency framework for async programming.\n\n- Non-blocking\n- Structured concurrency\n- Simpler than threads"
    },
    {
      "id": 12,
      "section": "Coroutines",
      "question": "What is a suspend function?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["coroutines"],
      "askedIn": ["Google"],
      "markdown": "### Suspend Function\n\nA function that can **pause and resume execution**.\n\n```kotlin\nsuspend fun fetchData() {}\n```"
    },
    {
      "id": 13,
      "section": "Coroutines",
      "question": "Difference between launch and async?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["coroutines"],
      "askedIn": ["Amazon"],
      "markdown": "### launch vs async\n\n- `launch` → Job, no result\n- `async` → Deferred, returns result\n\n```kotlin\nval result = async { load() }.await()\n```"
    },
    {
      "id": 14,
      "section": "Coroutines",
      "question": "What is withContext()?",
      "difficulty": "Medium",
      "expectedReadTime": "45 sec",
      "tags": ["coroutines"],
      "askedIn": ["Google"],
      "markdown": "### withContext\n\nSwitches coroutine dispatcher.\n\n```kotlin\nwithContext(Dispatchers.IO) {\n    // background work\n}\n```"
    },
    {
      "id": 15,
      "section": "Advanced Kotlin",
      "question": "What are sealed classes?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["sealed"],
      "askedIn": ["Google"],
      "markdown": "### Sealed Classes\n\nRestricts class hierarchy.\n\nUsed for representing **states** safely."
    },
    {
      "id": 16,
      "section": "Advanced Kotlin",
      "question": "What is companion object?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["objects"],
      "askedIn": ["Amazon"],
      "markdown": "### Companion Object\n\nUsed to declare **static-like members** in Kotlin."
    },
    {
      "id": 17,
      "section": "Advanced Kotlin",
      "question": "What is delegation?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["delegation"],
      "askedIn": ["Google"],
      "markdown": "### Delegation\n\nAllows a class to delegate implementation to another object.\n\n```kotlin\nclass MyPrinter(printer: Printer) : Printer by printer\n```"
    },
    {
      "id": 18,
      "section": "Advanced Kotlin",
      "question": "What is by lazy?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["lazy"],
      "askedIn": ["Google"],
      "markdown": "### Lazy Initialization\n\n```kotlin\nval value: String by lazy { \"Initialized\" }\n```"
    },
    {
      "id": 19,
      "section": "Android + Kotlin",
      "question": "What is ViewModel?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["android"],
      "askedIn": ["Google"],
      "markdown": "### ViewModel\n\nHolds UI state across configuration changes.\n\n```kotlin\nclass MainVM : ViewModel() {}\n```"
    },
    {
      "id": 20,
      "section": "Android + Kotlin",
      "question": "What is StateFlow?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["flow"],
      "askedIn": ["Google"],
      "markdown": "### StateFlow\n\nHot flow that always holds **latest state**."
    },
    {
      "id": 21,
      "section": "Android + Kotlin",
      "question": "Difference between LiveData and StateFlow?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["flow"],
      "askedIn": ["Google"],
      "markdown": "### LiveData vs StateFlow\n\n- LiveData → lifecycle aware\n- StateFlow → Kotlin native, hot stream"
    },
    {
      "id": 22,
      "section": "Android + Kotlin",
      "question": "What is Jetpack Compose?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["compose"],
      "askedIn": ["Google"],
      "markdown": "### Jetpack Compose\n\nModern **declarative UI toolkit** for Android.\n\n```kotlin\n@Composable fun Greeting() {}\n```"
    },
    {
      "id": 23,
      "section": "Android + Kotlin",
      "question": "What is recomposition?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["compose"],
      "askedIn": ["Google"],
      "markdown": "### Recomposition\n\nUI re-executes when state changes."
    },
    {
      "id": 24,
      "section": "Architecture",
      "question": "What is MVVM?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["architecture"],
      "askedIn": ["Google"],
      "markdown": "### MVVM\n\n- Model → Data\n- View → UI\n- ViewModel → State & logic"
    },
    {
      "id": 25,
      "section": "Architecture",
      "question": "What is Clean Architecture?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["architecture"],
      "askedIn": ["Google"],
      "markdown": "### Clean Architecture\n\nSeparates concerns into layers.\n\n- Presentation\n- Domain\n- Data"
    }
  ]
}
