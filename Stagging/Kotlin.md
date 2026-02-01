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
"markdown": "### val vs var\n\n- `val` → Immutable (cannot be reassigned)\n- `var` → Mutable (can be reassigned)\n\n```kotlin\nval name = \"Aasim\"\nvar age = 25\nage = 26 // allowed\nname = \"Ali\" // error\n```\n\n👉 Prefer `val` for safer code."
},
{
"id": 2,
"section": "Core Kotlin",
"question": "What is the advantage of using const in Kotlin?",
"difficulty": "Easy",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### const in Kotlin\n\n- Compile-time constant.\n- Can be used in annotations and top-level declarations.\n\n```kotlin\nconst val MAX_COUNT = 10\n```\n\n👉 Use `const` for immutable constants that don’t change at runtime."
},
{
"id": 3,
"section": "Core Kotlin",
"question": "When to use lateinit and how to check if it has been initialized?",
"difficulty": "Medium",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### lateinit\n\n- Used for non-null properties initialized later.\n- Check initialization with `::variable.isInitialized`\n\n```kotlin\nlateinit var name: String\nif(::name.isInitialized){ println(name) }\n```"
},
{
"id": 4,
"section": "Core Kotlin",
"question": "How to do lazy initialization of variables in Kotlin?",
"difficulty": "Easy",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### Lazy Initialization\n\n```kotlin\nval name: String by lazy {\n    println(\"Initializing\")\n    \"Aasim\"\n}\n```"
},
{
"id": 5,
"section": "Core Kotlin",
"question": "What is an init block in Kotlin?",
"difficulty": "Easy",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### init Block\n\nExecuted when an instance is created.\n\n```kotlin\nclass User(val name: String){\n  init { println(\"User initialized: $name\") }\n}\n```"
},
{
"id": 6,
"section": "Core Kotlin",
"question": "Explain the difference between == and === in Kotlin.",
"difficulty": "Easy",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### == vs ===\n\n- `==` → Structural equality (value)\n- `===` → Referential equality (memory reference)\n\n```kotlin\nval a = \"A\"\nval b = \"A\"\nprintln(a == b) // true\nprintln(a === b) // may be true or false\n```"
},
{
"id": 7,
"section": "Core Kotlin",
"question": "What are companion objects in Kotlin?",
"difficulty": "Easy",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### Companion Object\n\nActs like static members in Java.\n\n```kotlin\nclass MyClass{\n  companion object{\n    val version = 1\n  }\n}\nprintln(MyClass.version)\n```"
},
{
"id": 8,
"section": "Core Kotlin",
"question": "What is the equivalent of Java static methods in Kotlin?",
"difficulty": "Easy",
"tags": ["basics", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### Kotlin Equivalent of Static Methods\n\n- Use **companion objects**\n- Use **top-level functions** (preferred)\n\n```kotlin\nfun utils() { println(\"Top-level function\") }\nMyClass.Companion.version // for companion object\n```"
},
{
"id": 9,
"section": "Core Kotlin",
"question": "How to create a Singleton class in Kotlin?",
"difficulty": "Medium",
"tags": ["basics", "kotlin", "singleton"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### Singleton in Kotlin\n\n```kotlin\nobject MySingleton {\n  val name = \"Aasim\"\n  fun doWork() {}\n}\nMySingleton.doWork()\n```"
},
{
"id": 10,
"section": "Core Kotlin",
"question": "Explain open, abstract, final, internal, public, and private keywords in Kotlin.",
"difficulty": "Medium",
"tags": ["core", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Kotlin Modifiers\n\n- `open` → can be inherited\n- `abstract` → must be implemented in subclasses\n- `final` → default, cannot be overridden\n- `internal` → visible within module\n- `public` → visible everywhere (default)\n- `private` → visible within class/file\n\n```kotlin\nopen class A{}\nabstract class B{}\nfinal class C{}\n```"
},
{
"id": 11,
"section": "Core Kotlin",
"question": "What is a data class in Kotlin and what methods are auto-generated?",
"difficulty": "Easy",
"tags": ["basics", "kotlin", "data-class"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Data Classes\n\n- Holds data and auto-generates `toString()`, `equals()`, `hashCode()`, `copy()`.\n\n```kotlin\ndata class User(val name: String, val age: Int)\n```"
},
{
"id": 12,
"section": "Advanced Kotlin",
"question": "Explain inline classes (value classes) in Kotlin.",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "inline-class"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Inline (Value) Classes\n\n- Wraps a value without extra object overhead.\n- Must have a single property.\n\n```kotlin\n@JvmInline\nvalue class UserId(val id: Int)\n```"
},
{
"id": 13,
"section": "Advanced Kotlin",
"question": "What is the purpose of inline, noinline, crossinline, and reified keywords?",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "functions"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Inline Function Keywords\n\n- `inline` → inlines function bytecode to reduce overhead\n- `noinline` → prevents specific lambda inlining\n- `crossinline` → prevents non-local returns from lambda\n- `reified` → allows type info at runtime in inline functions\n\n```kotlin\ninline fun <reified T> Gson.fromJson(json: String): T = this.fromJson(json, T::class.java)\n```"
},
{
"id": 14,
"section": "Advanced Kotlin",
"question": "What are higher-order functions and how do you return a function from a function?",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "functions"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Higher-Order Functions\n\n- Functions that take other functions as parameters or return functions.\n\n```kotlin\nfun operation(x: Int): (Int) -> Int = { y -> x + y }\nval add5 = operation(5)\nprintln(add5(10)) // 15\n```"
},
{
"id": 15,
"section": "Advanced Kotlin",
"question": "What are lambda expressions in Kotlin?",
"difficulty": "Easy",
"tags": ["advanced", "kotlin", "lambda"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Lambda Expressions\n\nAnonymous functions defined as expressions.\n\n```kotlin\nval sum: (Int, Int) -> Int = { a, b -> a + b }\nprintln(sum(2,3)) // 5\n```"
},
{
"id": 16,
"section": "Advanced Kotlin",
"question": "What are extension functions and how do you use them?",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "extension"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Extension Functions\n\nAdd functions to existing classes.\n\n```kotlin\nfun String.removeSpaces() = this.replace(\" \", \"\")\nprintln(\"A B C\".removeSpaces()) // ABC\n```"
},
{
"id": 17,
"section": "Advanced Kotlin",
"question": "Explain scope functions (let, apply, run, with, also) and their use-cases.",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "scope-functions"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Scope Functions\n\n- `let` → nullable checks, transformation\n- `run` → combine object initialization & return\n- `with` → access object without extension\n- `also` → side-effects, returns object\n- `apply` → object config, returns object\n\n```kotlin\nval user = User().apply { name = \"Aasim\" }.also { println(it) }\n```"
},
{
"id": 18,
"section": "Advanced Kotlin",
"question": "Difference between apply and with, and when to use each.",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "scope-functions"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### apply vs with\n\n- `apply` → extension, returns object, use for initialization/config\n- `with` → regular function, returns lambda result, use for actions on object\n\n```kotlin\nval user = User().apply { name = \"Aasim\" }\nval length = with(user) { name.length }\n```"
},
{
"id": 19,
"section": "Advanced Kotlin",
"question": "What are labels in Kotlin and how do you use them?",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "labels"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Labels\n\nUsed with `break`, `continue`, and lambdas for nested loops/functions.\n\n```kotlin\nloop@ for(i in 1..5){\n  for(j in 1..5){\n    if(j==3) break@loop\n  }\n}\n```"
},
{
"id": 20,
"section": "Advanced Kotlin",
"question": "Explain sealed classes and common use-cases in Android.",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "sealed"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Sealed Classes\n\n- Restricted class hierarchies, allows exhaustive `when` checks.\n- Common in Android for state handling.\n\n```kotlin\nsealed class UiState {\n  object Loading : UiState()\n  data class Success(val data: List<String>) : UiState()\n  data class Error(val error: Throwable) : UiState()\n}\n```"
},
{
"id": 21,
"section": "Core Kotlin",
"question": "Difference between List and Array types in Kotlin.",
"difficulty": "Easy",
"tags": ["basics", "kotlin", "collections"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### List vs Array\n\n- `Array` → fixed size, mutable\n- `List` → read-only by default, `MutableList` for mutable\n\n```kotlin\nval arr = arrayOf(1,2,3)\nval list = listOf(1,2,3)\nval mutableList = mutableListOf(1,2,3)\n```"
},
{
"id": 22,
"section": "Core Kotlin",
"question": "How to remove duplicates from an array or collection in Kotlin?",
"difficulty": "Easy",
"tags": ["collections", "kotlin"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "### Remove Duplicates\n\n```kotlin\nval list = listOf(1,2,2,3,3,3)\nval distinctList = list.distinct()\nprintln(distinctList) // [1,2,3]\n```"
},
{
"id": 23,
"section": "Advanced Kotlin",
"question": "Explain Delegates (lazy, observable, vetoable) in Kotlin.",
"difficulty": "Medium",
"tags": ["advanced", "kotlin", "delegates"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Delegates in Kotlin\n\n- `lazy` → initialized once on first access\n- `observable` → notifies on change\n- `vetoable` → allows or rejects changes\n\n```kotlin\nval lazyValue: String by lazy { \"Hello\" }\nvar observed: Int by Delegates.observable(0){ prop, old, new -> println(\"$old -> $new\") }\nvar vetoed: Int by Delegates.vetoable(0){ _, _, new -> new >= 0 }\n```"
},
    {
      "id": 1,
      "section": "Basics",
      "question": "What are coroutines in Kotlin?",
      "difficulty": "Easy",
      "tags": ["coroutines", "async", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Coroutines in Kotlin\n\n- Lightweight threads for asynchronous programming.\n- Non-blocking, can suspend and resume without blocking a thread.\n\n```kotlin\nGlobalScope.launch {\n    delay(1000)\n    println(\"Hello from coroutine\")\n}\n```"
    },
    {
      "id": 2,
      "section": "Basics",
      "question": "Difference between suspending and blocking functions.",
      "difficulty": "Medium",
      "tags": ["coroutines", "async"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Suspending vs Blocking\n\n- **Suspending** → `suspend` function, non-blocking, can be paused.\n- **Blocking** → stops the thread until completion.\n\n```kotlin\nsuspend fun fetchData() { delay(1000) } // suspend\nThread.sleep(1000) // blocking\n```"
    },
    {
      "id": 3,
      "section": "Basics",
      "question": "Difference between launch and async.",
      "difficulty": "Medium",
      "tags": ["coroutines", "async", "launch"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### launch vs async\n\n- `launch` → returns **Job**, used for fire-and-forget.\n- `async` → returns **Deferred**, used for returning a result.\n\n```kotlin\nval job = launch { println(\"Job\") }\nval deferred = async { 42 }\nval result = deferred.await()\n```"
    },
    {
      "id": 4,
      "section": "Dispatchers",
      "question": "Explain Coroutine Dispatchers (Dispatchers.Main, IO, Default, Unconfined).",
      "difficulty": "Medium",
      "tags": ["dispatchers", "coroutines"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Coroutine Dispatchers\n\n- `Dispatchers.Main` → UI thread\n- `Dispatchers.IO` → for IO tasks (network, db)\n- `Dispatchers.Default` → CPU-intensive tasks\n- `Dispatchers.Unconfined` → starts in caller thread, resumes where suspended\n\n```kotlin\nlaunch(Dispatchers.IO){ fetchData() }\n```"
    },
    {
      "id": 5,
      "section": "Scopes",
      "question": "Difference between coroutineScope and supervisorScope.",
      "difficulty": "Medium",
      "tags": ["coroutines", "scope"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### coroutineScope vs supervisorScope\n\n- `coroutineScope` → cancels all child coroutines if one fails.\n- `supervisorScope` → child failure does **not** cancel siblings.\n\n```kotlin\nsupervisorScope {\n  launch { /* child */ }\n}\n```"
    },
    {
      "id": 6,
      "section": "Basics",
      "question": "Explain withContext vs async-await in Kotlin.",
      "difficulty": "Medium",
      "tags": ["coroutines", "async", "context"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### withContext vs async-await\n\n- `withContext` → switch dispatcher, returns result, suspends\n- `async-await` → runs concurrently, returns Deferred, then `await()`\n\n```kotlin\nval result = withContext(Dispatchers.IO){ fetchData() }\nval deferred = async { fetchData() }\nval r = deferred.await()\n```"
    },
    {
      "id": 7,
      "section": "Basics",
      "question": "What is CoroutineContext in Kotlin?",
      "difficulty": "Medium",
      "tags": ["coroutines", "context"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### CoroutineContext\n\n- Carries information like dispatcher, job, name.\n- Can combine elements using `+`\n\n```kotlin\nval context = Dispatchers.IO + Job()\nlaunch(context){ /* work */ }\n```"
    },
    {
      "id": 8,
      "section": "Interoperability",
      "question": "How to convert a callback-based API into coroutines.",
      "difficulty": "Medium",
      "tags": ["coroutines", "callback"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Callback to Coroutine\n\nUse `suspendCoroutine`.\n\n```kotlin\nsuspend fun fetchData(): String = suspendCoroutine { cont ->\n  api.getData { result -> cont.resume(result) }\n}\n```"
    },
    {
      "id": 9,
      "section": "Parallelism",
      "question": "How to run parallel multiple network calls using coroutines.",
      "difficulty": "Medium",
      "tags": ["coroutines", "parallel", "network"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Parallel Network Calls\n\n```kotlin\nval result1 = async { fetchData1() }\nval result2 = async { fetchData2() }\nval combined = awaitAll(result1, result2)\n```"
    },
    {
      "id": 10,
      "section": "Database",
      "question": "Room database integration with coroutines.",
      "difficulty": "Medium",
      "tags": ["coroutines", "room", "database"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Room + Coroutines\n\n- DAO methods marked with `suspend`\n- Call them in coroutines or ViewModelScope\n\n```kotlin\n@Dao\ninterface UserDao {\n  @Insert suspend fun insert(user: User)\n  @Query(\"SELECT * FROM User\") suspend fun getAll(): List<User>\n}\nviewModelScope.launch { userDao.insert(user) }\n```"
    },
    {
      "id": 11,
      "section": "Testing",
      "question": "How to write unit tests for ViewModel using coroutines and LiveData.",
      "difficulty": "Medium",
      "tags": ["testing", "coroutines", "viewmodel"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Unit Testing ViewModel + Coroutines\n\n- Use `runTest` from `kotlinx-coroutines-test`\n- Use `InstantTaskExecutorRule` for LiveData\n\n```kotlin\n@get:Rule val rule = InstantTaskExecutorRule()\n\n@Test\nfun testFetchData() = runTest {\n    viewModel.fetchData()\n    assertEquals(expected, viewModel.data.getOrAwaitValue())\n}\n```"
    },
    {
      "id": 12,
      "section": "Concurrency",
      "question": "Difference between Job, SupervisorJob, and cancellation.",
      "difficulty": "Medium",
      "tags": ["coroutines", "job", "supervisorjob"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Job vs SupervisorJob\n\n- `Job` → cancels all children if parent is cancelled\n- `SupervisorJob` → child failure does not cancel siblings\n- Cancellation propagates to children by default\n\n```kotlin\nval job = Job()\nval supervisor = SupervisorJob()\n```"
    },
    {
      "id": 13,
      "section": "Concurrency",
      "question": "What happens if an exception is thrown inside an async coroutine, but await() is never called?",
      "difficulty": "Medium",
      "tags": ["coroutines", "async"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Async Exception without await\n\n- Exception is **ignored** until `await()` is called.\n- If `await()` never called, exception is **lost** but logged if parent is `SupervisorJob`."
    },
    {
      "id": 14,
      "section": "Concurrency",
      "question": "Explain structured concurrency in Kotlin.",
      "difficulty": "Medium",
      "tags": ["coroutines", "concurrency"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Structured Concurrency\n\n- All coroutines launched in a scope are **tied to the scope**.\n- Cancelling scope cancels all child coroutines.\n- Ensures predictable cancellation and error propagation.\n\n```kotlin\ncoroutineScope {\n  launch { doWork() }\n}\n```"
    },
    {
      "id": 15,
      "section": "Basics",
      "question": "Difference between Thread.sleep() and delay() in coroutines.",
      "difficulty": "Easy",
      "tags": ["coroutines", "delay"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "### Thread.sleep() vs delay()\n\n- `Thread.sleep()` → blocks thread\n- `delay()` → suspends coroutine, non-blocking\n\n```kotlin\nThread.sleep(1000) // blocks thread\ndelay(1000) // suspends coroutine\n```"
    },
    {
      "id": 16,
      "section": "Basics",
      "question": "Using yield in coroutines – what is its purpose?",
      "difficulty": "Medium",
      "tags": ["coroutines", "yield"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "### yield in Coroutines\n\n- Suspends current coroutine to give other coroutines chance to run.\n- Cooperative multitasking.\n\n```kotlin\nlaunch {\n  for(i in 1..5){\n    println(i)\n    yield()\n  }\n}\n```"
    },
    {
      "id": 17,
      "section": "Advanced",
      "question": "How to implement debounce using coroutines.",
      "difficulty": "Medium",
      "tags": ["coroutines", "debounce", "flow"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Debounce in Coroutines\n\n- Use **Flow** with `debounce()` operator for delayed emission.\n\n```kotlin\nflowOf(1,2,3)\n  .debounce(300)\n  .collect { println(it) }\n```"
    },
    {
      "id": 18,
      "section": "Advanced",
      "question": "How do you combine multiple coroutine results using async and awaitAll.",
      "difficulty": "Medium",
      "tags": ["coroutines", "async", "awaitAll"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Combine Multiple Coroutine Results\n\n```kotlin\nval results = awaitAll(\n    async { fetchData1() },\n    async { fetchData2() }\n)\n```"
    },
    {
      "id": 19,
      "section": "Advanced",
      "question": "Explain timeouts in coroutines.",
      "difficulty": "Medium",
      "tags": ["coroutines", "timeout"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Timeouts in Coroutines\n\n- Use `withTimeout` or `withTimeoutOrNull`\n\n```kotlin\nval result = withTimeout(1000){ fetchData() } // throws TimeoutCancellationException\nval safeResult = withTimeoutOrNull(1000){ fetchData() } // returns null\n```"
    },
    {
      "id": 1,
      "section": "Kotlin Flow",
      "question": "Explain Flow builder, operators, and collector.",
      "difficulty": "Medium",
      "tags": ["flow", "coroutines"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Kotlin Flow Overview\n\n- **Flow Builder** → `flow { emit(...) }`, `flowOf()`, `asFlow()`\n- **Operators** → Transform or filter data (`map`, `filter`, `flatMapConcat`)\n- **Collector** → Terminal operation to collect values (`collect { }`)\n\n```kotlin\nflowOf(1,2,3)\n  .map { it * 2 }\n  .collect { println(it) }\n```"
    },
    {
      "id": 2,
      "section": "Kotlin Flow",
      "question": "Difference between flowOn, map, filter, zip, flatMapConcat, flatMapMerge, flatMapLatest.",
      "difficulty": "Medium",
      "tags": ["flow", "operators"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Kotlin Flow Operators\n\n- `flowOn` → changes dispatcher of upstream flow\n- `map` → transforms values\n- `filter` → filters values\n- `zip` → combines two flows\n- `flatMapConcat` → sequentially flatten inner flows\n- `flatMapMerge` → concurrently flatten inner flows\n- `flatMapLatest` → cancels previous inner flow on new emission\n\n```kotlin\nflowOf(1,2,3).map { it*2 }.filter { it>2 }\n```"
    },
    {
      "id": 3,
      "section": "Kotlin Flow",
      "question": "Difference between terminal operators and intermediate operators.",
      "difficulty": "Medium",
      "tags": ["flow", "operators"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Operators in Flow\n\n- **Intermediate operators** → transform flow (`map`, `filter`), lazy, return Flow\n- **Terminal operators** → trigger execution (`collect`, `toList`), return final result"
    },
    {
      "id": 4,
      "section": "Kotlin Flow",
      "question": "Cold Flow vs Hot Flow.",
      "difficulty": "Medium",
      "tags": ["flow"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Cold vs Hot Flow\n\n- **Cold Flow** → emits values on collection, each collector gets new emissions\n- **Hot Flow** → emits values even without collectors, shared among multiple collectors\n\n```kotlin\nval cold = flow { emit(System.currentTimeMillis()) }\nval hot = MutableSharedFlow<Long>()\n```"
    },
    {
      "id": 5,
      "section": "Kotlin Flow",
      "question": "Difference between StateFlow, SharedFlow, callbackFlow, and channelFlow.",
      "difficulty": "Medium",
      "tags": ["flow", "stateflow", "sharedflow"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### StateFlow vs SharedFlow vs callbackFlow vs channelFlow\n\n- `StateFlow` → holds current value, always emits last value\n- `SharedFlow` → hot flow, configurable replay, no initial value required\n- `callbackFlow` → wrap callback APIs into flow\n- `channelFlow` → concurrent emission inside a flow"
    },
    {
      "id": 6,
      "section": "Kotlin Flow",
      "question": "Difference between collect and collectLatest.",
      "difficulty": "Medium",
      "tags": ["flow", "collect"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "### collect vs collectLatest\n\n- `collect` → processes every emission\n- `collectLatest` → cancels previous collector if new value emitted\n\n```kotlin\nflowOf(1,2,3).collectLatest { println(it) }\n```"
    },
    {
      "id": 7,
      "section": "Kotlin Flow",
      "question": "What is stateIn vs shareIn in Kotlin Flow.",
      "difficulty": "Medium",
      "tags": ["flow", "stateflow", "sharedflow"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### stateIn vs shareIn\n\n- `stateIn` → converts Flow to StateFlow, keeps latest value\n- `shareIn` → converts Flow to SharedFlow, hot and shared among collectors\n\n```kotlin\nval stateFlow = flowOf(1,2).stateIn(scope)\nval sharedFlow = flowOf(1,2).shareIn(scope, SharingStarted.Lazily)\n```"
    },
    {
      "id": 8,
      "section": "Kotlin Flow",
      "question": "How to handle exceptions in Flows.",
      "difficulty": "Medium",
      "tags": ["flow", "error-handling"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Exception Handling in Flow\n\n- Use `catch` operator for exceptions\n\n```kotlin\nflow { emit(1/0) }\n  .catch { e -> emit(-1) }\n  .collect { println(it) }\n```"
    },
    {
      "id": 9,
      "section": "Kotlin DSL & Advanced",
      "question": "What is a reified type parameter and when would you use it?",
      "difficulty": "Medium",
      "tags": ["kotlin", "reified", "generics"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Reified Type Parameter\n\n- Allows access to **type info at runtime** for generic functions.\n- Only works with `inline` functions.\n\n```kotlin\ninline fun <reified T> printType() { println(T::class) }\nprintType<String>()\n```"
    },
    {
      "id": 10,
      "section": "Kotlin DSL & Advanced",
      "question": "Explain inline class and its memory/performance benefits.",
      "difficulty": "Medium",
      "tags": ["kotlin", "inline", "value-class"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Inline (Value) Classes\n\n- Wrap a single value, no runtime overhead\n- Compile-time optimization\n\n```kotlin\n@JvmInline value class UserId(val id: Int)\n```"
    },
    {
      "id": 11,
      "section": "Kotlin DSL & Advanced",
      "question": "What are CompositionLocal and context receivers?",
      "difficulty": "Medium",
      "tags": ["compose", "contextlocal", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### CompositionLocal & Context Receivers\n\n- `CompositionLocal` → pass dependencies down Compose tree\n- `context receivers` → provide implicit context for functions\n\n```kotlin\nval LocalTheme = compositionLocalOf { defaultTheme }\n```"
    },
    {
      "id": 12,
      "section": "Kotlin DSL & Advanced",
      "question": "How does Kotlin Multiplatform work?",
      "difficulty": "Medium",
      "tags": ["kotlin", "multiplatform"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Kotlin Multiplatform\n\n- Share common code (Kotlin/JVM/JS/Native)\n- Use `expect/actual` to implement platform-specific code\n\n```kotlin\nexpect fun platformName(): String\nactual fun platformName(): String = \"Android\"\n```"
    },
    {
      "id": 13,
      "section": "Kotlin DSL & Advanced",
      "question": "How do Kotlin coroutines integrate with Android lifecycle components?",
      "difficulty": "Medium",
      "tags": ["coroutines", "lifecycle", "android"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Coroutines + Android Lifecycle\n\n- Use `lifecycleScope` and `viewLifecycleOwner.lifecycleScope`\n- Auto-cancels when lifecycle is destroyed\n\n```kotlin\nlifecycleScope.launch { fetchData() }\n```"
    },
    {
      "id": 14,
      "section": "Kotlin DSL & Advanced",
      "question": "How to implement custom DSLs in Kotlin?",
      "difficulty": "Medium",
      "tags": ["kotlin", "dsl"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Custom DSL\n\n- Use **extension functions**, lambda with receiver\n\n```kotlin\nfun html(block: Html.() -> Unit): Html { val h = Html(); h.block(); return h }\n```"
    },
    {
      "id": 15,
      "section": "Kotlin DSL & Advanced",
      "question": "How to create type-safe builders using Kotlin DSL.",
      "difficulty": "Medium",
      "tags": ["kotlin", "dsl", "builder"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Type-safe Builder\n\n- Leverage lambdas with receiver to ensure proper structure\n\n```kotlin\nfun table(block: Table.() -> Unit): Table { val t = Table(); t.block(); return t }\n```"
    },
    {
      "id": 16,
      "section": "Kotlin DSL & Advanced",
      "question": "Explain the differences between Kotlin reflection (KClass) and Java reflection.",
      "difficulty": "Medium",
      "tags": ["kotlin", "reflection"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Kotlin vs Java Reflection\n\n- `KClass` → Kotlin class reference, type-safe\n- Java reflection → `Class<?>`, less type-safe, runtime only\n\n```kotlin\nval kClass = String::class\nval javaClass = String::class.java\n```"
    },
    {
      "id": 17,
      "section": "Kotlin DSL & Advanced",
      "question": "How do Kotlin contracts help the compiler optimize your code?",
      "difficulty": "Medium",
      "tags": ["kotlin", "contracts"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Kotlin Contracts\n\n- Allow compiler to understand **effects of functions**\n- Can optimize smart-cast, null-safety\n\n```kotlin\n@ExperimentalContracts\nfun requireNonNull(value: Any?) { contract { returns() implies (value != null) } }\n```"
    },
    {
      "id": 18,
      "section": "Kotlin DSL & Advanced",
      "question": "How to use expect and actual in Kotlin Multiplatform projects.",
      "difficulty": "Medium",
      "tags": ["kotlin", "multiplatform", "expect-actual"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Expect/Actual\n\n- Define common API with `expect`\n- Platform-specific implementation with `actual`\n\n```kotlin\nexpect fun getPlatformName(): String\nactual fun getPlatformName(): String = \"Android\"\n```"
    },
    {
      "id": 1,
      "section": "Performance & Best Practices",
      "question": "When to use const val vs val.",
      "difficulty": "Medium",
      "tags": ["kotlin", "performance"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "30 sec",
      "markdown": "### const val vs val\n\n- `const val` → compile-time constant, top-level or in object, cannot be computed at runtime\n- `val` → read-only runtime value, can be computed\n\n```kotlin\nconst val MAX_COUNT = 100\nval currentTime = System.currentTimeMillis()\n```"
    },
    {
      "id": 2,
      "section": "Performance & Best Practices",
      "question": "When to use lateinit vs lazy.",
      "difficulty": "Medium",
      "tags": ["kotlin", "initialization"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### lateinit vs lazy\n\n- `lateinit var` → initialize later for non-null vars, must be var, only for objects\n- `val lazy` → initialized on first access, thread-safe by default\n\n```kotlin\nlateinit var repo: UserRepository\nval db by lazy { Database.getInstance() }\n```"
    },
    {
      "id": 3,
      "section": "Performance & Best Practices",
      "question": "How to avoid unnecessary object allocations in Kotlin.",
      "difficulty": "Medium",
      "tags": ["kotlin", "optimization"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Avoiding Unnecessary Object Allocations\n\n- Prefer `val` over `var` for immutability\n- Use inline classes for lightweight wrappers\n- Reuse objects instead of creating new instances repeatedly\n- Use sequences or lazy operations for large collections\n\n```kotlin\nval list = (1..1000).asSequence().map { it*2 }.toList()\n```"
    },
    {
      "id": 4,
      "section": "Performance & Best Practices",
      "question": "Best practices for working with Flow and StateFlow in large apps.",
      "difficulty": "Medium",
      "tags": ["flow", "stateflow", "best-practices"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Flow & StateFlow Best Practices\n\n- Keep flows cold until collection\n- Use `stateIn` or `shareIn` for shared hot flows\n- Avoid unnecessary `map`/`filter` chains that recompute\n- Combine Flows with `combine` or `zip` carefully\n- Use `collectLatest` when only latest value matters"
    },
    {
      "id": 5,
      "section": "Performance & Best Practices",
      "question": "How to prevent recomposition issues in Compose using stable types.",
      "difficulty": "Medium",
      "tags": ["compose", "recomposition", "performance"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Prevent Recomposition in Compose\n\n- Use `remember` for state retention\n- Use `rememberUpdatedState` for lambdas\n- Prefer **immutable and stable types**\n- Break UI into smaller composables\n- Annotate custom types with `@Stable` when possible"
    },
    {
      "id": 6,
      "section": "Interoperability & Android Specific",
      "question": "How to use Kotlin coroutines with Retrofit.",
      "difficulty": "Medium",
      "tags": ["coroutines", "retrofit", "android"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Retrofit + Coroutines\n\n- Define service functions with `suspend`\n- Call them inside `viewModelScope.launch`\n\n```kotlin\ninterface ApiService {\n    @GET(\"users\")\n    suspend fun getUsers(): List<User>\n}\n\nviewModelScope.launch {\n    val users = api.getUsers()\n}\n```"
    },
    {
      "id": 7,
      "section": "Interoperability & Android Specific",
      "question": "How to integrate Kotlin coroutines with Room database.",
      "difficulty": "Medium",
      "tags": ["coroutines", "room", "android"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Room + Coroutines\n\n- DAO functions marked `suspend` or returning Flow\n- Use coroutines for async database operations\n\n```kotlin\n@Dao\ninterface UserDao {\n    @Query(\"SELECT * FROM user\")\n    fun getAllUsers(): Flow<List<User>>\n\n    @Insert\n    suspend fun insert(user: User)\n}\n\nviewModelScope.launch { userDao.insert(newUser) }\n```"
    },
    {
      "id": 8,
      "section": "Interoperability & Android Specific",
      "question": "How to write idiomatic Kotlin for Android MVVM architecture.",
      "difficulty": "Medium",
      "tags": ["mvvm", "android", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Idiomatic Kotlin in MVVM\n\n- Use `viewModelScope` for async operations\n- Expose immutable `StateFlow` or `LiveData` from ViewModel\n- Use data classes for state representation\n- Leverage extension functions to reduce boilerplate\n\n```kotlin\nval users: StateFlow<List<User>> get() = _users\n```"
    },
    {
      "id": 9,
      "section": "Interoperability & Android Specific",
      "question": "How to combine LiveData and Flow in a Compose project.",
      "difficulty": "Medium",
      "tags": ["compose", "flow", "livedata"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### LiveData + Flow in Compose\n\n- Convert LiveData to Flow using `asFlow()`\n- Collect Flow in Compose using `collectAsState()`\n\n```kotlin\nval liveDataFlow = liveData.asFlow()\nval state by liveDataFlow.collectAsState(initial = emptyList())\n```"
    },
    {
      "id": 10,
      "section": "Interoperability & Android Specific",
      "question": "How to write efficient, type-safe Android View binding using Kotlin.",
      "difficulty": "Medium",
      "tags": ["viewbinding", "android", "kotlin"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "45 sec",
      "markdown": "### Efficient View Binding in Kotlin\n\n- Use ViewBinding for type-safe access to views\n- Avoid `findViewById`\n- Use `by lazy` or `lazy` delegated properties for binding in fragments\n\n```kotlin\nprivate var _binding: FragmentMainBinding? = null\nprivate val binding get() = _binding!!\n```\n- Initialize in `onCreateView` and clear in `onDestroyView`"
    }

]
}
