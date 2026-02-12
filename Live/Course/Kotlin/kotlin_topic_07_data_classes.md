
## 1. Data Classes

A **Data Class** is a class whose main purpose is to hold data. When you mark a class with the **data** keyword, the compiler automatically generates several useful functions for you.

### Syntax

```kotlin
data class User(val id: Int, val name: String, val email: String)
```

### Requirements for Data Classes:

* The primary constructor must have at least one parameter.
* All primary constructor parameters must be marked as **val** or **var**.
* Data classes cannot be **abstract**, **open**, **sealed**, or **inner**.

### What do you get automatically?

1. **toString()**: Prints a readable string like **User(id=1, name=Alex, email=[a@b.com](mailto:a@b.com))**.
2. **equals() & hashCode()**: Compares objects based on their actual data, not their memory address.
3. **copy()**: Allows you to create a new object with some properties changed while keeping the rest the same.

```kotlin
val user1 = User(1, "Samy", "samy@mail.com")
// Create a new user based on user1, but change the email
val user2 = user1.copy(email = "new_samy@mail.com")
```


## 2. Destructuring Declarations

Data classes allow you to "unpack" an object into multiple variables. This is very common in Android development when handling state or results.

```kotlin
val (id, name, email) = user1
println(name) // Output: Samy
```


## 3. Enum Classes

**Enum Classes** are used to represent a fixed set of constants (like directions, days of the week, or API states).

### Basic Enum

```kotlin
enum class Difficulty {
    EASY, MEDIUM, HARD
}
```

### Enums with Properties

Enums in Kotlin can have properties and methods, just like regular classes.

```kotlin
enum class Priority(val color: String) {
    LOW("Green"),
    MEDIUM("Yellow"),
    HIGH("Red"); // Semicolon is required here if you add a function

    fun displayInfo() = "Priority level is $name and color is $color"
}
```


## 4. Using Enums with **when**

The **when** expression is particularly powerful with Enums. If you cover all possible enum cases, you don’t even need an **else** branch.

```kotlin
val currentPriority = Priority.HIGH

val message = when(currentPriority) {
    Priority.LOW -> "Take your time."
    Priority.MEDIUM -> "Keep a steady pace."
    Priority.HIGH -> "Address this immediately!"
}
```


### Summary

* **data class** eliminates boilerplate for classes that just hold information.
* Use **copy()** to safely update immutable data.
* **enum class** represents a specific collection of related constants.
* Enums can hold properties and logic, making them more than just simple labels.

