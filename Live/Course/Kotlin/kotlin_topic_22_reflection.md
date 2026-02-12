
## 1. The Core Components

To use reflection, you need the **kotlin-reflect** library. The API revolves around three main "K" classes:

| Component     | Description                                                                                    |
| ------------- | ---------------------------------------------------------------------------------------------- |
| **KClass**    | Represents a class (e.g., **User::class**). Used to find constructors or check the class name. |
| **KFunction** | Represents a function (e.g., **::myFunction**). Used to call functions dynamically.            |
| **KProperty** | Represents a property (e.g., **User::name**). Used to read or update variable values.          |


## 2. Introspection in Action

Here is how you look inside a class at runtime to see what's there.

```kotlin
data class User(val name: String, val age: Int)

fun main() {
    val userClass = User::class // This is a KClass
    
    println("Class Name: ${userClass.simpleName}") // Prints "User"
    
    // List all properties
    userClass.members.forEach { member ->
        println("Found member: ${member.name}")
    }
}
```


## 3. Dynamic Invocation

Reflection allows you to call a function even if you don't know its name until the app is running.

```kotlin
class Greeter {
    fun sayHello(name: String) = "Hello, $name!"
}

val greeter = Greeter()
val function = Greeter::sayHello // KFunction

// Call the function dynamically
val result = function.call(greeter, "Android Developer")
println(result) // Prints "Hello, Android Developer!"
```



## 4. Annotations: The Metadata Powerhouse

Annotations are "tags" you add to your code to provide extra info. Reflection is what "reads" these tags.

```kotlin
// 1. Declare an annotation
@Target(AnnotationTarget.PROPERTY)
@Retention(AnnotationRetention.RUNTIME) // Must be RUNTIME to be seen by reflection
annotation class JsonKey(val name: String)

// 2. Use it
data class User(@JsonKey("user_full_name") val name: String)

// 3. Read it via Reflection
val property = User::name
val annotation = property.annotations.find { it is JsonKey } as? JsonKey
println(annotation?.name) // Prints "user_full_name"
```



## 5. Reflection vs. Code Generation (KSP)

In Android, reflection is powerful but can be **slow** (about **20x–70x slower** than direct calls) and uses more memory.

* **Reflection:** Works at **Runtime**. Easier to write but slower for the user. (Example: **Gson**)
* **KSP / Kapt (Code Generation):** Works at **Compile Time**. It writes the "boring" mapping code for you before the app even runs. (Example: **Room**, **Moshi**, **Kotlin Serialization**)



## 6. Pro-Tip: Reified Types

Remember **Topic 21**? **inline** functions with **reified** types actually use reflection under the hood to let you do things like **if (T is String)**, which is normally impossible due to **Type Erasure**.



### Summary

* **Reflection** lets your app inspect and manipulate its own structure at runtime.
* **KClass**, **KFunction**, and **KProperty** are your primary tools.
* **Annotations** provide metadata that reflection can read to automate tasks.
* **Warning:** Excessive reflection can slow down app startup. Prefer **Code Generation** (**KSP**) for performance-critical logic.
