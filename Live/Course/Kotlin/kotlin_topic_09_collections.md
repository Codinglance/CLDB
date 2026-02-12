
# Collections

A collection usually contains a number of objects (from zero to many) of the same type. Kotlin provides three main types of collections: **List**, **Set**, and **Map**.


## 1. Immutable vs. Mutable

This is the most important concept in Kotlin collections:

* **Immutable (Read-Only):** You can access the data, but you cannot add, remove, or update items. Created using functions like **listOf()**.
* **Mutable:** You can modify the contents. Created using functions like **mutableListOf()**.


## 2. Lists

A **List** is an ordered collection where elements can be accessed by their indices (starting from 0). Lists allow duplicate elements.

```kotlin
// Read-only list
val fruits = listOf("Apple", "Banana", "Cherry")
println(fruits[1]) // Output: Banana

// Mutable list
val animals = mutableListOf("Lion", "Tiger")
animals.add("Bear")
animals.removeAt(0)
```


## 3. Sets

A **Set** is a collection of **unique** elements. It does not allow duplicates. The order of elements is generally not guaranteed (unless using a **LinkedHashSet**).

```kotlin
val numbers = setOf(1, 2, 3, 3, 3) 
println(numbers.size) // Output: 3 (duplicates are ignored)

val mutableSet = mutableSetOf("A", "B")
mutableSet.add("A") // No effect, "A" already exists
```


## 4. Maps

A **Map** (or Dictionary) holds pairs of **Keys** and **Values**. Keys must be unique, but values can be duplicated.

```kotlin
// Read-only map (Key to Value)
val airPorts = mapOf("LHR" to "London", "JFK" to "New York")

// Mutable map
val userScores = mutableMapOf("Alex" to 10, "Samy" to 20)
userScores["Alex"] = 15 // Update value
userScores["John"] = 5  // Add new pair
```


## 5. Common Collection Operations

Kotlin provides a rich set of "functional" operators to transform and filter data without using manual **for** loops.

| Operator        | Description                                          |
| --------------- | ---------------------------------------------------- |
| **filter**      | Returns a list of elements matching a condition.     |
| **map**         | Transforms each element into something else.         |
| **any**         | Returns **true** if at least one element matches.    |
| **count**       | Returns the number of elements matching a condition. |
| **firstOrNull** | Safely gets the first element or returns null.       |

```kotlin
val numbers = listOf(1, 2, 3, 4, 5, 6)
val evenNumbers = numbers.filter { it % 2 == 0 } // [2, 4, 6]
val doubled = numbers.map { it * 2 }            // [2, 4, 6, 8, 10, 12]
```


### Summary

* **List**: Ordered, allows duplicates.
* **Set**: Unordered, unique elements only.
* **Map**: Key-Value pairs.
* Always prefer **Read-Only** collections (**listOf**) unless you specifically need to change the data.
* Use **Functional Operators** like **filter** and **map** for cleaner code.

