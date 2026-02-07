## 1. What is an Exception?

An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. If an exception isn't "caught," the app will crash.

In Kotlin, all exception classes descend from the **Throwable** class. Every exception has a message and an optional cause.



## 2. Try, Catch, and Finally

To prevent a crash, you wrap risky code in a **try** block and provide a **catch** block to handle the error.

```kotlin
try {
    val result = 10 / 0 // This will throw an ArithmeticException
} catch (e: ArithmeticException) {
    println("Caught a math error: ${e.message}")
} finally {
    // This code ALWAYS runs, regardless of whether an exception occurred
    println("Cleaning up resources...")
}
```

* **try**: The block where you put code that might fail.
* **catch**: The block that runs only if an error occurs. You can have multiple catch blocks for different error types.
* **finally**: Used for cleanup (closing files, hiding progress bars).


## 3. Try as an Expression

Just like **if** and **when**, **try** is an expression in Kotlin. It can return a value.

```kotlin
val input = "123a"
val number = try {
    input.toInt() 
} catch (e: NumberFormatException) {
    null // If it fails, the variable becomes null
}
```



## 4. Throwing Exceptions

You can manually trigger an exception using the **throw** keyword. This is useful for validating data or signaling that a specific business rule was broken.

```kotlin
fun setAge(age: Int) {
    if (age !in 0..120) {
        throw IllegalArgumentException("Age must be between 0 and 120")
    }
}
```


## 5. Checked vs. Unchecked Exceptions

Here is a major difference between Kotlin and Java:

* **Java** has **Checked Exceptions** (errors you are *forced* to catch or declare).
* **Kotlin** does **not** have checked exceptions. You are never forced by the compiler to wrap code in a try/catch. While this makes code cleaner, it puts the responsibility on you, the developer, to know what might fail.


## 6. Practical Android Example

When working with APIs or Databases in Android, you should always handle potential failures to ensure a smooth user experience.

```kotlin
lifecycleScope.launch {
    try {
        binding.progressBar.show()
        val data = repository.getRemoteData()
        displayData(data)
    } catch (e: IOException) {
        // Handle network/disk errors
        showErrorMessage("Please check your internet connection")
    } catch (e: Exception) {
        // Handle everything else
        showErrorMessage("An unexpected error occurred")
    } finally {
        binding.progressBar.hide()
    }
}
```


### Summary

* Use **try-catch** to handle errors gracefully without crashing the app.
* The **finally** block is perfect for UI cleanup (like hiding a spinner).
* Kotlin treats **try** as an expression, making it easy to assign fallback values.
* There are **no checked exceptions** in Kotlin, so stay vigilant about what might fail!


