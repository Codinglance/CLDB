# Functions

Functions in Kotlin are declared using the **fun** keyword. They are designed to be concise, often allowing you to skip curly braces and explicit return types.


## 1. Basic Function Anatomy

A standard function includes a name, parameters (with types), and a return type.

```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}
```

* **Parameters:** Must always have an explicit type (**a: Int**).
* **Return Type:** Placed after the parameter list following a colon. If a function returns nothing, the return type is **Unit** (similar to **void** in Java), which is usually omitted.


## 2. Single-Expression Functions

If a function returns a single expression, you can omit the curly braces and the **return** keyword. The compiler will infer the return type.

```kotlin
fun multiply(a: Int, b: Int) = a * b
```


## 3. Default and Named Arguments

Kotlin allows you to provide **default values** for parameters. This significantly reduces the need for "method overloading."

### Default Arguments

```kotlin
fun displayMessage(message: String, prefix: String = "INFO") {
    println("[$prefix] $message")
}

// Calls:
displayMessage("System started")          // Output: [INFO] System started
displayMessage("Battery low", "WARNING")  // Output: [WARNING] Battery low
```

### Named Arguments

When calling a function, you can name the arguments to make the code readable or to skip parameters with default values.

```kotlin
displayMessage(prefix = "LOG", message = "User logged in")
```


## 4. Function Scope

In Kotlin, you don't always need to wrap a function inside a class.

* **Top-level Functions:** Functions defined outside of any class. These are globally accessible.
* **Member Functions:** Functions defined inside a class or object.
* **Local Functions:** You can actually define a function **inside** another function!

```kotlin
fun outer() {
    fun inner() {
        println("I am a local function")
    }
    inner()
}
```


## 5. Varargs (Variable Number of Arguments)

If you don't know how many arguments will be passed, use the **vararg** modifier.

```kotlin
fun printAll(vararg messages: String) {
    for (m in messages) println(m)
}

// Usage:
printAll("Hello", "World", "Kotlin", "Android")
```


### Summary

* Use **fun** to declare functions.
* **Single-expression functions** make your code much cleaner.
* **Default arguments** eliminate the need for multiple overloaded methods.
* **Named arguments** improve code readability, especially with many parameters.

