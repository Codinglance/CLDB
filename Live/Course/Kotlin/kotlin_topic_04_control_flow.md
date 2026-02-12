# Operators & Control Flow

Control flow determines the order in which your code executes. Kotlin improves upon traditional logic structures by treating almost everything as an **expression** (meaning it can return a value).


## 1. Arithmetic & Comparison Operators

Kotlin uses standard operators for math and logic:

* **Arithmetic:** `+`, `-`, `*`, `/`, `%`
* **Comparison:** `==` (equality), `!=` (not equal), `<`, `>`, `<=`, `>=`
* **Assignment:** `=`, `+=`, `-=`, `*=`, `/=`, `%=`

 **Note:** In Kotlin, **==** checks for **structural equality** (calls **.equals()**), while **===** checks for **referential equality** (if two references point to the same object).


## 2. Conditional Expressions: **if**

In Kotlin, **if** is an expression, not just a statement. This means it can return a value directly to a variable.

```kotlin
val a = 10
val b = 20

// Using if as an expression
val max = if (a > b) {
    println("Choose a")
    a
} else {
    println("Choose b")
    b
}

```


## 3. The **when** Expression

The **when** expression is Kotlin's far more powerful version of the **switch** statement found in Java or C++.

```kotlin
val day = 3

val dayName = when (day) {
    1 -> "Monday"
    2 -> "Tuesday"
    3 -> "Wednesday"
    in 4..5 -> "Weekday remainder" // Range check
    6, 7 -> "Weekend"             // Multiple values
    else -> "Invalid day"         // Required if used as an expression
}

```


## 4. Loops

Kotlin provides several ways to iterate over data.

### A. The **for** Loop

The **for** loop works with anything that provides an iterator (ranges, arrays, collections).

```kotlin
// Ranges: Including 5
for (i in 1..5) print(i) 

// Ranges: Excluding 5 (until)
for (i in 1 until 5) print(i)

// Stepping through
for (i in 1..10 step 2) print(i)

// Downward
for (i in 5 downTo 1) print(i)

```

### B. **while** and **do-while**

These function exactly like they do in most other languages.

```kotlin
var x = 5
while (x > 0) {
    x--
}

do {
    val y = retrieveData()
} while (y != null)

```


## 5. Ranges and Checks

Kotlin introduces the **..** operator and the **in** keyword to make range checks incredibly readable.

```kotlin
val percent = 85

if (percent in 0..100) {
    println("Valid percentage")
}

if (percent !in 0..50) {
    println("Passed!")
}

```

### Summary

* **if** and **when** are expressions and can return values.
* **when** is the preferred way to handle multiple branches of logic.
* **Ranges** (**..**, **until**, **step**) make loops very flexible and readable.
* **in** keyword simplifies checking if a value exists within a bound.


