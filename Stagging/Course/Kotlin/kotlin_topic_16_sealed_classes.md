

## 1. What is a Sealed Class?

A sealed class is a class that restricts its inheritance hierarchy. All subclasses must be defined in the same package (and usually the same file). Think of it as an **Enum on steroids**.

While an Enum constant is a single instance, a subclass of a sealed class can have **multiple instances**, each with its own state.


## 2. Sealed Class vs. Enum

The table below highlights the key differences between enum class and sealed class, helping you decide which one fits your design needs.
| Feature            | Enum Class                              | Sealed Class                                           |
| ------------------ | --------------------------------------- | ------------------------------------------------------ |
| **Instance State** | Every constant is exactly one instance. | Subclasses can be data classes with different data.    |
| **Flexibility**    | Limited to simple constants.            | Can contain objects, data classes, or regular classes. |
| **Usage**          | Fixed values (Days, Colors).            | Complex states (API Responses, UI States).             |


## 3. Real-World Android Example: UI State

This is the most common use case in Android apps today. It allows your Activity or Fragment to handle every possible state of a screen.

```kotlin
sealed class Result {
    object Loading : Result()
    data class Success(val data: String) : Result()
    data class Error(val message: String, val code: Int) : Result()
}
```

### Handling the State with **when**

The compiler knows exactly how many subclasses exist. If you use **when** as an expression, it will force you to handle every case (exhaustive check).

```kotlin
fun updateUI(result: Result) {
    when (result) {
        is Result.Loading -> binding.progressBar.show()
        is Result.Success -> {
            binding.progressBar.hide()
            binding.textView.text = result.data
        }
        is Result.Error -> {
            binding.progressBar.hide()
            showErrorToast(result.message)
        }
    }
}
```


## 4. Sealed Interfaces

Introduced in Kotlin 1.5, **Sealed Interfaces** work just like sealed classes but allow a class to implement multiple sealed hierarchies. Use these when you don't need to share code from a base class (like a constructor).

```kotlin
sealed interface NetworkEvent

class ClickEvent(val id: Int) : NetworkEvent
class SwipeEvent(val direction: String) : NetworkEvent
```


## 5. Benefits for Clean Architecture

* **Type Safety:** You don't need an **else** branch in **when** statements because the compiler knows the hierarchy is sealed.
* **Readability:** It makes the flow of data between your ViewModel and Activity very clear.
* **Grouping:** It keeps related logic together, making the code easier to maintain as the app grows.


### Summary

* **Sealed classes** provide a closed hierarchy for class inheritance.
* They allow for **stateful** constants (unlike Enums).
* They are essential for representing **Result** types and **UI States** in Android.
* They work perfectly with the **when** expression to ensure all cases are handled.
