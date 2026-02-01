{
"category": "Compose",
"format": "Markdown inside JSON",
"questions": [
{
"id": 1,
"section": "Jetpack Compose Basics",
"question": "What is Jetpack Compose?",
"difficulty": "Easy",
"tags": ["compose", "ui", "basics"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Jetpack Compose\n\nJetpack Compose is Android’s **modern declarative UI toolkit**.\n\n**Key Points:**\n- Build UI using **Kotlin code** instead of XML\n- Uses `@Composable` functions\n- Reactive UI (auto updates on state change)\n- Less boilerplate, better readability"
},
{
"id": 2,
"section": "Jetpack Compose Basics",
"question": "What is a Composable function?",
"difficulty": "Easy",
"tags": ["compose", "composable"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Composable Function\n\nA function annotated with `@Composable` that describes UI.\n\n```kotlin\n@Composable\nfun Greeting(name: String) {\n    Text(text = \"Hello, $name!\")\n}\n```\n\n**Key Points:**\n- Can call other composables\n- Automatically reacts to state changes"
},
{
"id": 3,
"section": "State Management",
"question": "What is State in Jetpack Compose?",
"difficulty": "Easy",
"tags": ["state", "compose"],
"askedIn": ["Amazon"],
"expectedReadTime": "1 min",
"markdown": "### State in Compose\n\nState represents UI data that can change over time. Compose **recomposes UI** when state changes.\n\n**Types:**\n- `remember`\n- `mutableStateOf`\n\n```kotlin\nvar count by remember { mutableStateOf(0) }\n\nButton(onClick = { count++ }) {\n    Text(\"Clicked $count times\")\n}\n```"
},
{
"id": 4,
"section": "State Management",
"question": "Difference between remember and rememberSaveable",
"difficulty": "Easy",
"tags": ["state", "remember"],
"askedIn": ["Google"],
"expectedReadTime": "45 sec",
"markdown": "### remember vs rememberSaveable\n\n| Keyword | Description |\n|-------|-------------|\n| remember | Survives recomposition only |\n| rememberSaveable | Survives recomposition + config changes |\n\n```kotlin\nvar text by rememberSaveable { mutableStateOf(\"\") }\n```"
},
{
"id": 5,
"section": "Compose Internals",
"question": "What is Recomposition in Compose?",
"difficulty": "Medium",
"tags": ["recomposition", "performance"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Recomposition\n\nRecomposition is the process of **redrawing affected UI** when state changes.\n\n**Key Points:**\n- Only affected composables redraw\n- More efficient than Views\n- Avoid unnecessary recompositions"
},
{
"id": 6,
"section": "Modifiers & Layout",
"question": "Difference between Modifier and LayoutModifier",
"difficulty": "Medium",
"tags": ["modifier", "layout"],
"askedIn": ["Google"],
"expectedReadTime": "1 min",
"markdown": "### Modifier vs LayoutModifier\n\n| Type | Description |\n|----|-------------|\n| Modifier | Styling & interaction (padding, click, bg) |\n| LayoutModifier | Affects measurement & placement |\n\n```kotlin\nText(\n  \"Hello\",\n  modifier = Modifier.padding(16.dp).background(Color.Gray)\n)\n```"
},
{
"id": 7,
"section": "Layouts",
"question": "Difference between Column, Row, and Box",
"difficulty": "Easy",
"tags": ["layout", "compose"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Column vs Row vs Box\n\n| Composable | Purpose |\n|----------|---------|\n| Column | Vertical layout |\n| Row | Horizontal layout |\n| Box | Stack / overlay |\n\n```kotlin\nColumn {\n  Text(\"Hello\")\n  Text(\"Compose\")\n}\n```"
},
{
"id": 8,
"section": "Lazy Components",
"question": "What is LazyColumn and LazyRow?",
"difficulty": "Easy",
"tags": ["lazycolumn", "recyclerview"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### LazyColumn & LazyRow\n\nLazy lists are **efficient scrolling components**.\n\n**Key Points:**\n- Only visible items are composed\n- Replacement for RecyclerView\n\n```kotlin\nLazyColumn {\n  items(100) { index ->\n    Text(\"Item $index\")\n  }\n}\n```"
},
{
"id": 9,
"section": "Material Design",
"question": "What are Scaffold and Material Components?",
"difficulty": "Easy",
"tags": ["scaffold", "material"],
"askedIn": ["Google"],
"expectedReadTime": "1 min",
"markdown": "### Scaffold & Material Components\n\n**Scaffold** provides Material structure:\n- TopBar\n- BottomBar\n- FAB\n- Snackbar\n\n```kotlin\nScaffold(\n  topBar = { TopAppBar(title = { Text(\"My App\") }) },\n  floatingActionButton = {\n    FloatingActionButton(onClick = {}) { Text(\"+\") }\n  }\n) {\n  Text(\"Content here\")\n}\n```"
},
{
"id": 10,
"section": "Side Effects & Coroutines",
"question": "Difference between rememberCoroutineScope and LaunchedEffect",
"difficulty": "Medium",
"tags": ["coroutines", "side-effects"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### rememberCoroutineScope vs LaunchedEffect\n\n| Concept | Description |\n|------|-------------|\n| rememberCoroutineScope | Launch coroutine on events (clicks) |\n| LaunchedEffect | Runs automatically on key change |\n\n```kotlin\nval scope = rememberCoroutineScope()\nButton(onClick = {\n  scope.launch { doSomething() }\n}) { Text(\"Click\") }\n\nLaunchedEffect(count) {\n  delay(1000)\n  println(\"Count changed\")\n}\n```"
}
]
}
