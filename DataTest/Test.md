{
"category": "Android",
"format": "Markdown inside JSON",
"questions": [
    {
      "id": 1,
      "section": "Kotlin Basics",
      "question": "What is Kotlin and why is it preferred over Java for Android?",
      "difficulty": "Easy",
      "tags": ["basics", "introduction"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Kotlin Overview\n\nKotlin is a **modern, statically typed language** developed by JetBrains.\n\n**Why preferred over Java?**\n- Less boilerplate code\n- Built-in null safety\n- Better readability\n- Full Java interoperability\n- Official Android language by Google\n\n👉 Faster development with fewer crashes."
    },
    {
      "id": 2,
      "section": "Kotlin Basics",
      "question": "What is the difference between val and var?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### val vs var\n\n- `val` → Immutable (cannot be reassigned)\n- `var` → Mutable (can be reassigned)\n\n```kotlin\nval name = \"Aasim\"\nvar age = 25\nage = 26\n```\n\n👉 Prefer `val` for safer code."
    },
    {
      "id": 3,
      "section": "Kotlin Basics",
      "question": "Explain Kotlin null safety.",
      "difficulty": "Easy",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Null Safety\n\nKotlin avoids `NullPointerException` by separating nullable and non-nullable types.\n\n```kotlin\nvar name: String? = null\n```\n\nKey tools:\n- `?` nullable\n- `?.` safe call\n- `?:` elvis operator\n- `!!` not-null assertion"
    },
    {
      "id": 4,
      "section": "Kotlin Basics",
      "question": "What is a nullable type and how do you declare it?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Nullable Type\n\nA type that can hold `null`.\n\n```kotlin\nvar email: String? = null\n```\n\n👉 Non-nullable types cannot hold null."
    },
    {
      "id": 5,
      "section": "Kotlin Basics",
      "question": "What is the Elvis operator (?:)?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Elvis Operator\n\nProvides a default value if expression is null.\n\n```kotlin\nval name = userName ?: \"Guest\"\n```"
    },
    {
      "id": 6,
      "section": "Kotlin Basics",
      "question": "What are data classes? Why are they useful?",
      "difficulty": "Easy",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Data Classes\n\nUsed to hold data.\n\n```kotlin\ndata class User(val name: String, val age: Int)\n```\n\nAuto-generates:\n- `toString()`\n- `equals()`\n- `hashCode()`\n- `copy()`"
    },
    {
      "id": 7,
      "section": "Kotlin Basics",
      "question": "Difference between == and === in Kotlin?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### == vs ===\n\n- `==` → Structural equality (value)\n- `===` → Referential equality (memory reference)"
    },
    {
      "id": 8,
      "section": "Kotlin Basics",
      "question": "What is a when expression?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### when Expression\n\nReplacement for switch.\n\n```kotlin\nwhen(x) {\n  1 -> \"One\"\n  else -> \"Other\"\n}\n```\n\n👉 More powerful than switch."
    },
    {
      "id": 9,
      "section": "Kotlin Basics",
      "question": "What are default and named arguments?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Default & Named Arguments\n\n```kotlin\nfun greet(name: String = \"User\") {}\ngreet(name = \"Aasim\")\n```\n\n👉 Improves readability."
    },
    {
      "id": 10,
      "section": "Kotlin Basics",
      "question": "What are smart casts?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Smart Casts\n\nKotlin automatically casts after type check.\n\n```kotlin\nif (obj is String) {\n  println(obj.length)\n}\n```"
    },
    {
      "id": 11,
      "section": "Functions & Classes",
      "question": "What are higher-order functions?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Higher-Order Functions\n\nFunctions that take another function as parameter or return it.\n\n```kotlin\nfun operate(a:Int, b:Int, op:(Int,Int)->Int)\n```"
    },
    {
      "id": 12,
      "section": "Functions & Classes",
      "question": "What are lambda expressions?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Lambda Expression\n\nAnonymous function.\n\n```kotlin\nval sum = { a:Int, b:Int -> a + b }\n```"
    },
    {
      "id": 13,
      "section": "Functions & Classes",
      "question": "Difference between apply, let, also, run, and with?",
      "difficulty": "Medium",
      "expectedReadTime": "2 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Scope Functions\n\n- `let` → null check\n- `apply` → configure object\n- `also` → side effects\n- `run` → object + result\n- `with` → operate without extension"
    },
    {
      "id": 14,
      "section": "Functions & Classes",
      "question": "What is an inline function?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Inline Function\n\nFunction body copied at call site to reduce overhead.\n\n```kotlin\ninline fun doWork() {}\n```"
    },
    {
      "id": 15,
      "section": "Functions & Classes",
      "question": "What are sealed classes?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Sealed Class\n\nRestricts inheritance.\n\nUsed for representing states."
    },
    {
      "id": 16,
      "section": "Functions & Classes",
      "question": "Difference between open, abstract, and final classes?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Class Types\n\n- `final` → default, cannot inherit\n- `open` → can inherit\n- `abstract` → must implement"
    },
    {
      "id": 17,
      "section": "Functions & Classes",
      "question": "What is companion object?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Companion Object\n\nActs like static members in Java."
    },
    {
      "id": 18,
      "section": "Functions & Classes",
      "question": "Object declaration vs object expression?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Object Declaration vs Expression\n\n- Declaration → singleton\n- Expression → anonymous object"
    },
    {
      "id": 19,
      "section": "Functions & Classes",
      "question": "What is a primary constructor?",
      "difficulty": "Easy",
      "expectedReadTime": "30 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Primary Constructor\n\nDeclared in class header."
    },
    {
      "id": 20,
      "section": "Functions & Classes",
      "question": "What is secondary constructor and when to use it?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Secondary Constructor\n\nUsed when additional initialization is needed."
    },
    {
      "id": 21,
      "section": "Coroutines",
      "question": "What are coroutines?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Coroutines\n\nLightweight async programming solution."
    },
    {
      "id": 22,
      "section": "Coroutines",
      "question": "Difference between coroutine and thread?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Coroutine vs Thread\n\nCoroutines are lightweight and cheaper."
    },
    {
      "id": 23,
      "section": "Coroutines",
      "question": "What is suspend function?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### Suspend Function\n\nCan pause and resume execution."
    },
    {
      "id": 24,
      "section": "Coroutines",
      "question": "What is viewModelScope?",
      "difficulty": "Easy",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### viewModelScope\n\nCoroutine scope tied to ViewModel lifecycle."
    },
    {
      "id": 25,
      "section": "Coroutines",
      "question": "Difference between launch and async?",
      "difficulty": "Medium",
      "expectedReadTime": "1 min",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### launch vs async\n\n- `launch` → no result\n- `async` → returns Deferred"
    },
    {
      "id": 26,
      "section": "Coroutines",
      "question": "What is withContext()?",
      "difficulty": "Medium",
      "expectedReadTime": "45 sec",
      "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
      "markdown": "### withContext\n\nSwitches coroutine dispatcher."
    },
      {
        "id": 26,
        "section": "Coroutines",
        "question": "What is withContext()?",
        "difficulty": "Medium",
        "expectedReadTime": "45 sec",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### withContext()\n\n`withContext` is used to switch the coroutine context (dispatcher) and execute a block of code there.\n\n```kotlin\nsuspend fun fetchData() {\n    withContext(Dispatchers.IO) {\n        // network call\n    }\n}\n```\n\n👉 Keeps main thread free for UI updates."
      },
      {
        "id": 27,
        "section": "Coroutines",
        "question": "What is structured concurrency?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Structured Concurrency\n\nCoroutines launched in a **scope** are automatically canceled when the scope is canceled.\n\n```kotlin\nviewModelScope.launch {\n    // all coroutines here are bound to ViewModel\n}\n```\n\n✅ Prevents leaks and orphan coroutines."
      },
      {
        "id": 28,
        "section": "Coroutines",
        "question": "Difference between StateFlow and SharedFlow?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### StateFlow vs SharedFlow\n\n- **StateFlow**: Holds a **state**, emits latest value to new subscribers.\n- **SharedFlow**: Hot stream, emits **events**, does not hold state.\n\n```kotlin\nval stateFlow = MutableStateFlow(0)\nval sharedFlow = MutableSharedFlow<Int>()\n```"
      },
      {
        "id": 29,
        "section": "Coroutines",
        "question": "How do you handle exceptions in coroutines?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Exception Handling\n\nUse `try-catch` inside coroutine or `CoroutineExceptionHandler`.\n\n```kotlin\nval handler = CoroutineExceptionHandler { _, e ->\n    println(\"Error: ${e.localizedMessage}\")\n}\n\nlaunch(handler) {\n    // risky operation\n}\n```"
      },
      {
        "id": 30,
        "section": "Coroutines",
        "question": "Difference between launch and async?",
        "difficulty": "Medium",
        "expectedReadTime": "45 sec",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### launch vs async\n\n- `launch` → Job, no return value\n- `async` → Deferred, returns result\n\n```kotlin\nval result = async { fetchData() }.await()\n```"
      },
      {
        "id": 31,
        "section": "Android + Kotlin",
        "question": "What is Jetpack Compose?",
        "difficulty": "Easy",
        "expectedReadTime": "45 sec",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Jetpack Compose\n\nModern **declarative UI toolkit** for Android.\n- No XML layouts needed\n- Compose UI elements as Kotlin functions\n- Fully reactive with state\n\n```kotlin\n@Composable\nfun Greeting(name: String) {\n    Text(text = \"Hello, $name!\")\n}\n```"
      },
      {
        "id": 32,
        "section": "Android + Kotlin",
        "question": "Difference between XML UI and Compose?",
        "difficulty": "Easy",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### XML vs Compose\n\n| Feature | XML | Compose |\n|---|---|---|\n| Approach | Imperative | Declarative |\n| Updates | findViewById + manual | Auto-recomposition |\n| Boilerplate | High | Low |\n| State handling | ViewModel + LiveData | State + Compose |\n"
      },
      {
        "id": 33,
        "section": "Android + Kotlin",
        "question": "What is recomposition in Compose?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Recomposition\n\nRe-execution of composable functions when **state changes**.\n\n```kotlin\nvar count by remember { mutableStateOf(0) }\nText(\"Count: $count\") // updates automatically\n```"
      },
      {
        "id": 34,
        "section": "Android + Kotlin",
        "question": "What is remember and rememberSaveable?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### remember vs rememberSaveable\n\n- `remember` → survives recompositions, not configuration changes\n- `rememberSaveable` → survives recompositions **and** config changes\n\n```kotlin\nvar text by rememberSaveable { mutableStateOf(\"\") }\n```"
      },
      {
        "id": 35,
        "section": "Android + Kotlin",
        "question": "What is LaunchedEffect?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### LaunchedEffect\n\nRuns a suspend function **once** when key changes.\n\n```kotlin\nLaunchedEffect(Unit) {\n    loadData()\n}\n```"
      },
      {
        "id": 36,
        "section": "Android + Kotlin",
        "question": "How do you manage state in Compose?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### State Management\n\n- `mutableStateOf`\n- `remember` + `mutableStateOf`\n- `ViewModel` + `StateFlow`\n- `rememberSaveable` for config changes\n\nCompose auto updates UI on state changes."
      },
      {
        "id": 37,
        "section": "Android + Kotlin",
        "question": "What is ViewModel and why is it used?",
        "difficulty": "Easy",
        "expectedReadTime": "45 sec",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### ViewModel\n\n- Holds UI data **across configuration changes**\n- Lifecycle-aware\n- Works with LiveData / StateFlow\n\n```kotlin\nclass MainViewModel : ViewModel() {\n    val data = MutableStateFlow(\"\")\n}\n```"
      },
      {
        "id": 38,
        "section": "Android + Kotlin",
        "question": "Difference between LiveData and StateFlow?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### LiveData vs StateFlow\n\n| Feature | LiveData | StateFlow |\n|---|---|---|\n| Lifecycle aware | Yes | No (needs collectWithLifecycle) |\n| Cold/Hot | Cold | Hot |\n| Thread safety | Main thread | Multi-thread safe |\n"
      },
      {
        "id": 39,
        "section": "Android + Kotlin",
        "question": "What is MVVM architecture?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### MVVM Architecture\n\n- **Model** → Data layer\n- **View** → UI layer\n- **ViewModel** → Business logic, state holder\n\nKeeps UI & logic separated, easier testing."
      },
      {
        "id": 40,
        "section": "Android + Kotlin",
        "question": "How does Compose handle lifecycle?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Lifecycle in Compose\n\n- Compose observes **LifecycleOwner** automatically.\n- Use `DisposableEffect` to clean resources on dispose.\n\n```kotlin\nDisposableEffect(Unit) {\n    onDispose { cleanup() }\n}\n```"
      },
      {
        "id": 41,
        "section": "Advanced Kotlin & Android",
        "question": "What are inline classes (value classes)?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Inline (Value) Classes\n\nWrap a value **without extra allocation**.\n\n```kotlin\n@JvmInline value class UserId(val id: Int)\n```"
      },
      {
        "id": 42,
        "section": "Advanced Kotlin & Android",
        "question": "What is delegation in Kotlin?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Delegation\n\nForward method calls to another object.\n\n```kotlin\nclass PrinterDelegate: Printer { override fun print() {} }\nclass MyPrinter(printer: Printer) : Printer by printer\n```"
      },
      {
        "id": 43,
        "section": "Advanced Kotlin & Android",
        "question": "What is by lazy?",
        "difficulty": "Easy",
        "expectedReadTime": "30 sec",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Lazy Initialization\n\n```kotlin\nval name: String by lazy {\n    println(\"Initializing\")\n    \"Aasim\"\n}\n```"
      },
      {
        "id": 44,
        "section": "Advanced Kotlin & Android",
        "question": "What is dependency injection?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Dependency Injection\n\nProvides dependencies from outside rather than creating inside class.\n\n```kotlin\nclass Repository @Inject constructor(val api: ApiService)\n```"
      },
      {
        "id": 45,
        "section": "Advanced Kotlin & Android",
        "question": "What is Hilt and why is it used?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Hilt\n\n- Dependency Injection library for Android.\n- Simplifies ViewModel + Repository injection.\n- Built on Dagger.\n"
      },
      {
        "id": 46,
        "section": "Advanced Kotlin & Android",
        "question": "Difference between Retrofit and Volley?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Retrofit vs Volley\n\n| Feature | Retrofit | Volley |\n|---|---|---|\n| API | REST client | HTTP client |\n| Async | Built-in | Needs listener |\n| Parsing | Converter (Gson/Moshi) | Manual |\n| Ideal | Complex APIs | Simple requests |"
      },
      {
        "id": 47,
        "section": "Advanced Kotlin & Android",
        "question": "How do you handle API errors properly?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### API Error Handling\n\n- Check HTTP status code\n- Use `try-catch`\n- Return sealed class: `Success` / `Error`\n\n```kotlin\nsealed class Result<out T> { data class Success<T>(val data: T): Result<T>() ... }\n```"
      },
      {
        "id": 48,
        "section": "Advanced Kotlin & Android",
        "question": "What is Clean Architecture?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Clean Architecture\n\n- Separation of concerns\n- Layers: Presentation, Domain, Data\n- Testable, maintainable, scalable"
      },
      {
        "id": 49,
        "section": "Advanced Kotlin & Android",
        "question": "What are side effects in Compose?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Side Effects\n\nOperations that **affect outside world**:\n- Logging\n- Networking\n- Database\n\nUse `LaunchedEffect`, `SideEffect`, `DisposableEffect` for handling."
      },
      {
        "id": 50,
        "section": "Advanced Kotlin & Android",
        "question": "How do you optimize Compose performance?",
        "difficulty": "Medium",
        "expectedReadTime": "1 min",
        "tags": ["basics", "introduction"], "askedIn": ["Google", "Amazon"],
        "markdown": "### Compose Performance Tips\n\n- Use `remember` / `rememberSaveable`\n- Avoid unnecessary recompositions\n- Use `key()` for lists\n- Break into smaller composables\n- Use stable state objects"
      }
]
}


