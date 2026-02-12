
## 1. Calling Java from Kotlin

When you call Java code from Kotlin, most things work exactly as you’d expect. However, Kotlin adds some “syntactic sugar” to make Java code look like native Kotlin.

### Getters and Setters

If a Java class has methods following the getter/setter convention (e.g., **getName()** and **setName()**), Kotlin treats them as **properties**.

```kotlin
// Java Code: user.getName();
// Kotlin Code:
val name = user.name 

// Java Code: user.setName("Alex");
// Kotlin Code:
user.name = "Alex"
```



### Nullability in Java

Java doesn't have null safety built into the type system. When you call Java code, Kotlin sees the types as **Platform Types** (marked with **!**, like **String!**).

* A platform type means Kotlin doesn't know if the value is nullable or not.
* **Best Practice:** Always check the Java documentation or annotations (**@Nullable** / **@NonNull**) and treat the value as nullable in Kotlin if you aren't sure.


## 2. Calling Kotlin from Java

To make Kotlin code look natural to a Java developer, Kotlin provides several specialized annotations.

### **@JvmStatic**

By default, Kotlin **companion object** members are compiled as nested class fields. Use **@JvmStatic** to make them true static methods in Java.

```kotlin
// Kotlin
class Utils {
    companion object {
        @JvmStatic fun doWork() { ... }
    }
}

// Java usage
Utils.doWork(); // Without the annotation, you'd need Utils.Companion.doWork();
```


### **@JvmOverloads**

Kotlin's **Default Arguments** don't exist in Java. Java would normally only see the version of the function with **all** arguments. This annotation tells the compiler to generate multiple overloaded versions for Java.

```kotlin
// Kotlin
@JvmOverloads
fun draw(width: Int, height: Int = 100) { ... }

// Java now sees:
// void draw(int width, int height)
// void draw(int width)
```


## 3. Key Syntax Differences

If you are converting a Java file to Kotlin (using Android Studio’s **Ctrl+Alt+Shift+K**), here are the major shifts:

| Feature                  | Java                      | Kotlin                        |
| ------------------------ | ------------------------- | ----------------------------- |
| **Semicolons**           | Required (**;**)          | Not required                  |
| **Variable Declaration** | **String name = "Alex";** | **val name: String = "Alex"** |
| **Ternary Operator**     | **a ? b : c**             | **if (a) b else c**           |
| **Switch vs When**       | **switch(x) { ... }**     | **when(x) { ... }**           |
| **Casting**              | **(String) obj**          | **obj as String**             |
| **Static Members**       | **static** keyword        | **companion object**          |


## 4. The **Any** vs **Object**

In Java, the root of the hierarchy is **Object**. In Kotlin, it is **Any**. While they serve the same purpose, **Any** does not have methods like **wait()** or **notify()**. If you need those, you must cast the object to **java.lang.Object**.



## 5. SAM Conversions (Single Abstract Method)

Kotlin makes working with Java interfaces (like **OnClickListener**) incredibly easy. If a Java interface has exactly one method, you can pass a lambda instead of an anonymous inner class.

```java
// Java:
button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        doSomething();
    }
});
```

```kotlin
// Kotlin (SAM Conversion):
button.setOnClickListener { v -> doSomething() }
```


### Summary

* **Interoperability:** You can mix Java and Kotlin freely in Android Studio.
* **Properties:** Kotlin automatically turns Java getters/setters into properties.
* **Annotations:** Use **@JvmStatic** and **@JvmOverloads** to make Kotlin code Java-friendly.
* **Platform Types:** Be careful with nulls when receiving data from Java code.


