
## 1. Inline Functions

When you mark a function as **inline**, the compiler doesn't "call" the function in the traditional way. Instead, it copies the code of the function (and the code of the lambdas passed to it) directly into the call site.

### Why use it?

For every lambda you pass to a non-inline function, an object of the **Function** interface is created. If that function is inside a loop, you could be creating thousands of objects, leading to memory pressure and frequent Garbage Collection.

```kotlin
inline fun <T> measureTime(block: () -> T): T {
    val start = System.currentTimeMillis()
    val result = block()
    println("Time taken: ${System.currentTimeMillis() - start}ms")
    return result
}

// At compile time, the code inside 'measureTime' and your lambda 
// are pasted right here, avoiding object creation.
measureTime {
    // perform heavy task
}
```


## 2. Noinline and Crossinline

Sometimes you want a function to be **inline**, but you need to restrict how the lambdas are used.

* **noinline**: Use this if your inline function takes multiple lambdas and you want to keep one as a regular object (e.g., to store it in a variable or pass it elsewhere).
* **crossinline**: Use this when a lambda is called inside another execution context (like a nested local object or a different thread). It prevents the lambda from using a **non-local return** (calling **return** to exit the outer function).



## 3. Reified Type Parameters

One of the coolest "side effects" of inlining is **Reified Types**. In standard Java/Kotlin, generic types are "erased" at runtime (you can't check **if (T is String)**). But because inline functions copy code, the compiler knows the actual type used.

```kotlin
// In Android, starting an Activity normally requires .class:
// startActivity(Intent(context, DetailActivity::class.java))

// With reified:
inline fun <reified T : Activity> Context.start() {
    val intent = Intent(this, T::class.java)
    startActivity(intent)
}

// Usage:
start<DetailActivity>()
```


## 4. Inline Classes (Value Classes)

Sometimes we create a class just to wrap a single value (e.g., a **Password** class that just holds a **String**). This adds the overhead of a full object for just one piece of data.

**value class** (formerly inline class) creates a wrapper at the code level for type safety, but at runtime, the compiler uses the underlying primitive/type directly.

```kotlin
@JvmInline
value class Color(val hex: String)

// This feels like an object but performs like a String
val red = Color("#FF0000")
```


## 5. When to use Inline?

* **DO** use it for functions that take **lambdas** as arguments.
* **DO** use it when you need **reified** types.
* **DON'T** use it for very large functions (it increases the size of your APK/binary).
* **DON'T** use it for functions without lambdas (the compiler will even warn you about this).


### Summary

* **inline** pastes code at the call site to save memory and CPU.
* **reified** allows you to access the actual class of a generic type at runtime.
* **value class** provides type safety for simple values without the cost of object allocation.
* In Android, these are heavily used in libraries like **Koin** and **Timber** to keep the app fast.
