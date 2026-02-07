# Kotlin Best Practices & Coding Style

## 1. Favor Immutability

Always start with **val**. Only change it to **var** if you absolutely must. This prevents accidental data changes in different parts of your app.

* **Variables:** Use **val** by default.
* **Collections:** Use **listOf()** instead of **mutableListOf()** unless you are actively adding/removing items.



## 2. Use Expression Bodies

If a function or logic can be written in one line, do it. It reduces "visual noise."

```kotlin
// ❌ Not Idiomatic
fun getGreeting(name: String): String {
    return "Hello, $name"
}

// ✅ Idiomatic
fun getGreeting(name: String) = "Hello, $name"
```


## 3. Leverage String Templates

Stop using the **+** operator to join strings. It’s harder to read and less efficient.

```kotlin
// ❌ Bad
println("The result is: " + result + " units")

// ✅ Good
println("The result is: $result units")
```


## 4. Master Scope Functions

Use **apply** for configuration and **let** for null-checks. This keeps your code blocks organized and clearly communicates your intent.

```kotlin
// ✅ Clean UI configuration
val profileImage = ImageView(context).apply {
    contentScale = ScaleType.CENTER_CROP
    alpha = 0.5f
    isVisible = true
}
```


## 5. Avoid **!!** (The Not-Null Assertion)

Using **!!** is essentially telling the compiler, “I don't care about safety; crash the app if I'm wrong.”

* **Better:** Use **?.** (Safe Call) or **?:** (Elvis Operator).
* **Better:** Use **if (value != null)** to let the compiler smart-cast the variable.


## 6. Meaningful Named Arguments

When a function has more than two parameters—especially Booleans or Strings—name them at the call site. This makes the code self-documenting.

```kotlin
// ❌ What do these booleans mean?
updateUser("Alex", true, false)

// ✅ Crystal clear
updateUser(
    name = "Alex",
    isAdmin = true,
    isNotificationsEnabled = false
)
```


## 7. Sealed Classes for UI States

In Android, don't use multiple Booleans like **isLoading**, **isError**, and **data** in your ViewModel. Group them into a single **Sealed Class**. This creates a **Single Source of Truth**.


## 8. Extension Functions for Utility

Instead of creating a **StringUtils** class, create extension functions. This makes the code feel like it's part of the language.

```kotlin
// ✅ Extension property for common validation
val String.isValidEmail: Boolean
    get() = Patterns.EMAIL_ADDRESS.matcher(this).matches()
```


## 9. Trailing Commas

Kotlin supports trailing commas. Using them makes your git **diffs** cleaner because adding a new item to a list doesn't change the line above it.

```kotlin
val colors = listOf(
    "Red",
    "Green",
    "Blue", // Trailing comma
)
```


### Summary Checklist

* [ ] Is it **val**?
* [ ] Can it be a **String template**?
* [ ] Did I handle nulls safely without **!!**?
* [ ] Is my UI state represented by a **Sealed Class**?
* [ ] Am I using **Dispatchers.IO** for background tasks?


