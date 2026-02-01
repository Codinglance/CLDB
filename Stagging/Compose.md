{
"category": "Android",
"format": "Markdown inside JSON",
"questions": [
{
"id": 1,
"section": "Jetpack Compose Basics",
"question": "What is Jetpack Compose, and how does it differ from the traditional Android View system?",
"difficulty": "Easy",
"tags": [
"compose",
"basics",
"ui"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Jetpack Compose\n\nJetpack Compose is **Android's modern declarative UI toolkit**.\n\n**Differences from traditional Views:**\n- Declarative vs Imperative: Compose describes **what UI should look like**.\n- Less boilerplate: No XML layouts.\n- Reactive: UI updates automatically when state changes.\n- Composables: UI elements are Kotlin functions.\n- Works seamlessly with existing Android components.\n\n```kotlin\n@Composable\nfun Greeting(name: String) {\n    Text(\"Hello, $name\")\n}\n```"
},
{
"id": 2,
"section": "Jetpack Compose Basics",
"question": "Explain the concept of declarative UI in Jetpack Compose.",
"difficulty": "Easy",
"tags": [
"compose",
"ui",
"declarative"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Declarative UI\n\nIn declarative UI, you **describe the UI for a given state** instead of specifying steps to update it.\n- Compose automatically updates UI on state changes.\n\n```kotlin\n@Composable\nfun Greeting(name: String) {\n    Text(text = \"Hello, $name!\")\n}\n```"
},
{
"id": 3,
"section": "Jetpack Compose Basics",
"question": "Declarative UI vs Imperative UI",
"difficulty": "Easy",
"tags": [
"compose",
"ui",
"comparison"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "| Type | Approach | Example |\n|------|---------|---------|\n| Declarative | Describe UI state | Jetpack Compose `Text(\"Hello\")` updates automatically |\n| Imperative | Manual UI updates | Traditional Views: `textView.setText(\"Hello\")` |"
},
{
"id": 4,
"section": "Jetpack Compose Basics",
"question": "What are Composable functions?",
"difficulty": "Easy",
"tags": [
"compose",
"functions",
"basics"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Composable Functions\n\n- Annotated with `@Composable`\n- Can define UI elements or layouts\n- Can call other composables\n\n```kotlin\n@Composable\nfun Greeting(name: String) {\n    Text(text = \"Hello, $name\")\n}\n```"
},
{
"id": 5,
"section": "Jetpack Compose Basics",
"question": "What are the benefits of Jetpack Compose?",
"difficulty": "Easy",
"tags": [
"compose",
"ui",
"benefits"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "- Declarative and reactive UI\n- Less boilerplate, no XML layouts\n- Easier to maintain and test\n- Kotlin-first, fully interoperable\n- Built-in Material Design components\n- Integrates with existing Android Views"
},
{
"id": 6,
"section": "Jetpack Compose Basics",
"question": "Jetpack Compose vs Android View System",
"difficulty": "Medium",
"tags": [
"compose",
"comparison",
"ui"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "| Feature | Compose | View System |\n|---------|--------|------------|\n| UI Approach | Declarative | Imperative |\n| Layout | Composables | XML + Views |\n| State Handling | Automatic recomposition | Manual updates |\n| Boilerplate | Less | More |\n| Interoperability | Works with Views | Views can host Compose via AndroidView |"
},
{
"id": 7,
"section": "@Composable & Lifecycle",
"question": "Explain the role of @Composable in Jetpack Compose.",
"difficulty": "Easy",
"tags": [
"compose",
"lifecycle",
"basics"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### @Composable\n\nMarks a function as composable so it can emit UI elements.\n- Can call other composables\n- Compose tracks them for **recomposition** when state changes."
},
{
"id": 8,
"section": "@Composable & Lifecycle",
"question": "Explain the lifecycle of a Composable.",
"difficulty": "Medium",
"tags": [
"compose",
"lifecycle"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Composable Lifecycle\n\n1. **Composition** → Function executes, UI drawn.\n2. **Recomposition** → Function re-executes when observed state changes.\n3. **Disposal** → Resources released when leaving composition.\n\nManaged automatically by Compose."
},
{
"id": 9,
"section": "@Composable & Lifecycle",
"question": "How do you handle lifecycle events in Compose functions?",
"difficulty": "Medium",
"tags": [
"compose",
"lifecycle",
"effects"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Lifecycle Handling\n\n- `LaunchedEffect` → Run suspend code when key changes\n- `DisposableEffect` → Cleanup resources\n- `SideEffect` → Run after successful composition\n- Observe LifecycleOwner using `LocalLifecycleOwner.current`\n\n```kotlin\nval lifecycleOwner = LocalLifecycleOwner.current\nDisposableEffect(lifecycleOwner) {\n    val observer = LifecycleEventObserver { _, event -> /* handle */ }\n    lifecycleOwner.lifecycle.addObserver(observer)\n    onDispose { lifecycleOwner.lifecycle.removeObserver(observer) }\n}\n```"
},
{
"id": 10,
"section": "State Management & Recomposition",
"question": "What is State in Compose?",
"difficulty": "Easy",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### State\n\nRepresents **data that can change** and triggers recomposition.\n\n```kotlin\nvar count by remember { mutableStateOf(0) }\nText(\"Count: $count\")\n```"
},
{
"id": 11,
"section": "State Management & Recomposition",
"question": "How does state management work in Jetpack Compose, and what are the common state types?",
"difficulty": "Medium",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### State Management\n\n- Compose observes **state objects** (`State<T>`) and **recomposes UI** automatically.\n- Common types:\n  - `mutableStateOf` → Local state\n  - `remember` + `mutableStateOf` → Survive recomposition\n  - `rememberSaveable` → Survive recomposition & config changes\n  - `ViewModel` + `StateFlow` / `LiveData` → App-level state"
},
{
"id": 12,
"section": "State Management & Recomposition",
"question": "What is MutableState and how does recomposition happen?",
"difficulty": "Medium",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### MutableState & Recomposition\n\n- `MutableState<T>` holds value and triggers **recomposition** on change.\n- Compose tracks which composables read the state and only recomposes those.\n\n```kotlin\nvar count by remember { mutableStateOf(0) }\ncount++ // Triggers recomposition for dependent UI\n```"
},
{
"id": 13,
"section": "State Management & Recomposition",
"question": "Stateful composable vs Stateless composable",
"difficulty": "Medium",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Stateful vs Stateless\n\n- **Stateful:** Holds its own state internally.\n- **Stateless:** Receives state via parameters, no internal state.\n\n```kotlin\n@Composable\nfun Counter(count: Int, onIncrement: ()->Unit) { /* stateless */ }\n```"
},
{
"id": 14,
"section": "State Management & Recomposition",
"question": "Difference between Stateless and Stateful composables",
"difficulty": "Medium",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "| Type | Holds State | Recomposition |\n|------|------------|---------------|\n| Stateless | No | Depends on parent |\n| Stateful | Yes | Local changes trigger recomposition |"
},
{
"id": 15,
"section": "State Management & Recomposition",
"question": "What is State Hoisting?",
"difficulty": "Medium",
"tags": [
"compose",
"state",
"pattern"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### State Hoisting\n\n- Moving state **up to parent** so child is stateless.\n- Makes composables reusable and testable.\n\n```kotlin\n@Composable\nfun Parent() {\n    var count by remember { mutableStateOf(0) }\n    Counter(count) { count++ }\n}\n```"
},
{
"id": 16,
"section": "State Management & Recomposition",
"question": "How to retain state across recomposition and configuration changes?",
"difficulty": "Medium",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Retaining State\n\n- **Recomposition:** `remember { mutableStateOf() }`\n- **Configuration change:** `rememberSaveable { mutableStateOf() }`\n\n```kotlin\nvar text by rememberSaveable { mutableStateOf(\"\") }\n```"
},
{
"id": 17,
"section": "State Management & Recomposition",
"question": "What is Recomposition?",
"difficulty": "Easy",
"tags": [
"compose",
"recomposition"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Recomposition\n\nRe-execution of a composable when **observed state changes**.\n\n```kotlin\nvar count by remember { mutableStateOf(0) }\nText(\"Count: $count\") // updates automatically\n```"
},
{
"id": 18,
"section": "State Management & Recomposition",
"question": "How to avoid recomposition of a composable if the state is not changed? (Smart Recomposition)",
"difficulty": "Medium",
"tags": [
"compose",
"recomposition"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Smart Recomposition\n\n- Use **stable types**\n- Use `key()` for lists\n- Make parameters `@Stable`\n- Avoid unnecessary reads inside composables"
},
{
"id": 19,
"section": "State Management & Recomposition",
"question": "Does re-composition of ComposeItem1 affect ComposeItem2? If yes, how?",
"difficulty": "Medium",
"tags": [
"compose",
"recomposition"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Independent Recomposition\n\n- Compose tracks **read state** per composable.\n- Only composables reading changed state are recomposed.\n- ComposeItem2 is **not recomposed** if it doesn't read the changed state."
},
{
"id": 20,
"section": "State Management & Recomposition",
"question": "What are stable types that can skip recomposition?",
"difficulty": "Medium",
"tags": [
"compose",
"recomposition",
"optimization"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Stable Types\n\n- Types annotated with `@Stable` or primitives (`Int`, `String`, `Boolean`) can skip recomposition.\n- Compose treats immutable data as stable, reducing unnecessary recomposition."
},
{
"id": 21,
"section": "Side Effects & Coroutines",
"question": "What are side effects in Compose?",
"difficulty": "Medium",
"tags": [
"compose",
"side-effects",
"coroutines"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Side Effects in Compose\n\nOperations that affect the outside world or are non-reproducible:\n- Logging\n- Networking\n- Database operations\n\nCompose provides APIs to handle them safely:\n- `LaunchedEffect`\n- `DisposableEffect`\n- `SideEffect`"
},
{
"id": 22,
"section": "Side Effects & Coroutines",
"question": "Difference between LaunchedEffect and DisposableEffect",
"difficulty": "Medium",
"tags": [
"compose",
"side-effects",
"coroutines"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### LaunchedEffect vs DisposableEffect\n\n| Effect | Purpose | Runs When |\n|--------|---------|-----------|\n| LaunchedEffect | Launch suspend functions tied to key | When key changes or enters composition |\n| DisposableEffect | Setup/cleanup resources | On enter and exit of composition |\n\n```kotlin\nLaunchedEffect(key) { /* network call */ }\nDisposableEffect(key) {\n  val observer = ...\n  onDispose { /* cleanup */ }\n}\n```"
},
{
"id": 23,
"section": "Side Effects & Coroutines",
"question": "What is rememberCoroutineScope and its use cases?",
"difficulty": "Medium",
"tags": [
"compose",
"coroutines",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### rememberCoroutineScope\n\nProvides a coroutine scope tied to the **composition lifecycle**.\n- Can launch coroutines from event handlers.\n\n```kotlin\nval scope = rememberCoroutineScope()\nButton(onClick = {\n    scope.launch { /* async work */ }\n})\n```"
},
{
"id": 24,
"section": "Side Effects & Coroutines",
"question": "How to launch a coroutine from a composable function (LaunchedEffect)?",
"difficulty": "Medium",
"tags": [
"compose",
"coroutines",
"side-effects"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Launching Coroutine in Composable\n\nUse `LaunchedEffect`:\n```kotlin\nLaunchedEffect(key1 = Unit) {\n    val data = fetchData() // suspend call\n}\n```"
},
{
"id": 25,
"section": "Side Effects & Coroutines",
"question": "How to launch a coroutine from a non-composable function but tied to composition (rememberCoroutineScope)?",
"difficulty": "Medium",
"tags": [
"compose",
"coroutines"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Launch Coroutine from Event Handler\n\nUse `rememberCoroutineScope`:\n```kotlin\nval scope = rememberCoroutineScope()\nfun onButtonClick() {\n    scope.launch { fetchData() }\n}\n```"
},
{
"id": 26,
"section": "Modifier & UI Components",
"question": "What is the role of the Modifier in Jetpack Compose?",
"difficulty": "Easy",
"tags": [
"compose",
"modifier",
"ui"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Modifier\n\n- Configure **layout, drawing, gestures, behavior** of a composable.\n- Can be **chained**.\n\n```kotlin\nText(\"Hello\", modifier = Modifier.padding(16.dp).background(Color.Gray))\n```"
},
{
"id": 27,
"section": "Modifier & UI Components",
"question": "What are Semantics?",
"difficulty": "Medium",
"tags": [
"compose",
"accessibility",
"ui"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Semantics\n\n- Provide **metadata for accessibility and testing**.\n- Compose uses `Modifier.semantics` or built-in modifiers.\n\n```kotlin\nBox(modifier = Modifier.semantics { contentDescription = \"Profile Image\" })\n```"
},
{
"id": 28,
"section": "Modifier & UI Components",
"question": "When to use Icon and Image composable functions?",
"difficulty": "Easy",
"tags": [
"compose",
"ui",
"images"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Icon vs Image\n\n- `Icon` → vector-based, tinted, for buttons, toolbar, standard UI icons\n- `Image` → bitmap, drawable, or custom pictures\n\n```kotlin\nIcon(Icons.Default.Favorite, contentDescription = null)\nImage(painterResource(R.drawable.photo), contentDescription = null)\n```"
},
{
"id": 29,
"section": "Modifier & UI Components",
"question": "When to use Box and Column layout components?",
"difficulty": "Easy",
"tags": [
"compose",
"layout"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### Box vs Column\n\n- `Box` → Stack children on top of each other, useful for overlays\n- `Column` → Arrange children vertically\n\n```kotlin\nBox { Text(\"Overlay\") }\nColumn { Text(\"Item1\") ; Text(\"Item2\") }\n```"
},
{
"id": 30,
"section": "Modifier & UI Components",
"question": "Difference between LazyColumn and RecyclerView?",
"difficulty": "Medium",
"tags": [
"compose",
"layout",
"list"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### LazyColumn vs RecyclerView\n\n- `LazyColumn` → Compose's declarative lazy list, simpler, no adapter needed\n- `RecyclerView` → Traditional imperative list with adapter\n\n```kotlin\nLazyColumn { items(list) { item -> Text(item) } }\n```"
},
{
"id": 31,
"section": "Modifier & UI Components",
"question": "What is AndroidView in Compose?",
"difficulty": "Medium",
"tags": [
"compose",
"interop",
"ui"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### AndroidView\n\nEmbed traditional Android Views inside Compose.\n\n```kotlin\nAndroidView(factory = { context ->\n    TextView(context).apply { text = \"Hello\" }\n})\n```"
},
{
"id": 32,
"section": "Layouts & Custom Views",
"question": "How to create custom layouts in Compose?",
"difficulty": "Medium",
"tags": [
"compose",
"layout",
"custom"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Custom Layouts\n\nUse `Layout` composable:\n```kotlin\nLayout(content = { /* children */ }) { measurables, constraints ->\n    val placeables = measurables.map { it.measure(constraints) }\n    layout(width, height) {\n        placeables.forEach { it.place(x, y) }\n    }\n}\n```"
},
{
"id": 33,
"section": "Layouts & Custom Views",
"question": "Custom views in Compose",
"difficulty": "Medium",
"tags": [
"compose",
"custom",
"ui"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Custom Views\n\n- Compose encourages building UI via **composables** instead of extending Views.\n- For legacy views, use `AndroidView`.\n- Use `Canvas` and `Modifier` to draw custom shapes and interactions."
},
{
"id": 34,
"section": "Layouts & Custom Views",
"question": "Canvas in Compose",
"difficulty": "Medium",
"tags": [
"compose",
"canvas",
"custom-draw"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Canvas\n\nDraw shapes, paths, images directly:\n```kotlin\nCanvas(modifier = Modifier.size(100.dp)) {\n    drawCircle(Color.Red, radius = size.minDimension / 2)\n}\n```"
},
{
"id": 35,
"section": "Layouts & Custom Views",
"question": "Thoughts on flat hierarchy, ConstraintLayout in Compose vs older XML view hierarchy",
"difficulty": "Medium",
"tags": [
"compose",
"layout",
"performance"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Layout Hierarchy\n\n- Compose encourages **flat hierarchies** for performance.\n- `ConstraintLayout` is available in Compose but often not needed due to `Modifier` + `Box`/`Column`/`Row` flexibility.\n- Older XML required deep hierarchies for complex layouts, impacting performance.\n- Compose recomposition + lazy layouts reduces unnecessary view inflation."
},
{
"id": 36,
"section": "Navigation",
"question": "How is navigation handled in Jetpack Compose?",
"difficulty": "Medium",
"tags": [
"compose",
"navigation",
"android"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Navigation in Jetpack Compose\n\n- Jetpack Compose uses **Navigation Compose** library.\n- Define **NavHost** and **NavController**.\n- Navigate between composables using `navController.navigate(\"route\")`.\n- Supports arguments, deep links, and nested navigation.\n\n```kotlin\nval navController = rememberNavController()\nNavHost(navController, startDestination = \"home\") {\n    composable(\"home\") { HomeScreen() }\n    composable(\"details/{id}\") { backStackEntry ->\n        DetailsScreen(id = backStackEntry.arguments?.getString(\"id\"))\n    }\n}\n```"
},
{
"id": 37,
"section": "Integration with Android Frameworks",
"question": "How does Jetpack Compose integrate with existing Android frameworks and libraries?",
"difficulty": "Medium",
"tags": [
"compose",
"integration",
"android"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Integration with Android Frameworks\n\n- Compose works seamlessly with **ViewModel, LiveData, Room, DataStore, Retrofit** etc.\n- Can collect `Flow`/`StateFlow` and update UI reactively.\n- Use `AndroidView` for embedding existing Views.\n\n```kotlin\nval data by viewModel.userFlow.collectAsState()\nText(text = data.name)\n```"
},
{
"id": 38,
"section": "Integration with Android Frameworks",
"question": "Can we use both Jetpack Compose and Android View in a single app?",
"difficulty": "Easy",
"tags": [
"compose",
"interop",
"android"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "30 sec",
"markdown": "### Compose + Android Views\n\n- Yes, apps can mix Compose and Views.\n- Use `ComposeView` in XML layouts to embed Compose.\n- Use `AndroidView` in Compose to embed traditional Views.\n- Useful for incremental migration."
},
{
"id": 39,
"section": "Performance Optimization",
"question": "What are the best practices for performance optimization in Jetpack Compose?",
"difficulty": "Medium",
"tags": [
"compose",
"performance",
"optimization"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Performance Optimization\n\n- Keep **composables small and reusable**\n- Use `remember`/`rememberSaveable` for state\n- Avoid unnecessary recompositions\n- Use `key` for lazy lists\n- Prefer **flat hierarchy**\n- Leverage **derivedStateOf** for expensive calculations\n- Avoid heavy operations in composition directly"
},
{
"id": 40,
"section": "State Utilities",
"question": "Explain derivedStateOf",
"difficulty": "Medium",
"tags": [
"compose",
"state",
"optimization"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### derivedStateOf\n\n- Creates a **state derived from other states**\n- Only recomputes when dependencies change\n\n```kotlin\nval list = remember { mutableStateListOf<Int>() }\nval evenCount by derivedStateOf { list.count { it % 2 == 0 } }\n```"
},
{
"id": 41,
"section": "State Utilities",
"question": "Explain rememberUpdatedState",
"difficulty": "Medium",
"tags": [
"compose",
"state",
"optimization"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### rememberUpdatedState\n\n- Keeps **latest value of a variable** without triggering recomposition\n- Useful in **LaunchedEffect** or callbacks\n\n```kotlin\nval latestOnClick by rememberUpdatedState(onClick)\nLaunchedEffect(Unit) { delay(1000); latestOnClick() }\n```"
},
{
"id": 42,
"section": "State Utilities",
"question": "Difference between remember and rememberSaveable",
"difficulty": "Medium",
"tags": [
"compose",
"state",
"optimization"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### remember vs rememberSaveable\n\n| Feature | remember | rememberSaveable |\n|--------|---------|----------------|\n| Survives recomposition | ✅ | ✅ |\n| Survives configuration changes | ❌ | ✅ |\n| Use case | Temporary UI state | State across rotation |"
},
{
"id": 43,
"section": "State Utilities",
"question": "Difference between remember and LaunchedEffect",
"difficulty": "Medium",
"tags": [
"compose",
"state",
"side-effects"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "45 sec",
"markdown": "### remember vs LaunchedEffect\n\n- `remember` → Stores value across recompositions, does not run suspend functions\n- `LaunchedEffect` → Runs suspend functions tied to composition key\n\n```kotlin\nval count = remember { mutableStateOf(0) }\nLaunchedEffect(count.value) { fetchData() }\n```"
},
{
"id": 44,
"section": "State Utilities",
"question": "What is remember in Compose?",
"difficulty": "Easy",
"tags": [
"compose",
"state"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "30 sec",
"markdown": "### remember\n\n- Stores a value **across recompositions**\n- Useful for state or expensive calculations\n\n```kotlin\nval count = remember { mutableStateOf(0) }\n```"
},
{
"id": 45,
"section": "State Utilities",
"question": "Why and when to use remember {}?",
"difficulty": "Medium",
"tags": [
"compose",
"state",
"optimization"
],
"askedIn": [
"Google",
"Amazon"
],
"expectedReadTime": "1 min",
"markdown": "### Why use remember {}\n\n- Avoid recalculating expensive values on recomposition\n- Store **mutable state** for composables\n- Ensures recomposition does **not reset the state**\n\n```kotlin\nval expensiveValue = remember { computeExpensiveValue() }\n```"
},
    {
      "id": 46,
      "section": "Data Flow",
      "question": "Explain the concept of unidirectional data flow in Jetpack Compose",
      "difficulty": "Medium",
      "tags": ["compose", "state", "architecture"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Unidirectional Data Flow (UDF)\n\n- Data flows **in one direction** from state holder (ViewModel) → UI → events → state holder.\n- UI is a function of **state only**, does not modify it directly.\n- Improves predictability, testability, and avoids side effects.\n\n```kotlin\n// State in ViewModel\nval uiState = MutableStateFlow(UiState())\n\n// UI observes state\nval state by viewModel.uiState.collectAsState()\nText(text = state.message)\n```"
    },
    {
      "id": 47,
      "section": "Data Flow",
      "question": "How to observe Flows and LiveData states in Compose UI",
      "difficulty": "Medium",
      "tags": ["compose", "state", "flow", "livedata"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Observing Flows & LiveData in Compose\n\n- **Flow** → `collectAsState()`\n- **LiveData** → `observeAsState()`\n\n```kotlin\nval data by viewModel.flowData.collectAsState()\nval liveData by viewModel.liveData.observeAsState()\nText(\"Flow: $data, LiveData: $liveData\")\n```"
    },
    {
      "id": 48,
      "section": "Data Flow",
      "question": "How can we handle asynchronous operations in Jetpack Compose?",
      "difficulty": "Medium",
      "tags": ["compose", "async", "coroutines"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Handling Asynchronous Operations\n\n- Use **coroutines** inside `LaunchedEffect`, `rememberCoroutineScope`, or `ViewModel`.\n- Update Compose state when async operation completes.\n\n```kotlin\nLaunchedEffect(Unit) {\n    val result = fetchData() // suspend function\n    state.value = result\n}\n```"
    },
    {
      "id": 49,
      "section": "Data Flow",
      "question": "How can we convert a non-compose state into a Compose state?",
      "difficulty": "Medium",
      "tags": ["compose", "state", "interop"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Converting Non-Compose State\n\n- Use **collectAsState()** for Flow\n- Use **observeAsState()** for LiveData\n- Converts external state into **Compose-reactive state**\n\n```kotlin\nval data by viewModel.flowData.collectAsState()\nval live by viewModel.liveData.observeAsState()\n```"
    },
    {
      "id": 50,
      "section": "Advanced Concepts",
      "question": "Explain CompositionLocal",
      "difficulty": "Medium",
      "tags": ["compose", "advanced", "state"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### CompositionLocal\n\n- Provides **context-like dependency injection** in Compose tree.\n- Values are **readable by all child composables** without explicit passing.\n\n```kotlin\nval LocalSpacing = compositionLocalOf { 8.dp }\nCompositionLocalProvider(LocalSpacing provides 16.dp) {\n    ChildComposable()\n}\n```"
    },
    {
      "id": 51,
      "section": "Advanced Concepts",
      "question": "Explain Jetpack Compose Phases",
      "difficulty": "Medium",
      "tags": ["compose", "advanced", "recomposition"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Jetpack Compose Phases\n\n1. **Composition** → Builds UI tree, executes composable functions.\n2. **Recomposition** → Updates affected UI nodes when state changes.\n3. **Commit** → Applies changes to UI elements.\n4. **Measure/Layout/Draw** → Updates visual representation."
    },
    {
      "id": 52,
      "section": "Advanced Concepts",
      "question": "What is Strong Skipping Mode?",
      "difficulty": "Medium",
      "tags": ["compose", "optimization", "recomposition"],
      "askedIn": ["Google", "Amazon"],
      "expectedReadTime": "1 min",
      "markdown": "### Strong Skipping Mode\n\n- Optimization technique in Compose to **skip recomposition** of composables whose input **did not change**.\n- Reduces unnecessary recompositions and improves performance.\n- Works with **stable types** and proper use of `remember`."
    }
]
}