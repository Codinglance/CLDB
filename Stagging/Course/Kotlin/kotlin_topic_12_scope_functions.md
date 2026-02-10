

# Scope Functions

There are five scope functions in Kotlin: **let**, **run**, **with**, **apply**, and **also**. They all do essentially the same thing—execute a block of code on an object—but they differ in how the object is referred to and what they return.


## 1. **apply** (The Configuration Tool)

**Context Object:** **this** | **Return Value:** The object itself
Use **apply** when you want to initialize or configure an object. It is most common in Android for setting up Intents or View properties.

```kotlin
// Without apply
val intent = Intent(this, DetailActivity::class.java)
intent.putExtra("ID", 123)
intent.action = "ACTION_VIEW"

// With apply
val intent = Intent(this, DetailActivity::class.java).apply {
    putExtra("ID", 123)
    action = "ACTION_VIEW"
}
```


## 2. **let** (The Null-Safety Tool)

**Context Object:** **it** | **Return Value:** The lambda result
**let** is primarily used to execute a block only if an object is not null, or to transform an object into a different result.

```kotlin
val name: String? = "Kotlin"

name?.let {
    // This block only runs if name is not null
    println("The length of the name is ${it.length}")
}
```


## 3. **also** (The Side-Effect Tool)

**Context Object:** **it** | **Return Value:** The object itself
Use **also** when you want to perform an additional action that doesn't modify the object, such as logging or validation.

```kotlin
val list = mutableListOf(1, 2, 3).also {
    Log.d("Debug", "List created with size: ${it.size}")
}
```


## 4. **with** (The Grouping Tool)

**Context Object:** **this** | **Return Value:** The lambda result
**with** is not an extension function; it takes the object as an argument. Use it when you want to call multiple methods on the same object without repeating its name.

```kotlin
with(binding) {
    tvTitle.text = "Welcome"
    tvDescription.text = "Click the button below to start."
    btnStart.isEnabled = true
}
```


## 5. **run** (The Hybrid Tool)

**Context Object:** **this** | **Return Value:** The lambda result
**run** is like a combination of **with** and **let**. It’s useful when you want to configure an object and then compute a result.

```kotlin
val hexString = "FF".run {
    toInt(16) // returns 255
}
```


## Which one to use?

Here’s a quick comparison to help you choose the right Kotlin scope function for your use case:

| Function  | Reference | Return Value  | Main Use Case                                      |
| --------- | --------- | ------------- | -------------------------------------------------- |
| **apply** | **this**  | Object itself | **Configuring** an object (Setting UI properties). |
| **let**   | **it**    | Lambda result | **Null-checks** or mapping an object.              |
| **also**  | **it**    | Object itself | **Logging** or additional side-actions.            |
| **with**  | **this**  | Lambda result | **Grouping** multiple calls on one object.         |
| **run**   | **this**  | Lambda result | **Configuration + Calculation**.                   |


### Summary

* Scope functions create a temporary scope for an object to improve readability.
* **apply** and **also** return the object itself (useful for chaining).
* **let**, **run**, and **with** return the last line of the block.
* In Android, **apply** is your best friend for UI setup, and **let** is your best friend for null safety.
