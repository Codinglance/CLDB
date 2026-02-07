
# Classes & Objects

A **Class** is a blueprint for creating objects. An **Object** is an instance of that blueprint.


## 1. Class Declaration

The most basic class consists of the **class** keyword and a name.

```kotlin
class User {
    // Properties and methods go here
}
```

To create an instance (object), we call the constructor like a function. **Note:** Kotlin does not use the **new** keyword.

```kotlin
val myUser = User()
```


## 2. Constructors

Kotlin distinguishes between a **Primary Constructor** and **Secondary Constructors**.

### Primary Constructor

The primary constructor is part of the class header. It initializes the class and defines properties directly.

```kotlin
class Car(val brand: String, var speed: Int)

// Usage
val myCar = Car("Toyota", 120)
println(myCar.brand) // Output: Toyota
```

### Initializer Blocks (**init**)

The primary constructor cannot contain any code. If you need initialization logic, use the **init** block.

```kotlin
class Car(val brand: String) {
    init {
        println("Car $brand is being created!")
    }
}
```


## 3. Properties: Getters and Setters

In Kotlin, when you declare a property, the compiler automatically generates getters and setters for you.

* **val:** Generates a **getter** (read-only).
* **var:** Generates both a **getter** and a **setter**.

You can also write custom accessors if needed:

```kotlin
class Rectangle(val width: Int, val height: Int) {
    val isSquare: Boolean
        get() = width == height // Custom getter
}
```


## 4. Visibility Modifiers

Kotlin uses modifiers to restrict access to class members:

| Modifier      | Description                                    |
| ------------- | ---------------------------------------------- |
| **public**    | Visible everywhere (Default).                  |
| **private**   | Visible only inside the class.                 |
| **protected** | Visible in the class and its subclasses.       |
| **internal**  | Visible only within the same module (Project). |


## 5. Constructors and Default Values

Just like functions, class constructors can have default values. This makes your classes very flexible without requiring multiple "overloaded" constructors.

```kotlin
class Button(val text: String, val color: String = "Gray")

val saveBtn = Button("Save")            // Uses default "Gray"
val deleteBtn = Button("Delete", "Red") // Overrides default
```


## 6. Abstract Classes

An **abstract** class cannot be instantiated. It is meant to be a base for other classes to inherit from.

```kotlin
abstract class Shape {
    abstract fun calculateArea(): Double
}
```


### Summary

* Use **class** to define a blueprint.
* **Primary constructors** are defined in the class header.
* **init** blocks handle initialization logic.
* **Properties** (**val** / **var**) handle data and automatically provide getters/setters.
* No **new** keyword is required to create an object.

