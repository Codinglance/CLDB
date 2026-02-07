
## 1. Property Delegation

Property delegation allows you to outsource the **get()** and **set()** logic of a variable to a separate class.

### Standard Delegate: **by lazy**

The most common delegate in Android. It ensures the variable is only initialized the **first time it is accessed**, saving memory and CPU.

```kotlin
// The heavy object is NOT created until 'database' is called for the first time
val database: AppDatabase by lazy {
    Room.databaseBuilder(context, AppDatabase::class.java, "db").build()
}
```



### Standard Delegate: **Delegates.observable**

This delegate acts as a “listener.” It triggers a callback every time the value of the property changes.

```kotlin
var count: Int by Delegates.observable(0) { property, oldValue, newValue ->
    println("Value changed from $oldValue to $newValue")
}
```


## 2. Custom Property Delegates

You can create your own delegate to handle repetitive logic, like reading from **SharedPreferences** or extras in an **Intent**.

A delegate must provide an **getValue** (and **setValue** for **var**) operator function.

```kotlin
class PreferenceDelegate(val key: String, val defaultValue: String) {
    operator fun getValue(thisRef: Any?, property: KProperty<*>): String {
        return prefs.getString(key, defaultValue) ?: defaultValue
    }

    operator fun setValue(thisRef: Any?, property: KProperty<*>, value: String) {
        prefs.edit().putString(key, value).apply()
    }
}

// Usage in an Activity
var userName: String by PreferenceDelegate("user_name", "Guest")
```



## 3. Class Delegation (The “Has-A” Pattern)

Class delegation allows you to implement an interface by delegating all its methods to a specific object. This is a powerful alternative to inheritance, avoiding the **fragile base class** problem.

### The Problem

If you want a class to behave like a **List** but add one custom feature, you usually have to override dozens of methods.

### The Solution

Use the **by** keyword in the class header.

```kotlin
interface Analytics {
    fun logEvent(event: String)
}

class FirebaseAnalytics : Analytics {
    override fun logEvent(event: String) = println("Logging to Firebase: $event")
}

// Screen implements Analytics by delegating to the provided provider
class HomeScreen(analyticsProvider: Analytics) : Analytics by analyticsProvider {
    // I don't need to override logEvent! It is handled by analyticsProvider.
}
```


## 4. Why use Delegation in Android?

1. **Memory Management:** Use **by lazy** to avoid initializing everything in **onCreate()**.
2. **Cleaner ViewModels:** Use **by viewModels()** (from KTX) to handle ViewModel lifecycle automatically.
3. **Composition over Inheritance:** Use Class Delegation to add functionality (like a “Navigator” or “Logger”) to an Activity without making the Activity class 2000 lines long.



## 5. ViewBinding Delegate (Pro Tip)

In XML-based Android, managing **_binding** and **binding** nullability in Fragments is annoying. Many developers use a custom delegate to handle this:

```kotlin
// Usage
class HomeFragment : Fragment(R.layout.fragment_home) {
    private val binding by viewBinding(FragmentHomeBinding::bind)

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        binding.titleText.text = "Hello Delegation!"
    }
}
```


### Summary

* **Property Delegation (by)** intercepts the getter and setter of a variable.
* **by lazy** is essential for performance in Android.
* **Class Delegation** allows a class to implement an interface by passing the work to a helper object.
* Delegation promotes **reusability** and keeps your classes focused on one task.

