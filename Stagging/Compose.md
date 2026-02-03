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
      "markdown": "**Imperative UI:**\n- Describes **how to update UI** step-by-step\n- Used in XML + View system\n- Requires manual UI updates\n\n**Declarative UI:**\n- Describes **what UI should display** based on state\n- Used in Jetpack Compose\n- UI updates automatically\n\n**In Short:**\n- Imperative = Manual updates\n- Declarative = State-driven UI"
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
      "markdown": "**Composable functions** are the basic building blocks of UI in **Jetpack Compose**. They are functions marked with the `@Composable` annotation that define how the UI should look.\n\n### Key Features\n- Used to **create UI components**\n- Can be **combined (composed)** to build complex layouts\n- Automatically update UI when state changes\n- Written using Kotlin functions instead of XML\n\n### Example\n```kotlin\n@Composable\nfun Greeting(name: String) {\n    Text(text = \"Hello $name\")\n}\n````"
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
      "markdown": "Jetpack Compose is Android’s modern UI toolkit that lets developers build UI using Kotlin instead of XML, making development faster and simpler.\n\n- \uD83D\uDE80 **Less Code** – Removes XML layouts and reduces boilerplate.\n- ⚡ **Faster Development** – Declarative UI with live previews speeds up development.\n- \uD83C\uDFA8 **Easy Theming** – Built-in Material Design and dark mode support.\n- \uD83E\uDDE9 **Reusable UI** – Composable functions improve modularity and maintainability.\n- \uD83D\uDD04 **Better State Management** – UI updates automatically when data changes.\n- \uD83D\uDCF1 **Improved Performance** – Smart recomposition updates only necessary UI parts.\n- \uD83D\uDD17 **Interoperability** – Works with existing XML Views for gradual migration.\n\n✅ **Conclusion:** Compose simplifies Android UI development with cleaner code, better performance, and faster UI creation.\n"
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
      "markdown": "\n`@Composable` turns a Kotlin function into a UI function that builds and updates UI in Jetpack Compose.\n\n\n#### \uD83E\uDDE9 Defines UI Components  \nUsed to create UI elements like text, buttons, layouts, or screens.\n\n#### \uD83D\uDD04 Enables Declarative UI  \nDescribes **what UI should look like**. UI updates automatically when data changes.\n\n#### \uD83E\uDDE0 Supports Recomposition  \nOnly affected composables are redrawn when state changes, improving performance.\n\n#### \uD83D\uDD17 Allows UI Composition  \nComposable functions can call other composables to build reusable and complex UI.\n"
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
      "markdown": "The lifecycle of a composable defines how it is created, updated, and removed from the UI in Jetpack Compose.\n\n\n#### \uD83C\uDD95 Composition  \nWhen a composable is first called, Compose creates the UI and adds it to the screen.\n\n\n#### \uD83D\uDD04 Recomposition  \nWhen the state used inside a composable changes, Compose re-executes the function and updates only the required UI parts.\n\n\n#### \uD83E\uDDF9 Disposal  \nWhen a composable is no longer needed, it is removed from the UI and its resources are cleared.\n\n#### ⚙\uFE0F State Awareness  \nCompose tracks state changes automatically, ensuring the UI stays updated and efficient.\n"
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
      "markdown": "State in Jetpack Compose represents data that can change and affect the UI. When state changes, Compose automatically updates the UI.\n\n#### \uD83D\uDCE6 Holds UI Data  \nStores values like text input, selection, or visibility.\n\n#### \uD83D\uDD04 Triggers UI Updates  \nState changes automatically recompose and update the UI.\n\n#### \uD83E\uDDE0 Managed with State APIs  \nHandled using tools like `remember` and `mutableStateOf`.\n\n#### ⚙\uFE0F Enables Reactive UI  \nHelps create dynamic UI that responds to user actions and data changes."
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
      "markdown": "State management in Jetpack Compose controls how UI data is stored, updated, and observed. When state changes, Compose automatically recomposes and updates the UI.\n\n---\n\n#### \uD83D\uDD04 How State Management Works  \nCompose observes state values used inside composable functions. When the state changes, only the affected UI is recomposed.\n\n#### \uD83D\uDCE6 Common State Types  \n\n- **`remember`**  \n  Stores state inside a composable and survives recomposition.\n\n- **`mutableStateOf`**  \n  Creates observable state that triggers UI updates when changed.\n\n- **`rememberSaveable`**  \n  Saves state across configuration changes like screen rotation.\n\n- **`State` / `MutableState`**  \n  Wrapper classes that hold and observe state values."
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
      "markdown": "`MutableState` is a state holder in Jetpack Compose that stores a value and notifies Compose when the value changes.\n\n#### \uD83D\uDCE6 What is MutableState?  \nA wrapper around a value that can be observed and updated, usually created using `mutableStateOf`.\n\n#### \uD83D\uDD04 How Recomposition Happens  \nWhen the state value changes, Compose re-executes composables using that state and updates only the affected UI.\n\n#### ⚙\uFE0F Benefit  \nHelps create reactive UI with automatic and efficient updates."
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
      "markdown": "In Jetpack Compose, composables can be **stateful** or **stateless** depending on whether they hold or rely on state.\n\n\n#### \uD83E\uDDE9 Stateful Composable  \n- Holds its own state using `remember` or `mutableStateOf`.  \n- Responsible for updating itself when the state changes.  \n- Example: A text field that manages its input internally.\n\n#### ⚡ Stateless Composable  \n- Does **not** hold state internally.  \n- Receives state and events via parameters.  \n- Relies on parent composables to manage state.  \n- Example: A button that displays a value passed from its parent."
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
      "markdown": "- **Stateful Composable**  \n  - Holds and manages its own state.  \n  - Updates itself when the state changes.  \n  - Less reusable due to internal state.  \n  - Example: A `TextField` managing its input internally.  \n\n- **Stateless Composable**  \n  - Does not hold state; receives state from parent.  \n  - UI updates rely on external state changes.  \n  - Highly reusable and easier to test.  \n  - Example: A `Button` displaying text passed from parent."
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
      "markdown": "\nState Hoisting in Jetpack Compose is moving state **up to a parent** composable, making the child **stateless** and reusable.\n\n#### \uD83D\uDD04 How It Works  \n- Parent holds the state and passes it to the child.  \n- Child emits events to update the parent’s state.\n\n#### \uD83E\uDDE9 Benefits  \n- Makes UI components **reusable and testable**.  \n- Separates **state management** from UI.  \n- Enables **unidirectional data flow**.\n\n\n#### ⚡ Example  \n```kotlin\n@Composable\nfun Parent() {\n    var text by remember { mutableStateOf(\"\") }\n    Child(text = text, onTextChange = { text = it })\n}\n\n@Composable\nfun Child(text: String, onTextChange: (String) -> Unit) {\n    TextField(value = text, onValueChange = onTextChange)\n}\n```"
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
      "markdown": "#### \uD83D\uDD39 Across Recomposition  \n- Use `remember` to keep state during recomposition.  \n```kotlin\nvar count by remember { mutableStateOf(0) }\n````\n\n#### \uD83D\uDD39 Across Configuration Changes\n\n* Use `rememberSaveable` to retain state during recomposition **and** rotations.\n\n```kotlin\nvar count by rememberSaveable { mutableStateOf(0) }\n```\n\n**Key:** `remember` → recomposition only, `rememberSaveable` → recomposition + config changes.\n"
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
      "markdown": "Recomposition in Jetpack Compose is the process where **a composable function is re-executed** to update the UI when the state it depends on changes.\n\n#### \uD83D\uDD04 How It Works  \n- Compose tracks state used in composables.  \n- When the state changes, only the affected composables are recomposed.  \n- Unaffected parts of the UI are not redrawn, improving performance.\n\n#### \uD83E\uDDE9 Benefits  \n- Ensures UI is always **in sync with data**.  \n- Provides **efficient and reactive updates** without manual UI refresh."
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
      "markdown": "To prevent recomposition when state hasn’t changed:\n\n- **`remember`** – Keeps state across recompositions.  \n```kotlin\nval value = remember { computeValue() }\n````\n\n* **`key`** – Recompose only when the key changes.\n\n```kotlin\nkey(user.id) { UserProfile(user) }\n```\n\n* **`derivedStateOf`** – Recompose only if the derived value changes.\n\n```kotlin\nval derivedValue by remember { derivedStateOf { state1 + state2 } }\n```\n\n* **Immutable/Stable Data** – Helps Compose skip recomposition if the value is unchanged.\n"
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
      "markdown": "No, recomposition in Jetpack Compose is **localized**.  \n\n---\n\n#### \uD83D\uDD39 How It Works\n- Compose tracks which state each composable uses.  \n- If `ComposeItem1`’s state changes, only `ComposeItem1` is recomposed.  \n- `ComposeItem2` remains unaffected **if it doesn’t depend on the same state**.  \n\n#### \uD83D\uDD39 Key Point\n- Only composables that **observe changed state** are recomposed.  \n- This makes Compose **efficient** by avoiding unnecessary UI redraws."
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
      "markdown": "Stable types are objects or values that **don’t change unexpectedly**, allowing Compose to skip recomposition when they remain the same.\n\n\n#### \uD83D\uDD39 Examples of Stable Types\n- **Primitive types**: `Int`, `Float`, `Boolean`, `String`  \n- **Immutable collections**: `List`, `Map`, `Set` from Kotlin’s immutable types  \n- **Data classes with `val` properties**  \n- **Objects marked with `@Stable`**  \n- **Functions / Lambdas** that don’t capture changing state  \n\n#### \uD83D\uDD39 Key Point\n- If a composable uses only **stable types**, Compose can avoid recomposing it when unrelated state changes, improving performance.\n"
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
      "markdown": "Side effects in Compose are operations that **interact with the outside world** or cause changes **outside the composable scope**, such as updating state, launching coroutines, or performing I/O.\n\n---\n\n#### \uD83D\uDD39 Examples of Side Effects\n- Showing a `Toast` or `Snackbar`  \n- Navigating to another screen  \n- Writing to a database or shared preferences  \n- Launching coroutines for API calls  \n\n---\n\n#### \uD83D\uDD39 Handling Side Effects\nCompose provides **special APIs** to safely handle side effects:  \n- `LaunchedEffect` – Runs a coroutine tied to the composable lifecycle  \n- `SideEffect` – Runs after every successful recomposition  \n- `DisposableEffect` – Cleans up resources when the composable leaves composition "
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
      "markdown": "- **`LaunchedEffect`**  \n  - Runs a **coroutine** tied to composable lifecycle.  \n  - Used for async tasks (API calls, animations).  \n  - Cancels automatically when key changes or composable leaves.  \n  ```kotlin\n  LaunchedEffect(userId) { fetchUserData(userId) }\n\n* **`DisposableEffect`**\n\n    * Runs **side effects with cleanup** when entering/leaving composition.\n    * Used for resources or listeners.\n\n  ```kotlin\n  DisposableEffect(lifecycleOwner) {\n      val observer = LifecycleEventObserver { _, _ -> }\n      lifecycleOwner.lifecycle.addObserver(observer)\n      onDispose { lifecycleOwner.lifecycle.removeObserver(observer) }\n  }\n  ```"
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
      "markdown": "`rememberCoroutineScope` is a Compose API that provides a **lifecycle-aware CoroutineScope** tied to a composable. It allows launching coroutines from UI events like clicks or gestures.\n\n---\n\n#### \uD83D\uDD39 How It Works\n- Returns a `CoroutineScope` that **cancels automatically** when the composable leaves the composition.\n- Unlike `LaunchedEffect`, it can be used **inside event handlers** (e.g., button clicks).\n\n\n#### \uD83D\uDD39 Use Cases\n- Performing **asynchronous tasks on user interaction**  \n  ```kotlin\n  val scope = rememberCoroutineScope()\n  Button(onClick = { \n      scope.launch { fetchData() } \n  })\n* Animations triggered by events\n* Temporary background work tied to a composable"
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
      "markdown": "`LaunchedEffect` lets you launch a coroutine tied to a composable’s lifecycle. It cancels automatically when the key changes or the composable leaves.\n\n```kotlin\n@Composable\nfun UserScreen(userId: String) {\n    LaunchedEffect(userId) {\n        val userData = fetchUserData(userId) // suspend function\n        // Update UI\n    }\n}\n````\n\n**Use Case:** Initial data loading, animations, or side effects in composables."
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
      "markdown": "`rememberCoroutineScope` provides a **lifecycle-aware CoroutineScope** that can be used in **event handlers or non-composable functions** inside a composable.\n\n#### \uD83D\uDD39 How It Works\n- The scope is tied to the composable’s lifecycle.  \n- Cancels automatically when the composable leaves composition.  \n- Useful for launching coroutines **imperatively** (e.g., on button click).\n\n#### \uD83D\uDD39 Example\n```kotlin\n@Composable\nfun FetchButton() {\n    val scope = rememberCoroutineScope()\n    Button(onClick = {\n        scope.launch {\n            fetchData() // suspend function\n        }\n    }) {\n        Text(\"Fetch Data\")\n    }\n}\n````"
    }
  ]
}
