
## **1. What is Jetpack Compose?**

**Jetpack Compose** is Android’s modern **declarative UI toolkit**.

**Key Points:**

* Allows building UI with **Kotlin code** instead of XML.
* Uses **Composable functions** annotated with `@Composable`.
* Reactive: UI automatically updates when state changes.
* Reduces boilerplate code and improves readability.

---

## **2. What is a Composable function?**

**Composable Function:** A function annotated with `@Composable` that describes UI.

**Syntax:**

```kotlin
@Composable
fun Greeting(name: String) {
    Text(text = "Hello, $name!")
}
```

**Key Points:**

* Can call other composables.
* Can read state and update UI automatically.

---

## **3. What is State in Compose?**

**State:** Represents UI data that can change over time. Compose automatically **recomposes** when state changes.

**Types:**

* `remember` – State stored in memory for recomposition.
* `mutableStateOf` – Holds mutable data.

**Example:**

```kotlin
var count by remember { mutableStateOf(0) }

Button(onClick = { count++ }) {
    Text("Clicked $count times")
}
```

---

## **4. Difference between `remember` and `rememberSaveable`**

| Keyword            | Description                                                                       |
| ------------------ | --------------------------------------------------------------------------------- |
| `remember`         | Stores state during recompositions; lost on config change                         |
| `rememberSaveable` | Stores state across recompositions **and configuration changes** (e.g., rotation) |

**Example:**

```kotlin
var text by rememberSaveable { mutableStateOf("") }
```

---

## **5. What is Recomposition in Compose?**

**Recomposition:** The process of **redrawing parts of UI** when state changes.

**Key Points:**

* Only affected composables are redrawn.
* Efficient compared to traditional View updates.
* Avoid unnecessary recompositions for performance.

---

## **6. Difference between `Modifier` and `LayoutModifier`**

| Type             | Description                                                                   |
| ---------------- | ----------------------------------------------------------------------------- |
| `Modifier`       | General-purpose modifiers applied to UI elements (padding, background, click) |
| `LayoutModifier` | Specifically affects layout measurement and placement                         |

**Example:**

```kotlin
Text(
    "Hello",
    modifier = Modifier.padding(16.dp).background(Color.Gray)
)
```

---

## **7. Difference between Column, Row, and Box**

| Composable | Description                          | Key Points                  |
| ---------- | ------------------------------------ | --------------------------- |
| Column     | Arranges children vertically         | Top-to-bottom layout        |
| Row        | Arranges children horizontally       | Left-to-right layout        |
| Box        | Stacks children on top of each other | Use for overlays, alignment |

**Example:**

```kotlin
Column {
    Text("Hello")
    Text("Compose")
}
```

---

## **8. What is LazyColumn and LazyRow?**

**Lazy Lists:** Efficient scrolling lists in Compose.

**Key Points:**

* Only visible items are composed.
* Equivalent to RecyclerView.
* Supports `items` and `itemsIndexed`.

**Example:**

```kotlin
LazyColumn {
    items(100) { index ->
        Text("Item $index")
    }
}
```

---

## **9. What are Scaffold and Material Components in Compose?**

**Scaffold:** A layout that implements **Material Design structure**, including:

* TopBar
* BottomBar
* FAB (FloatingActionButton)
* Snackbar

**Example:**

```kotlin
Scaffold(
    topBar = { TopAppBar(title = { Text("My App") }) },
    floatingActionButton = { FloatingActionButton(onClick = {}) { Text("+") } }
) {
    Text("Content here")
}
```

**Material Components:** Pre-built composables for **buttons, text fields, cards, chips**, etc.

---

## **10. Difference between `rememberCoroutineScope` and `LaunchedEffect`**

| Concept                  | Description                                                                                      |
| ------------------------ | ------------------------------------------------------------------------------------------------ |
| `rememberCoroutineScope` | Provides a **CoroutineScope tied to Composable**; can launch coroutines on events like clicks    |
| `LaunchedEffect`         | Runs **suspend functions automatically when keys change**; cancels and restarts on recomposition |

**Example:**

```kotlin
val scope = rememberCoroutineScope()
Button(onClick = {
    scope.launch { doSomething() }
}) { Text("Click") }

LaunchedEffect(key1 = count) {
    delay(1000)
    println("Count changed")
}
```

