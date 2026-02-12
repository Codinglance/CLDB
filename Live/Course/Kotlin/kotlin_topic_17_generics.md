
## 1. Why Generics?

Without generics, you might be tempted to use **Any** to handle different types. However, using **Any** requires manual casting, which is dangerous and can lead to **ClassCastException** at runtime. Generics catch these errors at **compile-time**.


## 2. Generic Classes

You define a generic class by adding a type parameter in angle brackets **<T>** (where **T** stands for "Type").

```kotlin
class Box<T>(val content: T)

val intBox = Box<Int>(10)
val stringBox = Box<String>("Hello")
```

In Android, you see this everywhere. For example, **ArrayList<String>** or **LiveData<User>**.


## 3. Generic Functions

Functions can also have their own type parameters. The type is placed before the function name.

```kotlin
fun <T> printItem(item: T) {
    println("Item is: $item")
}

// Usage
printItem(42)           // T is inferred as Int
printItem("Kotlin")     // T is inferred as String
```


## 4. Generic Constraints (Upper Bounds)

Sometimes you don't want a generic to accept *any* type. You can restrict it using a colon **:**. This is called an **Upper Bound**.

```kotlin
// This function only accepts Numbers (Int, Double, Float, etc.)
fun <T : Number> processPrice(amount: T) {
    println(amount.toDouble() * 0.10)
}

// processPrice("100") // ❌ Compilation Error: String is not a Number
```


## 5. Variance: **out** and **in**

This is an advanced concept that describes how generic types relate to each other in terms of inheritance.

### Covariance (**out**)

Use **out** if the class only **produces** (returns) the type **T** and never consumes it. This allows you to use a **Producer<Cat>** where a **Producer<Animal>** is expected.

```kotlin
interface Producer<out T> {
    fun produce(): T
}
```

### Contravariance (**in**)

Use **in** if the class only **consumes** (takes as an argument) the type **T**.

```kotlin
interface Consumer<in T> {
    fun consume(item: T)
}
```


## 6. Real-World Android Example: Generic Base Adapter

When working with XML-based RecyclerViews, developers often create a Base Adapter to avoid repeating boilerplate code for every list.

```kotlin
abstract class BaseAdapter<T>(private val items: List<T>) : RecyclerView.Adapter<MyViewHolder>() {
    // T can be 'User', 'Product', or 'Notification'
    override fun getItemCount() = items.size
    
    fun getItem(position: Int): T = items[position]
}
```


### Summary

* **Generics** (**<T>**) make code reusable and type-safe.
* **Type Inference** usually means you don't have to type **<String>** or **<Int>** manually when calling functions.
* **Constraints** (**<T : Type>**) limit what types can be used.
* **out** and **in** handle complex inheritance relationships in generic types.
