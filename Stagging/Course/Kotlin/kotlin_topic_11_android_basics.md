
## 1. The Activity: The Entry Point

In Android, an **Activity** represents a single screen with a user interface. In Kotlin, your Activity class must inherit from **AppCompatActivity**.

```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main) // Links the XML layout
    }
}
```

* **onCreate**: This is where the Activity is initialized.
* **setContentView**: This tells the Activity which XML file to display.


## 2. Accessing Views (XML to Kotlin)

In modern Android development, there are several ways to connect your XML views (like Buttons or TextViews) to your Kotlin code.

### A. **findViewById** (The Traditional Way)

This is the standard method built into the Android SDK.

```kotlin
val myButton: Button = findViewById(R.id.btn_submit)
myButton.setOnClickListener {
    // Handle click
}
```


### B. View Binding (The Recommended Way)

View Binding generates a binding class for every XML layout file in your project. It is safer and prevents **NullPointerExceptions** if a view ID is missing.

```kotlin
// Example for activity_main.xml
private lateinit var binding: ActivityMainBinding

override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    binding = ActivityMainBinding.inflate(layoutInflater)
    setContentView(binding.root)

    binding.btnSubmit.text = "Click Me"
}
```


## 3. The **lateinit** Keyword

You will see **lateinit var** used constantly in Android. Since Android UI components are often initialized in **onCreate** (not the constructor), **lateinit** tells Kotlin: *"I won't initialize this variable right now, but I promise to do it before I use it."*


## 4. Handling Click Listeners with Lambdas

Because Kotlin supports functional programming, setting up button clicks is very concise using the trailing lambda syntax we learned in the previous module.

```kotlin
binding.myButton.setOnClickListener {
    Toast.makeText(this, "Button Clicked!", Toast.LENGTH_SHORT).show()
}
```


## 5. Logcat: Debugging your Kotlin Code

To see what's happening behind the scenes, use the **Log** class. This is essential for tracking data flow in Android.

```kotlin
Log.d("MainActivity", "User clicked the button") // Debug
Log.e("MainActivity", "Error loading data")     // Error
```


## 6. String Resources & Context

Never hardcode strings in your Kotlin code. Use the **getString()** method to fetch values from **strings.xml**.

```kotlin
// ❌ Bad: val label = "Welcome"
// ✅ Good:
val label = getString(R.string.welcome_message)
```



### Summary

* **Activities** are the building blocks of your app UI.
* **lateinit** is used for variables that are initialized in **onCreate**.
* **View Binding** is the modern standard for interacting with XML from Kotlin.
* **Lambdas** make event handling (like **setOnClickListener**) clean and readable.
