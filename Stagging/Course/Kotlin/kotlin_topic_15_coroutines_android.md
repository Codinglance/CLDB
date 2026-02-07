
## 1. Lifecycle-Aware Scopes

In Android, we rarely use **GlobalScope**. Instead, we use scopes provided by the Android Jetpack libraries that are tied to the lifecycle of the UI components.

### A. **lifecycleScope**

Tied to an **Activity** or **Fragment**. When the Activity is destroyed, any coroutine running in this scope is automatically cancelled.

```kotlin
class HomeActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        
        lifecycleScope.launch {
            // This task will be cancelled if the Activity is closed
            val data = fetchData()
            binding.textView.text = data
        }
    }
}
```

### B. **viewModelScope**

Tied to a **ViewModel**. This is the most common scope used in professional Android development. Coroutines here survive configuration changes (like screen rotation) and only cancel when the ViewModel is cleared.

```kotlin
class UserViewModel : ViewModel() {
    fun loadUser() {
        viewModelScope.launch {
            val user = repository.getUser()
            // Update UI State...
        }
    }
}
```

## 2. Switching Contexts with **withContext**

You should always start a coroutine on the Main thread (the default for **lifecycleScope**) and only switch to a background thread when necessary.

```kotlin
lifecycleScope.launch(Dispatchers.Main) {
    // 1. UI is responsive here
    binding.progressBar.show()

    // 2. Switch to IO thread for heavy work
    val result = withContext(Dispatchers.IO) {
        performComplexCalculation() 
    }

    // 3. Back on Main thread automatically
    binding.progressBar.hide()
    binding.resultView.text = result
}
```


## 3. Handling Exceptions

If a coroutine fails (e.g., no internet connection during a network call), it can crash your app. Use a **try-catch** block inside the coroutine to handle errors gracefully.

```kotlin
viewModelScope.launch {
    try {
        val data = apiService.getData()
        _uiState.value = Success(data)
    } catch (e: Exception) {
        _uiState.value = Error("Failed to load data")
    }
}
```


## 4. **repeatOnLifecycle** (The Modern Way)

For modern XML-based apps using **Flow** or **LiveData**, you often want to collect data only when the UI is actually visible to the user. **repeatOnLifecycle** automatically starts and stops the coroutine as the Activity goes from **onStart** to **onStop**.

```kotlin
lifecycleScope.launch {
    repeatOnLifecycle(Lifecycle.State.STARTED) {
        // Collect data only when the app is in the foreground
        viewModel.dataFlow.collect { data ->
            binding.textView.text = data
        }
    }
}
```


## 5. Main-Safety

A well-written suspend function should be **Main-safe**. This means it should be safe to call from the Main thread without blocking it.

```kotlin
// This function is Main-safe because it handles its own Dispatcher switch
suspend fun safeDatabaseCall(): List<User> = withContext(Dispatchers.IO) {
    database.userDao().getAll()
}
```


### Summary

* Use **viewModelScope** for business logic and data fetching.
* Use **lifecycleScope** for UI-specific tasks (like animations).
* **withContext(Dispatchers.IO)** is the standard way to move work off the Main thread.
* **repeatOnLifecycle** prevents unnecessary background processing when the user isn't looking at the app.
