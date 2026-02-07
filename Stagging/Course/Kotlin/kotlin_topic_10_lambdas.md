## 1. What is a Lambda?

A lambda expression is a short way to represent a function. It is defined within curly braces **{ }**.

### Basic Syntax

**val sum = { a: Int, b: Int -> a + b }**

* **Parameters:** **a: Int, b: Int** (Before the **->**)
* **Body:** **a + b** (After the **->**)

```kotlin
fun main() {
    val greeting = { println("Hello Lambda!") }
    greeting() // Calls the lambda
}
```


## 2. Higher-Order Functions

A **Higher-Order Function** is a function that takes another function as a parameter or returns a function.

```kotlin
fun calculate(a: Int, b: Int, operation: (Int, Int) -> Int): Int {
    return operation(a, b)
}

fun main() {
    val result = calculate(10, 5) { x, y -> x + y }
    println(result) // Output: 15
}
```


## 3. The **it** Keyword

If a lambda has only **one parameter**, you don't have to name it. Kotlin provides an implicit name called **it**.

```kotlin
val numbers = listOf(1, 2, 3, 4)

// Instead of { num -> num * 2 }
val doubled = numbers.map { it * 2 }
```


## 4. Trailing Lambda Syntax

In Kotlin, if the **last parameter** of a function is a function, you can place the lambda expression **outside** the parentheses. This is a core part of how Android’s Jetpack Compose and various DSLs are written.

```kotlin
// Instead of this:
// repeat(3, { println("Hello") })

// We do this:
repeat(3) {
    println("Hello")
}
```


## 5. Function Types

To pass a function as a parameter, you must define its **type**.

* **() -> Unit** : Takes nothing, returns nothing.
* **(Int, Int) -> Int** : Takes two Integers, returns an Integer.
* **(String) -> Boolean** : Takes a String, returns true/false.


## 6. Closures

Lambdas in Kotlin can access variables declared outside their scope (their "closure"). Unlike Java, Kotlin allows you to even **modify** those variables.

```kotlin
var counter = 0
val increment = { counter++ }

increment()
increment()
println(counter) // Output: 2
```


### Summary

* **Lambdas** are functions without names, written inside **{ }**.
* **Higher-Order Functions** treat functions like variables (passing them as arguments).
* **it** is the default name for a single parameter in a lambda.
* **Trailing Lambda Syntax** makes code look cleaner by moving the lambda outside **()**.
