

# Null Safety

In many languages, accessing a member of a null reference results in a crash. In Kotlin, the type system distinguishes between references that can hold `null` (nullable) and those that cannot (non-nullable).


## 1. Non-Nullable by Default

In Kotlin, variables are non-nullable by default. If you try to assign **null** to a standard variable, the code will not compile.

```kotlin
var name: String = "John"
// name = null // ❌ Compilation Error

```

## 2. Nullable Types (**?**)

To allow a variable to hold a null value, you must explicitly declare it as nullable by adding a **?** after the type.

```kotlin
var nullableName: String? = "John"
nullableName = null // ✅ This is allowed

```


## 3. Handling Nulls Safely

When you have a nullable variable, Kotlin won't let you use it directly because it might be null. You have three main ways to handle this:

### A. Safe Call Operator (**?.**)

The safe call operator executes the property or method only if the variable is **not null**. If it is null, it simply returns **null** instead of crashing.

```kotlin
val length = nullableName?.length 
// If nullableName is null, length becomes null. It doesn't crash.

```

### B. The Elvis Operator (**?:**)

The Elvis operator allows you to provide a **default value** in case the expression on the left is null.

```kotlin
val length = nullableName?.length ?: 0
// If nullableName is null, length becomes 0.

```

### C. The Not-Null Assertion (**!!**)

This operator converts any value to a non-nullable type and **throws an exception** if the value is null.

 **Warning:** Use this sparingly. It is the "I know what I'm doing" operator and can lead to crashes if you are wrong.

```kotlin
val length = nullableName!!.length // Will crash if nullableName is null

```


## 4. Smart Casts and Null Checks

If you check a variable for null using an **if** statement, the Kotlin compiler remembers this and "smart casts" the variable to a non-nullable type inside that block.

```kotlin
val name: String? = "Kotlin"

if (name != null) {
    println(name.length) // ✅ No ?. needed here! Kotlin knows it's not null.
}

```


## 5. Safe Casting (**as?**)

Regular casting in Java/Kotlin using **as** can throw a **ClassCastException**. The safe cast operator returns **null** if the cast is not possible.

```kotlin
val message: Any = "Hello"
val safeInt: Int? = message as? Int // Returns null instead of crashing

```


### Summary

* **Type System:** Variables are non-nullable by default.
* **?**: Marks a type as nullable.
* **?.**: Safely access properties without crashing.
* **?:**: Provide a fallback/default value.
* **!!**: Force a null to be non-null (dangerous).


