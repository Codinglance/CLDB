
## 1. Inheritance

Inheritance allows a class (subclass) to inherit properties and methods from another class (parent or superclass).

### The **open** Keyword

In Kotlin, you must explicitly mark a class as **open** to allow other classes to inherit from it.

```kotlin
open class Vehicle(val brand: String) {
    fun drive() {
        println("The vehicle is moving")
    }
}

// Use a colon (:) to inherit
class ElectricCar(brand: String) : Vehicle(brand)
```


### Overriding Methods

To allow a subclass to change a method's behavior, the parent method must also be marked **open**. The subclass must use the **override** keyword.

```kotlin
open class Vehicle {
    open fun startEngine() {
        println("Starting standard engine...")
    }
}

class Tesla : Vehicle() {
    override fun startEngine() {
        println("Starting electric motor...")
    }
}
```


## 2. Interfaces

An **Interface** is a contract. It defines a set of properties or methods that a class *must* implement. Unlike classes, a class can implement **multiple** interfaces.

```kotlin
interface Flyable {
    val speed: Int // Abstract property
    fun fly()      // Abstract method
    
    // Interfaces can have default method implementations
    fun logFlight() {
        println("Flight logged at $speed km/h")
    }
}

class Bird(override val speed: Int) : Flyable {
    override fun fly() {
        println("Flapping wings...")
    }
}
```


## 3. Abstract Classes vs Interfaces

It can be confusing to choose between the two. Here is a quick breakdown:

| Feature         | Abstract Class                 | Interface                              |
| --------------- | ------------------------------ | -------------------------------------- |
| **State**       | Can hold state (fields).       | Cannot hold state (no backing fields). |
| **Inheritance** | A class can inherit only one.  | A class can implement many.            |
| **Purpose**     | Defines what an object **is**. | Defines what an object **can do**.     |


## 4. The **super** Keyword

If you want to call a method from the parent class inside an overridden method, use the **super** keyword.

```kotlin
override fun startEngine() {
    super.startEngine() // Runs the parent logic
    println("System check complete.")
}
```


## 5. Composition over Inheritance

In modern Android development, it is often better to use **Composition** (wrapping a class) rather than **Inheritance** to avoid deep, messy hierarchies.

 **Rule of Thumb:** If a **Cat** **is an** **Animal**, use inheritance. If a **User** **has an** **Address**, use composition.


### Summary

* Classes are **final** (closed) by default; use **open** to allow inheritance.
* Use **override** to redefine parent methods.
* **Interfaces** allow for shared behavior across unrelated classes.
* Interfaces can provide **default method bodies**, but they cannot store data.

