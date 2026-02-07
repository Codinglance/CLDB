

# Variables & Data Types

In Kotlin, how we handle data is centered around two main concepts: **immutability** (consistency) and **type inference** (conciseness).

## 1. Defining Variables: **val** vs **var**

Kotlin uses two keywords to declare variables. Choosing the right one is the first step toward writing safe code.

### **val** (Value)

* **Immutable:** Once assigned, the value cannot be changed.
* Equivalent to **final** in Java.
* **Rule of thumb:** Always use **val** by default.

### **var** (Variable)

* **Mutable:** The value can be reassigned later.
* Use this only when the data is expected to change (e.g., a counter or a user input field).

```kotlin
val birthYear = 1995 // Fixed
var currentWeight = 70 // Can change

// birthYear = 1996  <-- This would cause a Compiler Error
currentWeight = 68   // This is perfectly fine

```


## 2. Type Inference

Kotlin is **statically typed**, but you don't always have to write the type explicitly. The compiler "infers" the type based on the value you provide.

```kotlin
val message = "Hello" // The compiler knows this is a String
val age = 25          // The compiler knows this is an Int

```

If you want to be explicit (or don't assign a value immediately), use this syntax:
**val variableName: DataType = value**


## 3. Basic Data Types

Kotlin treats everything as an object, which means you can call methods on even basic types.

| Category | Types                           | Examples   |
| --- |---------------------------------|------------|
| **Numbers** | Byte, Short, Int, Long, Float, Double | 3.14f, 100L |
| **Booleans** | Boolean                         | true, false |
| **Characters** | Char                            | 'A', '1'   |
| **Strings** | String                          | "Kotlin is fun" |

### Numerical Literals

* **Long:** Suffixed with **L** (e.g., **1000L**)
* **Float:** Suffixed with **f** or **F** (e.g., **2.5f**)
* **Underscores:** You can use underscores to make large numbers readable: **val creditCard = 1234_5678_9012_3456L**


## 4. String Templates

Kotlin makes string concatenation incredibly easy using the **$** symbol. You no longer need to use **+** to join strings and variables.

```kotlin
val name = "Android"
val version = 14

// Simple variable usage
println("Welcome to $name version $version")

// Using expressions with curly braces
println("The name has ${name.length} characters")

```


## 5. Type Conversion

In Kotlin, smaller types (like **Int**) are **not** implicitly converted to larger types (like **Long**). You must perform an explicit conversion.

```kotlin
val smallInt: Int = 10
// val bigLong: Long = smallInt // Error: Type mismatch

val bigLong: Long = smallInt.toLong() // Correct

```


### Summary

* Use **val** for constants and **var** for variables.
* Kotlin can usually figure out the **Data Type** on its own.
* **String templates** ($) are the preferred way to format text.
* Explicit conversion is required between different number types.

