

In modern Android development, simply starting a task isn't enough; you must be able to stop it. If a user navigates away from a screen while a 10MB file is downloading, you need to kill that process immediately. This is where **Structured Concurrency** and **Cooperative Cancellation** come into play.


## 1. Structured Concurrency

Structured Concurrency ensures that when a parent coroutine is cancelled, all its children are cancelled too. You don't have to manually track every single background task; you just manage the **Scope**.

* **Parent-Child Bond:** If a child coroutine fails with an exception, it usually cancels its parent and its siblings (unless using a **SupervisorJob**).
* **Leak Prevention:** By using **viewModelScope** or **lifecycleScope**, Android ensures that when the UI dies, the tasks die with it.


## 2. Cancellation is Cooperative

A coroutine doesn't just "stop" instantly when you call **job.cancel()**. It has to **cooperate**. It must periodically check if it has been cancelled.

### How to check for cancellation:

1. **Suspending Functions:** Most standard library functions (like **delay()**, **withContext()**, or Room/Retrofit calls) are "cancellable." They check for cancellation before executing.
2. **isActive** property: If you are running a heavy **while** loop, you must check this property manually.
3. **ensureActive():** A quick way to throw a **CancellationException** if the job is no longer active.
4. **yield():** Suspends for a moment to let other tasks run and checks for cancellation.

```kotlin
val job = scope.launch(Dispatchers.Default) {
    var i = 0
    while (i < 1000) {
        ensureActive() // ❌ If cancelled, this stops the loop immediately
        // Do heavy work...
        i++
    }
}
```


## 3. Handling Cancellation (Cleaning Up)

When a coroutine is cancelled, it throws a **CancellationException**. You can use **try-finally** to clean up resources (like closing a database or file).

**Note:** You cannot call suspending functions in **finally** because the coroutine is already cancelled. If you absolutely must, you use **withContext(NonCancellable)**.

```kotlin
launch {
    try {
        doLongWork()
    } finally {
        withContext(NonCancellable) {
            // This code will run even if the coroutine was cancelled
            closeResource() 
        }
    }
}
```


## 4. Exception Handling: The SupervisorJob

By default, if one child fails, the whole "tree" dies. In Android, you often want one task to fail without killing the others (e.g., one image in a list failing to load shouldn't crash the whole screen).

**SupervisorJob** (or **supervisorScope**) changes this rule: failure in a child stays in that child.

```kotlin
val supervisor = CoroutineScope(Dispatchers.Main + SupervisorJob())

supervisor.launch {
    // If this fails...
    throw Exception("Failed!")
}

supervisor.launch {
    // ...this one keeps running!
    println("Still active!")
}
```


## 5. CoroutineExceptionHandler

This is your "Global Catch" for a specific coroutine. It is used to catch **uncaught exceptions** that weren't handled by a **try-catch**.

```kotlin
val handler = CoroutineExceptionHandler { _, exception ->
    Log.e("CoroutineError", "Caught $exception")
}

scope.launch(handler) {
    throw RuntimeException("Boom!")
}
```


### Summary

* **Cancellation is cooperative:** Your code must check **isActive** or use suspending functions to stop.
* **Structured Concurrency** means parent scopes control child lifetimes.
* **NonCancellable** allows cleanup logic to finish even after cancellation.
* **SupervisorJob** prevents one failing task from crashing its siblings.
