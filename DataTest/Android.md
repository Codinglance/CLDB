[//]: # ()
[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣ What is Android?)

[//]: # ()
[//]: # (Android is an **open-source mobile operating system** developed by Google, based on the Linux kernel.  )

[//]: # (It is used to build applications for smartphones, tablets, TVs, wearables, and IoT devices.)

[//]: # ()
[//]: # (### Key Features)

[//]: # (- Open-source and customizable)

[//]: # (- Supports Java, Kotlin, and C++)

[//]: # (- Component-based architecture)

[//]: # (- Large app ecosystem &#40;Google Play&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣ What is Context? How is it used?)

[//]: # ()
[//]: # (`Context` represents the environment in which an app is running.  )

[//]: # (It provides access to app resources, system services, and application-level operations.)

[//]: # ()
[//]: # (### Uses of Context)

[//]: # (- Access resources &#40;strings, colors, layouts&#41;)

[//]: # (- Start Activities and Services)

[//]: # (- Show Toasts and Dialogs)

[//]: # (- Access system services)

[//]: # ()
[//]: # (### Example)

[//]: # (```kotlin)

[//]: # (Toast.makeText&#40;this, "Hello Android", Toast.LENGTH_SHORT&#41;.show&#40;&#41;)

[//]: # (````)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3️⃣ What is Application Context?)

[//]: # ()
[//]: # (Application Context is tied to the **lifecycle of the entire application**.)

[//]: # ()
[//]: # (### Characteristics)

[//]: # ()
[//]: # (* Exists as long as the app is running)

[//]: # (* Not tied to any UI component)

[//]: # (* Used for long-lived operations)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val context = applicationContext)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4️⃣ What is Activity Context?)

[//]: # ()
[//]: # (Activity Context is tied to the **lifecycle of an Activity**.)

[//]: # ()
[//]: # (### Characteristics)

[//]: # ()
[//]: # (* Exists only while the Activity is alive)

[//]: # (* Used for UI-related operations)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val context = this // inside Activity)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5️⃣ Tell all Android application components.)

[//]: # ()
[//]: # (Android has four main application components:)

[//]: # ()
[//]: # (### 🔹 Activity)

[//]: # ()
[//]: # (* Represents a UI screen)

[//]: # (* Handles user interaction)

[//]: # ()
[//]: # (### 🔹 Service)

[//]: # ()
[//]: # (* Performs background tasks)

[//]: # (* No UI)

[//]: # ()
[//]: # (### 🔹 Broadcast Receiver)

[//]: # ()
[//]: # (* Responds to system-wide events)

[//]: # (* Example: network change, battery low)

[//]: # ()
[//]: # (### 🔹 Content Provider)

[//]: # ()
[//]: # (* Manages and shares app data)

[//]: # (* Example: Contacts provider)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6️⃣ What is AndroidManifest.xml?)

[//]: # ()
[//]: # (`AndroidManifest.xml` is the configuration file of an Android app.)

[//]: # ()
[//]: # (### It defines:)

[//]: # ()
[//]: # (* App components &#40;Activities, Services, Receivers&#41;)

[//]: # (* Permissions)

[//]: # (* App entry point)

[//]: # (* Package name)

[//]: # (* SDK versions)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```xml)

[//]: # (<manifest package="com.example.app">)

[//]: # ()
[//]: # (    <uses-permission android:name="android.permission.INTERNET"/>)

[//]: # ()
[//]: # (    <application>)

[//]: # (        <activity android:name=".MainActivity">)

[//]: # (            <intent-filter>)

[//]: # (                <action android:name="android.intent.action.MAIN"/>)

[//]: # (                <category android:name="android.intent.category.LAUNCHER"/>)

[//]: # (            </intent-filter>)

[//]: # (        </activity>)

[//]: # (    </application>)

[//]: # ()
[//]: # (</manifest>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7️⃣ What is Application class?)

[//]: # ()
[//]: # (The `Application` class represents the **global state of the app**.)

[//]: # (It is created before any Activity or Service.)

[//]: # ()
[//]: # (### Use Cases)

[//]: # ()
[//]: # (* Initialize libraries &#40;Firebase, DI, Analytics&#41;)

[//]: # (* Store global data)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyApp : Application&#40;&#41; {)

[//]: # (    override fun onCreate&#40;&#41; {)

[//]: # (        super.onCreate&#40;&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8️⃣ What is ADB in Android?)

[//]: # ()
[//]: # (ADB &#40;Android Debug Bridge&#41; is a command-line tool used to communicate with Android devices.)

[//]: # ()
[//]: # (### Uses)

[//]: # ()
[//]: # (* Install/uninstall apps)

[//]: # (* Debug apps)

[//]: # (* Execute shell commands)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```bash)

[//]: # (adb install app.apk)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9️⃣ What is AAPT &#40;Android Asset Packaging Tool&#41;?)

[//]: # ()
[//]: # (AAPT is a build tool that compiles and packages Android app resources.)

[//]: # ()
[//]: # (### Responsibilities)

[//]: # ()
[//]: # (* Compile XML resources)

[//]: # (* Generate R.java / R.class)

[//]: # (* Package APK or AAB)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 🔟 What is DEX file?)

[//]: # ()
[//]: # (DEX &#40;Dalvik Executable&#41; file contains compiled bytecode of Android apps.)

[//]: # (Java/Kotlin code is converted into DEX format for execution by Android Runtime &#40;ART&#41;.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣1️⃣ What is Multidex?)

[//]: # ()
[//]: # (Multidex allows an app to contain multiple DEX files when method count exceeds 65,536.)

[//]: # ()
[//]: # (### Why needed?)

[//]: # ()
[//]: # (Large apps exceed the single DEX limit.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```gradle)

[//]: # (multiDexEnabled true)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣2️⃣ What are processes in Android?)

[//]: # ()
[//]: # (A process is an instance of a running application.)

[//]: # (Android assigns priority to processes based on their importance.)

[//]: # ()
[//]: # (### Process Priority Order)

[//]: # ()
[//]: # (1. Foreground process)

[//]: # (2. Visible process)

[//]: # (3. Service process)

[//]: # (4. Background process)

[//]: # (5. Empty process)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣3️⃣ Is it possible to run an Android app in multiple processes? How?)

[//]: # ()
[//]: # (Yes ✅)

[//]: # ()
[//]: # (### How?)

[//]: # ()
[//]: # (By specifying `android:process` in `AndroidManifest.xml`.)

[//]: # ()
[//]: # (```xml)

[//]: # (<activity)

[//]: # (    android:name=".MainActivity")

[//]: # (    android:process=":remote" />)

[//]: # (```)

[//]: # ()
[//]: # (### Use Cases)

[//]: # ()
[//]: # (* Isolate heavy tasks)

[//]: # (* Improve stability)

[//]: # (* IPC &#40;Inter-Process Communication&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣4️⃣ How is memory managed in Android OS?)

[//]: # ()
[//]: # (Android uses automatic memory management through **Garbage Collection &#40;GC&#41;**.)

[//]: # ()
[//]: # (### Memory Management Features)

[//]: # ()
[//]: # (* Heap memory allocation)

[//]: # (* Garbage Collector)

[//]: # (* Low Memory Killer &#40;LMK&#41;)

[//]: # (* Process termination when memory is low)

[//]: # ()
[//]: # (### Best Practices)

[//]: # ()
[//]: # (* Avoid memory leaks)

[//]: # (* Use ViewBinding instead of findViewById)

[//]: # (* Release resources in lifecycle methods)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣5️⃣ What is StrictMode?)

[//]: # ()
[//]: # (StrictMode is a developer tool used to detect bad practices in Android apps.)

[//]: # ()
[//]: # (### Detects)

[//]: # ()
[//]: # (* Disk I/O on main thread)

[//]: # (* Network calls on main thread)

[//]: # (* Memory leaks)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (StrictMode.setThreadPolicy&#40;)

[//]: # (    StrictMode.ThreadPolicy.Builder&#40;&#41;.detectAll&#40;&#41;.penaltyLog&#40;&#41;.build&#40;&#41;)

[//]: # (&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣6️⃣ What is Lint?)

[//]: # ()
[//]: # (Lint is a static code analysis tool that checks Android code for bugs, performance issues, and best practices.)

[//]: # ()
[//]: # (### Detects)

[//]: # ()
[//]: # (* Unused resources)

[//]: # (* Performance issues)

[//]: # (* Security vulnerabilities)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣7️⃣ What is Support Library? Why was it introduced?)

[//]: # ()
[//]: # (The Android Support Library &#40;now AndroidX&#41; provides backward-compatible features for older Android versions.)

[//]: # ()
[//]: # (### Why introduced?)

[//]: # ()
[//]: # (* New APIs not available in old Android versions)

[//]: # (* Consistent behavior across devices)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```gradle)

[//]: # (implementation "androidx.appcompat:appcompat:1.6.1")

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣8️⃣ What is Doze Mode? What is App Standby?)

[//]: # ()
[//]: # (### 🔹 Doze Mode)

[//]: # ()
[//]: # (Introduced in Android 6.0 to save battery when the device is idle.)

[//]: # ()
[//]: # (### Effects)

[//]: # ()
[//]: # (* Restricts background CPU and network usage)

[//]: # (* Delays jobs and alarms)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔹 App Standby)

[//]: # ()
[//]: # (Restricts background activities of unused apps.)

[//]: # ()
[//]: # (### Effects)

[//]: # ()
[//]: # (* Limits background execution)

[//]: # (* Saves battery)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣9️⃣ What is File, Class, and Activity in Android?)

[//]: # ()
[//]: # (### 🔹 File)

[//]: # ()
[//]: # (A file is a physical resource stored in the project &#40;e.g., XML, Kotlin, images&#41;.)

[//]: # ()
[//]: # (Example:)

[//]: # ()
[//]: # (* `MainActivity.kt`)

[//]: # (* `activity_main.xml`)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔹 Class)

[//]: # ()
[//]: # (A class is a blueprint for objects in Java/Kotlin.)

[//]: # ()
[//]: # (Example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class User&#40;val name: String&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔹 Activity)

[//]: # ()
[//]: # (An Activity is a UI component representing a screen.)

[//]: # ()
[//]: # (Example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MainActivity : AppCompatActivity&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣0️⃣ How to change parameters in an app without app update?)

[//]: # ()
[//]: # (This can be done using **Remote Configuration techniques**.)

[//]: # ()
[//]: # (### Common Methods)

[//]: # ()
[//]: # (1. Firebase Remote Config)

[//]: # (2. Server API configuration)

[//]: # (3. Feature flags)

[//]: # (4. Remote JSON config)

[//]: # ()
[//]: # (### Example &#40;Firebase Remote Config&#41;)

[//]: # ()
[//]: # (* Change UI text, features, or behavior without updating the app.)

[//]: # ()
[//]: # (### Benefits)

[//]: # ()
[//]: # (* Dynamic updates)

[//]: # (* A/B testing)

[//]: # (* Feature toggling)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (//here is other one)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣ What is Activity and its lifecycle?)

[//]: # ()
[//]: # (An **Activity** is a core Android component that represents a single screen with a user interface.)

[//]: # ()
[//]: # (### Activity Lifecycle Methods)

[//]: # ()
[//]: # (```kotlin)

[//]: # (onCreate&#40;&#41;   // Activity created)

[//]: # (onStart&#40;&#41;    // Activity becomes visible)

[//]: # (onResume&#40;&#41;   // Activity in foreground &#40;interactive&#41;)

[//]: # (onPause&#40;&#41;    // Activity partially visible)

[//]: # (onStop&#40;&#41;     // Activity no longer visible)

[//]: # (onDestroy&#40;&#41;  // Activity destroyed)

[//]: # (onRestart&#40;&#41;  // Activity restarting after stop)

[//]: # (````)

[//]: # ()
[//]: # (### Lifecycle Flow)

[//]: # ()
[//]: # (```)

[//]: # (onCreate → onStart → onResume)

[//]: # (                ↓)

[//]: # (            onPause → onStop → onDestroy)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣ Difference between onCreate&#40;&#41; and onStart&#40;&#41;)

[//]: # ()
[//]: # (| onCreate&#40;&#41;                           | onStart&#40;&#41;                                  |)

[//]: # (| ------------------------------------ | ------------------------------------------ |)

[//]: # (| Called once when Activity is created | Called every time Activity becomes visible |)

[//]: # (| Used for initialization              | Used to prepare UI                         |)

[//]: # (| Set content view                     | Register listeners                         |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3️⃣ When is only onDestroy&#40;&#41; called without onPause&#40;&#41; and onStop&#40;&#41;?)

[//]: # ()
[//]: # (⚠️ In normal lifecycle flow, `onDestroy&#40;&#41;` is **not called alone**.)

[//]: # (However, it may be called directly when:)

[//]: # ()
[//]: # (* System kills the process)

[//]: # (* finish&#40;&#41; is called before Activity is fully resumed)

[//]: # (* App crashes)

[//]: # ()
[//]: # (✅ Note: Android does not guarantee `onDestroy&#40;&#41;` execution.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4️⃣ Activity lifecycle when launched for the first time)

[//]: # ()
[//]: # (```)

[//]: # (onCreate → onStart → onResume)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5️⃣ Activity lifecycle when back button is pressed)

[//]: # ()
[//]: # (```)

[//]: # (onPause → onStop → onDestroy)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6️⃣ Activity lifecycle when launched again after back press)

[//]: # ()
[//]: # (A new instance is created:)

[//]: # ()
[//]: # (```)

[//]: # (onCreate → onStart → onResume)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7️⃣ Activity lifecycle when home button is pressed)

[//]: # ()
[//]: # (```)

[//]: # (onPause → onStop)

[//]: # (```)

[//]: # ()
[//]: # (&#40;Activity is kept in back stack, not destroyed&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8️⃣ Activity lifecycle when app returns from background)

[//]: # ()
[//]: # (```)

[//]: # (onRestart → onStart → onResume)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9️⃣ Lifecycle when navigating from Activity A → Activity B)

[//]: # ()
[//]: # (```)

[//]: # (Activity A: onPause&#40;&#41;)

[//]: # (Activity B: onCreate → onStart → onResume)

[//]: # (Activity A: onStop&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 🔟 Lifecycle when pressing back from Activity B → Activity A)

[//]: # ()
[//]: # (```)

[//]: # (Activity B: onPause → onStop → onDestroy)

[//]: # (Activity A: onRestart → onStart → onResume)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣1️⃣ How to preserve activity state during screen rotation?)

[//]: # ()
[//]: # (Use:)

[//]: # ()
[//]: # (* `onSaveInstanceState&#40;&#41;`)

[//]: # (* ViewModel)

[//]: # (* SavedStateHandle)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (override fun onSaveInstanceState&#40;outState: Bundle&#41; {)

[//]: # (    outState.putString&#40;"name", "Aasim"&#41;)

[//]: # (    super.onSaveInstanceState&#40;outState&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣2️⃣ What is savedInstanceState Bundle?)

[//]: # ()
[//]: # (`savedInstanceState` is a Bundle that stores UI state before Activity destruction.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (override fun onCreate&#40;savedInstanceState: Bundle?&#41; {)

[//]: # (    super.onCreate&#40;savedInstanceState&#41;)

[//]: # (    val name = savedInstanceState?.getString&#40;"name"&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣3️⃣ Difference between Intent and Bundle)

[//]: # ()
[//]: # (| Intent                   | Bundle                  |)

[//]: # (| ------------------------ | ----------------------- |)

[//]: # (| Used to start components | Used to pass data       |)

[//]: # (| Can carry Bundle         | Cannot start components |)

[//]: # (| Messaging object         | Key-value container     |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣4️⃣ What are launchModes?)

[//]: # ()
[//]: # (Launch modes define how Activities are created and managed in the back stack.)

[//]: # ()
[//]: # (### Types)

[//]: # ()
[//]: # (* standard &#40;default&#41;)

[//]: # (* singleTop)

[//]: # (* singleTask)

[//]: # (* singleInstance)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣5️⃣ Explain standard launchMode)

[//]: # ()
[//]: # (* Default mode)

[//]: # (* Always creates a new instance)

[//]: # ()
[//]: # (### Back stack example)

[//]: # ()
[//]: # (```)

[//]: # (A → B → C → B &#40;new instance&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣6️⃣ Explain singleTop launchMode)

[//]: # ()
[//]: # (* Reuses Activity if already on top of stack)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```)

[//]: # (A → B → C → B &#40;reuse if B is on top&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣7️⃣ Explain singleTask launchMode)

[//]: # ()
[//]: # (* Only one instance exists in a task)

[//]: # (* Clears above Activities)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```)

[//]: # (A → B → C → D → B)

[//]: # (Result: A → B)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣8️⃣ Explain singleInstance launchMode)

[//]: # ()
[//]: # (* Activity runs in a separate task)

[//]: # (* No other Activity in the same task)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣9️⃣ What are tasks and back stack?)

[//]: # ()
[//]: # (### Task)

[//]: # ()
[//]: # (A task is a collection of Activities that users interact with.)

[//]: # ()
[//]: # (### Back Stack)

[//]: # ()
[//]: # (A stack of Activities in LIFO order.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣0️⃣ What is taskAffinity?)

[//]: # ()
[//]: # (taskAffinity defines which task an Activity prefers to belong to.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```xml)

[//]: # (<activity)

[//]: # (    android:name=".MainActivity")

[//]: # (    android:taskAffinity="com.example.newtask" />)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣1️⃣ What is installLocation tag?)

[//]: # ()
[//]: # (Specifies where the app can be installed.)

[//]: # ()
[//]: # (### Values)

[//]: # ()
[//]: # (* auto)

[//]: # (* internalOnly)

[//]: # (* preferExternal)

[//]: # ()
[//]: # (```xml)

[//]: # (<manifest android:installLocation="auto">)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣2️⃣ Relationship between Activity and Fragment lifecycle)

[//]: # ()
[//]: # (Fragments have their own lifecycle but depend on Activity.)

[//]: # ()
[//]: # (### Example mapping)

[//]: # ()
[//]: # (| Activity    | Fragment                      |)

[//]: # (| ----------- | ----------------------------- |)

[//]: # (| onCreate&#40;&#41;  | onAttach&#40;&#41; → onCreate&#40;&#41;       |)

[//]: # (| onStart&#40;&#41;   | onStart&#40;&#41;                     |)

[//]: # (| onResume&#40;&#41;  | onResume&#40;&#41;                    |)

[//]: # (| onPause&#40;&#41;   | onPause&#40;&#41;                     |)

[//]: # (| onStop&#40;&#41;    | onStop&#40;&#41;                      |)

[//]: # (| onDestroy&#40;&#41; | onDestroyView&#40;&#41; → onDestroy&#40;&#41; |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣3️⃣ How do we save and restore an activity's state during screen rotation?)

[//]: # ()
[//]: # (### Steps)

[//]: # ()
[//]: # (1. Save state in `onSaveInstanceState&#40;&#41;`)

[//]: # (2. Restore state in `onCreate&#40;&#41;` or `onRestoreInstanceState&#40;&#41;`)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣4️⃣ What is a Bundle?)

[//]: # ()
[//]: # (A Bundle is a key-value pair data structure used to pass data between Android components.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val bundle = Bundle&#40;&#41;)

[//]: # (bundle.putInt&#40;"age", 25&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣5️⃣ When Activity A starts Activity B, explain the lifecycle order)

[//]: # ()
[//]: # (```)

[//]: # (Activity A: onPause&#40;&#41;)

[//]: # (Activity B: onCreate → onStart → onResume)

[//]: # (Activity A: onStop&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣6️⃣ How do you declare the launch mode in your application?)

[//]: # ()
[//]: # (### In AndroidManifest.xml)

[//]: # ()
[//]: # (```xml)

[//]: # (<activity)

[//]: # (    android:name=".MainActivity")

[//]: # (    android:launchMode="singleTask" />)

[//]: # (```)

[//]: # ()
[//]: # (### In Intent)

[//]: # ()
[//]: # (```kotlin)

[//]: # (intent.addFlags&#40;Intent.FLAG_ACTIVITY_SINGLE_TOP&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣7️⃣ How to know configChange happens in onDestroy?)

[//]: # ()
[//]: # (Use `isChangingConfigurations`.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (override fun onDestroy&#40;&#41; {)

[//]: # (    super.onDestroy&#40;&#41;)

[//]: # (    if &#40;isChangingConfigurations&#41; {)

[//]: # (        Log.d&#40;"ConfigChange", "Activity destroyed due to configuration change"&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # (//fragment)

[//]: # ()
[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣ What is Fragment?)

[//]: # ()
[//]: # (A **Fragment** is a reusable portion of UI that represents a part of an Activity’s interface and behavior.)

[//]: # ()
[//]: # (### Key Points)

[//]: # (- Fragment cannot exist without an Activity.)

[//]: # (- It has its own lifecycle.)

[//]: # (- Used for modular and reusable UI.)

[//]: # (- Supports multi-pane layouts &#40;tablet, foldables&#41;.)

[//]: # ()
[//]: # (### Example)

[//]: # (```kotlin)

[//]: # (class HomeFragment : Fragment&#40;R.layout.fragment_home&#41;)

[//]: # (````)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2️⃣ Fragment Lifecycle)

[//]: # ()
[//]: # (Fragments have a lifecycle similar to Activities but with additional callbacks.)

[//]: # ()
[//]: # (### Lifecycle Methods)

[//]: # ()
[//]: # (```kotlin)

[//]: # (onAttach&#40;&#41;        // Fragment attached to Activity)

[//]: # (onCreate&#40;&#41;        // Fragment created)

[//]: # (onCreateView&#40;&#41;    // UI created)

[//]: # (onViewCreated&#40;&#41;   // View ready)

[//]: # (onStart&#40;&#41;         // Fragment visible)

[//]: # (onResume&#40;&#41;        // Fragment active)

[//]: # (onPause&#40;&#41;         // Fragment partially visible)

[//]: # (onStop&#40;&#41;          // Fragment hidden)

[//]: # (onDestroyView&#40;&#41;   // View destroyed)

[//]: # (onDestroy&#40;&#41;       // Fragment destroyed)

[//]: # (onDetach&#40;&#41;        // Fragment detached from Activity)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3️⃣ Why is it recommended to use only the default constructor in Fragment?)

[//]: # ()
[//]: # (Fragments must have a **public empty constructor** because Android may recreate them during configuration changes or process death.)

[//]: # ()
[//]: # (### ❌ Wrong Approach)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyFragment&#40;val name: String&#41; : Fragment&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ Correct Approach)

[//]: # ()
[//]: # (Use `newInstance&#40;&#41;` with Bundle.)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyFragment : Fragment&#40;&#41; {)

[//]: # ()
[//]: # (    companion object {)

[//]: # (        fun newInstance&#40;name: String&#41;: MyFragment {)

[//]: # (            val fragment = MyFragment&#40;&#41;)

[//]: # (            val bundle = Bundle&#40;&#41;)

[//]: # (            bundle.putString&#40;"name", name&#41;)

[//]: # (            fragment.arguments = bundle)

[//]: # (            return fragment)

[//]: # (        })

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4️⃣ Fragment lifecycle when launched)

[//]: # ()
[//]: # (```)

[//]: # (onAttach → onCreate → onCreateView → onViewCreated → onStart → onResume)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5️⃣ Fragment lifecycle when back button is pressed)

[//]: # ()
[//]: # (If Fragment is in back stack:)

[//]: # ()
[//]: # (```)

[//]: # (onPause → onStop → onDestroyView)

[//]: # (```)

[//]: # ()
[//]: # (If Fragment is removed completely:)

[//]: # ()
[//]: # (```)

[//]: # (onPause → onStop → onDestroyView → onDestroy → onDetach)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6️⃣ Fragment lifecycle when home button is pressed)

[//]: # ()
[//]: # (```)

[//]: # (onPause → onStop)

[//]: # (```)

[//]: # ()
[//]: # (&#40;Fragment remains in memory&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7️⃣ Fragment lifecycle when returning from background)

[//]: # ()
[//]: # (```)

[//]: # (onStart → onResume)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8️⃣ Difference between Fragment and Activity)

[//]: # ()
[//]: # (| Fragment            | Activity                |)

[//]: # (| ------------------- | ----------------------- |)

[//]: # (| Part of an Activity | Independent component   |)

[//]: # (| Cannot exist alone  | Can exist independently |)

[//]: # (| Lightweight         | Heavy component         |)

[//]: # (| Reusable UI         | Full screen UI          |)

[//]: # (| Child of Activity   | Parent container        |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9️⃣ When should you use Fragment instead of Activity?)

[//]: # ()
[//]: # (Use Fragment when:)

[//]: # ()
[//]: # (* Building modular UI)

[//]: # (* Supporting multiple screen sizes)

[//]: # (* Implementing single-activity architecture)

[//]: # (* Reusing UI components)

[//]: # (* Using ViewPager / Navigation Component)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 🔟 Difference between add and replace Fragment in back stack)

[//]: # ()
[//]: # (### add&#40;&#41;)

[//]: # ()
[//]: # (* Adds Fragment on top of existing Fragment)

[//]: # (* Previous Fragment remains in memory and visible &#40;if not hidden&#41;)

[//]: # ()
[//]: # (### replace&#40;&#41;)

[//]: # ()
[//]: # (* Removes current Fragment and adds new Fragment)

[//]: # (* Previous Fragment is destroyed &#40;view&#41;)

[//]: # ()
[//]: # (| add&#40;&#41;                      | replace&#40;&#41;                   |)

[//]: # (| -------------------------- | --------------------------- |)

[//]: # (| Multiple fragments coexist | Only one fragment at a time |)

[//]: # (| Faster UI switching        | Cleaner UI                  |)

[//]: # (| More memory usage          | Less memory usage           |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣1️⃣ What is Retained Fragment / Headless Fragment?)

[//]: # ()
[//]: # (A **Retained Fragment** is a Fragment that survives configuration changes.)

[//]: # ()
[//]: # (### Characteristics)

[//]: # ()
[//]: # (* No UI &#40;Headless Fragment&#41;)

[//]: # (* Used to retain data across configuration changes)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (setRetainInstance&#40;true&#41;)

[//]: # (```)

[//]: # ()
[//]: # (⚠️ Deprecated in modern Android → replaced by ViewModel.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣2️⃣ Purpose of addToBackStack&#40;&#41; in FragmentTransaction)

[//]: # ()
[//]: # (`addToBackStack&#40;&#41;` adds a Fragment transaction to the back stack, allowing users to navigate back.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (supportFragmentManager.beginTransaction&#40;&#41;)

[//]: # (    .replace&#40;R.id.container, SecondFragment&#40;&#41;&#41;)

[//]: # (    .addToBackStack&#40;null&#41;)

[//]: # (    .commit&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### Without addToBackStack&#40;&#41;)

[//]: # ()
[//]: # (* Back button closes Activity.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣3️⃣ How to communicate between two Fragments?)

[//]: # ()
[//]: # (### ✅ Best Approaches)

[//]: # ()
[//]: # (#### 1. Shared ViewModel &#40;Recommended&#41;)

[//]: # ()
[//]: # (* Both fragments share same ViewModel.)

[//]: # ()
[//]: # (#### 2. Interface Callback)

[//]: # ()
[//]: # (* Fragment communicates via Activity.)

[//]: # ()
[//]: # (#### 3. Fragment Result API)

[//]: # ()
[//]: # (* Modern solution.)

[//]: # ()
[//]: # (### Example &#40;Fragment Result API&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (parentFragmentManager.setFragmentResult&#40;"key", bundleOf&#40;"data" to "Hello"&#41;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣4️⃣ How to share ViewModel between fragments?)

[//]: # ()
[//]: # (Use `activityViewModels&#40;&#41;`.)

[//]: # ()
[//]: # (### Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class SharedViewModel : ViewModel&#40;&#41; {)

[//]: # (    val data = MutableLiveData<String>&#40;&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val viewModel: SharedViewModel by activityViewModels&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1️⃣5️⃣ Difference between Dialog and DialogFragment)

[//]: # ()
[//]: # (| Dialog               | DialogFragment                 |)

[//]: # (| -------------------- | ------------------------------ |)

[//]: # (| UI popup component   | Fragment wrapper around Dialog |)

[//]: # (| Not lifecycle-aware  | Lifecycle-aware                |)

[//]: # (| Manual management    | Managed by FragmentManager     |)

[//]: # (| Risk of memory leaks | Safer                          |)

[//]: # ()
[//]: # (### Example DialogFragment)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyDialogFragment : DialogFragment&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # (///intent)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ Android Intent & Broadcast – Explained with Tags + Examples)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is Intent?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Intent is a messaging object used to request an action from another component &#40;Activity, Service, BroadcastReceiver&#41;.)

[//]: # ()
[//]: # (✅ **Used Class / Tag:**)

[//]: # (`android.content.Intent`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;this, SecondActivity::class.java&#41;)

[//]: # (startActivity&#40;intent&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; What is Explicit Intent?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Intent where you specify the exact target component &#40;class name&#41;.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`Intent&#40;Context, TargetClass::class.java&#41;`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;this, ProfileActivity::class.java&#41;)

[//]: # (startActivity&#40;intent&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; What is Implicit Intent?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Intent where the target component is not specified, but the action is defined.)

[//]: # ()
[//]: # (✅ **Used Tags / Actions:**)

[//]: # (`Intent.ACTION_VIEW`, `Intent.ACTION_SEND`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;Intent.ACTION_VIEW&#41;)

[//]: # (intent.data = Uri.parse&#40;"https://google.com"&#41;)

[//]: # (startActivity&#40;intent&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; What is Sticky Intent?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Sticky Intent remains in the system after being broadcast, so future receivers can access it.)

[//]: # ()
[//]: # (⚠️ Deprecated in modern Android.)

[//]: # ()
[//]: # (✅ **Used Method:**)

[//]: # (`sendStickyBroadcast&#40;&#41;`)

[//]: # ()
[//]: # (✅ **Example &#40;Not recommended&#41;:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;"MY_ACTION"&#41;)

[//]: # (sendStickyBroadcast&#40;intent&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; What is PendingIntent?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A token that allows another app or system to execute your Intent later on your behalf.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`android.app.PendingIntent`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;this, MainActivity::class.java&#41;)

[//]: # (val pendingIntent = PendingIntent.getActivity&#40;)

[//]: # (    this, 0, intent, PendingIntent.FLAG_UPDATE_CURRENT)

[//]: # (&#41;)

[//]: # (```)

[//]: # ()
[//]: # (📌 Used in: Notifications, Alarms, Widgets.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; What is IntentFilter?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Declares which Intents a component can respond to.)

[//]: # ()
[//]: # (✅ **Used Tag &#40;Manifest&#41;:**)

[//]: # (`<intent-filter>`)

[//]: # ()
[//]: # (✅ **Example &#40;AndroidManifest.xml&#41;:**)

[//]: # ()
[//]: # (```xml)

[//]: # (<activity android:name=".MainActivity">)

[//]: # (    <intent-filter>)

[//]: # (        <action android:name="android.intent.action.MAIN"/>)

[//]: # (        <category android:name="android.intent.category.LAUNCHER"/>)

[//]: # (    </intent-filter>)

[//]: # (</activity>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; What is BroadcastReceiver?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A component that listens for system-wide or app-specific broadcast messages.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`BroadcastReceiver`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyReceiver : BroadcastReceiver&#40;&#41; {)

[//]: # (    override fun onReceive&#40;context: Context, intent: Intent&#41; {)

[//]: # (        Log.d&#40;"Receiver", "Broadcast received"&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (Register in Manifest:)

[//]: # ()
[//]: # (```xml)

[//]: # (<receiver android:name=".MyReceiver"/>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8&#41; What is LocalBroadcastManager?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Used to send broadcasts within the same app only &#40;more secure & efficient&#41;.)

[//]: # ()
[//]: # (⚠️ Deprecated → Use Flow / LiveData / SharedViewModel instead.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`LocalBroadcastManager`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (LocalBroadcastManager.getInstance&#40;this&#41;)

[//]: # (    .sendBroadcast&#40;Intent&#40;"MY_LOCAL_ACTION"&#41;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9&#41; Types of Broadcasts in Android)

[//]: # ()
[//]: # (### ✅ a&#41; Normal Broadcast)

[//]: # ()
[//]: # (* Delivered to all receivers simultaneously.)

[//]: # ()
[//]: # (### ✅ b&#41; Ordered Broadcast)

[//]: # ()
[//]: # (* Delivered one by one based on priority.)

[//]: # ()
[//]: # (### ✅ c&#41; Sticky Broadcast)

[//]: # ()
[//]: # (* Remains in system memory.)

[//]: # ()
[//]: # (### ✅ d&#41; Local Broadcast)

[//]: # ()
[//]: # (* Inside the same app only.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 10&#41; Difference between Normal vs Ordered Broadcast)

[//]: # ()
[//]: # (| Feature              | Normal Broadcast | Ordered Broadcast      |)

[//]: # (| -------------------- | ---------------- | ---------------------- |)

[//]: # (| Delivery             | Simultaneous     | Sequential             |)

[//]: # (| Priority             | No               | Yes                    |)

[//]: # (| Can stop propagation | ❌ No             | ✅ Yes                  |)

[//]: # (| Method               | sendBroadcast&#40;&#41;  | sendOrderedBroadcast&#40;&#41; |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (sendBroadcast&#40;Intent&#40;"ACTION_NORMAL"&#41;&#41;)

[//]: # (sendOrderedBroadcast&#40;Intent&#40;"ACTION_ORDERED"&#41;, null&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 11&#41; How can two Android apps interact?)

[//]: # ()
[//]: # (✅ Methods:)

[//]: # ()
[//]: # (### ✅ a&#41; Implicit Intent)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;Intent.ACTION_SEND&#41;)

[//]: # (intent.type = "text/plain")

[//]: # (startActivity&#40;intent&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ b&#41; Content Provider)

[//]: # ()
[//]: # (* Share data using URI.)

[//]: # ()
[//]: # (### ✅ c&#41; BroadcastReceiver)

[//]: # ()
[//]: # (* App-to-app communication.)

[//]: # ()
[//]: # (### ✅ d&#41; Deep Links)

[//]: # ()
[//]: # (* Open another app using URL.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 12&#41; What is Deeplink?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A URL that opens a specific screen inside an app instead of the browser.)

[//]: # ()
[//]: # (✅ **Used Tags:**)

[//]: # (`<data>`, `<intent-filter>`)

[//]: # ()
[//]: # (✅ **Example &#40;Manifest&#41;:**)

[//]: # ()
[//]: # (```xml)

[//]: # (<activity android:name=".ProductActivity">)

[//]: # (    <intent-filter>)

[//]: # (        <action android:name="android.intent.action.VIEW"/>)

[//]: # (        <category android:name="android.intent.category.DEFAULT"/>)

[//]: # (        <category android:name="android.intent.category.BROWSABLE"/>)

[//]: # ()
[//]: # (        <data)

[//]: # (            android:scheme="https")

[//]: # (            android:host="myapp.com")

[//]: # (            android:pathPrefix="/product"/>)

[//]: # (    </intent-filter>)

[//]: # (</activity>)

[//]: # (```)

[//]: # ()
[//]: # (✅ Open link:)

[//]: # ()
[//]: # (```)

[//]: # (https://myapp.com/product/123)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # (//service)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ Android Service & Background Processing – Explained with Tags + Examples)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is Service?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A Service is an Android component that performs long-running operations in the background without UI.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`android.app.Service`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyService : Service&#40;&#41; {)

[//]: # (    override fun onBind&#40;intent: Intent?&#41;: IBinder? = null)

[//]: # ()
[//]: # (    override fun onStartCommand&#40;intent: Intent?, flags: Int, startId: Int&#41;: Int {)

[//]: # (        Log.d&#40;"Service", "Service Started"&#41;)

[//]: # (        return START_STICKY)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (Start Service:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (startService&#40;Intent&#40;this, MyService::class.java&#41;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; Types of Services in Android)

[//]: # ()
[//]: # (### ✅ a&#41; Foreground Service)

[//]: # ()
[//]: # (### ✅ b&#41; Background Service &#40;Deprecated / Restricted&#41;)

[//]: # ()
[//]: # (### ✅ c&#41; Bound Service)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; What is Foreground Service?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A service that runs in the foreground with a visible notification.)

[//]: # ()
[//]: # (✅ **Used Methods:**)

[//]: # (`startForeground&#40;&#41;`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (startForeground&#40;1, notification&#41;)

[//]: # (```)

[//]: # ()
[//]: # (📌 Use cases:)

[//]: # (Music player, navigation, fitness tracking, location tracking.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; What is Background Service?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A service running in the background without user interaction.)

[//]: # ()
[//]: # (⚠️ Restricted from Android 8+ &#40;Oreo&#41;.)

[//]: # ()
[//]: # (📌 Reason: Battery optimization & security.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; What is Bound Service?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A service that allows components to bind and interact with it.)

[//]: # ()
[//]: # (✅ **Used Method:**)

[//]: # (`bindService&#40;&#41;`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (bindService&#40;Intent&#40;this, MyService::class.java&#41;, connection, Context.BIND_AUTO_CREATE&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; Difference between Service and IntentService)

[//]: # ()
[//]: # (| Feature            | Service            | IntentService     |)

[//]: # (| ------------------ | ------------------ | ----------------- |)

[//]: # (| Thread             | Main thread        | Background thread |)

[//]: # (| Queue              | ❌ No               | ✅ Yes             |)

[//]: # (| Stop automatically | ❌ No               | ✅ Yes             |)

[//]: # (| Use case           | Long-running tasks | Sequential tasks  |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; Why IntentService is deprecated?)

[//]: # ()
[//]: # (✅ Reasons:)

[//]: # ()
[//]: # (* Not lifecycle-aware)

[//]: # (* No support for modern background limits)

[//]: # (* Replaced by WorkManager / JobIntentService / Coroutines)

[//]: # ()
[//]: # (⚠️ Deprecated since Android API 30.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8&#41; What is JobIntentService?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A backward-compatible alternative to IntentService using JobScheduler.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`androidx.core.app.JobIntentService`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyJobIntentService : JobIntentService&#40;&#41; {)

[//]: # (    override fun onHandleWork&#40;intent: Intent&#41; {)

[//]: # (        Log.d&#40;"JobIntentService", "Task executed"&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9&#41; What is JobScheduler?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (API to schedule background jobs based on conditions &#40;network, charging, idle&#41;.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`android.app.job.JobScheduler`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val jobInfo = JobInfo.Builder&#40;1, ComponentName&#40;this, MyJobService::class.java&#41;&#41;)

[//]: # (    .setRequiredNetworkType&#40;JobInfo.NETWORK_TYPE_ANY&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 10&#41; What is WorkManager?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A modern Android library for guaranteed background work execution.)

[//]: # ()
[//]: # (✅ **Used Class:**)

[//]: # (`androidx.work.WorkManager`)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val workRequest = OneTimeWorkRequestBuilder<MyWorker>&#40;&#41;.build&#40;&#41;)

[//]: # (WorkManager.getInstance&#40;this&#41;.enqueue&#40;workRequest&#41;)

[//]: # (```)

[//]: # ()
[//]: # (📌 Best for:)

[//]: # ()
[//]: # (* Guaranteed execution)

[//]: # (* Deferrable tasks)

[//]: # (* Background sync)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 11&#41; Foreground Service vs WorkManager)

[//]: # ()
[//]: # (| Feature              | Foreground Service | WorkManager |)

[//]: # (| -------------------- | ------------------ | ----------- |)

[//]: # (| Runs immediately     | ✅ Yes              | ❌ No        |)

[//]: # (| Visible notification | ✅ Yes              | ❌ No        |)

[//]: # (| Guaranteed execution | ❌ No               | ✅ Yes       |)

[//]: # (| Long-running task    | ✅ Yes              | ⚠️ Limited  |)

[//]: # (| Battery-friendly     | ❌ No               | ✅ Yes       |)

[//]: # ()
[//]: # (✅ Rule:)

[//]: # ()
[//]: # (* Real-time task → Foreground Service)

[//]: # (* Deferred task → WorkManager)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 12&#41; How to get continuous location updates?)

[//]: # ()
[//]: # (✅ Best approaches:)

[//]: # ()
[//]: # (### ✅ a&#41; Foreground Service + FusedLocationProvider)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val locationRequest = LocationRequest.create&#40;&#41;)

[//]: # (    .setInterval&#40;5000&#41;)

[//]: # (    .setPriority&#40;LocationRequest.PRIORITY_HIGH_ACCURACY&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ b&#41; WorkManager &#40;not real-time&#41;)

[//]: # ()
[//]: # (### ✅ c&#41; Callback-based Location API)

[//]: # ()
[//]: # (📌 Recommended: Foreground Service.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13&#41; What can be used for background processing in Android?)

[//]: # ()
[//]: # (✅ Options:)

[//]: # ()
[//]: # (| Tool                     | Use Case             |)

[//]: # (| ------------------------ | -------------------- |)

[//]: # (| Thread / ExecutorService | Short tasks          |)

[//]: # (| Coroutine                | Modern async tasks   |)

[//]: # (| HandlerThread            | Background thread    |)

[//]: # (| Service                  | Long-running tasks   |)

[//]: # (| Foreground Service       | Real-time tasks      |)

[//]: # (| WorkManager              | Guaranteed tasks     |)

[//]: # (| JobScheduler             | System-managed jobs  |)

[//]: # (| AlarmManager             | Scheduled tasks      |)

[//]: # (| RxJava                   | Reactive async tasks |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# 🧵 Threads & Concurrency in Android)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is a Background Thread?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A background thread is a thread that runs tasks without blocking the main &#40;UI&#41; thread.)

[//]: # ()
[//]: # (✅ **Why needed?**)

[//]: # ()
[//]: # (* Network calls)

[//]: # (* Database operations)

[//]: # (* File I/O)

[//]: # (* Heavy computations)

[//]: # ()
[//]: # (✅ **Examples of background threads:**)

[//]: # ()
[//]: # (* Thread)

[//]: # (* ExecutorService)

[//]: # (* Coroutine)

[//]: # (* WorkManager)

[//]: # (* Service)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (Thread {)

[//]: # (    // background work)

[//]: # (}.start&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; Why should non-UI work not run on the main thread?)

[//]: # ()
[//]: # (✅ **Reason:**)

[//]: # (The main thread is responsible for UI rendering and user interactions.)

[//]: # ()
[//]: # (❌ If heavy work runs on main thread:)

[//]: # ()
[//]: # (* UI freezes)

[//]: # (* App becomes unresponsive)

[//]: # (* ANR occurs)

[//]: # ()
[//]: # (✅ **Android Rule:**)

[//]: # ()
[//]: # (> Network and heavy operations must not run on the main thread.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; What is ANR? How can it be prevented?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (ANR &#40;Application Not Responding&#41; occurs when the main thread is blocked for too long.)

[//]: # ()
[//]: # (⏱️ Time limits:)

[//]: # ()
[//]: # (* Activity: 5 seconds)

[//]: # (* BroadcastReceiver: 10 seconds)

[//]: # ()
[//]: # (### ✅ Common Causes:)

[//]: # ()
[//]: # (* Long operations on main thread)

[//]: # (* Infinite loops)

[//]: # (* Deadlocks)

[//]: # (* Heavy UI rendering)

[//]: # (* Network calls on main thread)

[//]: # ()
[//]: # (### ✅ Prevention:)

[//]: # ()
[//]: # (* Use background threads)

[//]: # (* Use coroutines / WorkManager)

[//]: # (* Optimize UI)

[//]: # (* Avoid blocking calls)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; What is AsyncTask?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (AsyncTask was used to perform background tasks and update UI easily.)

[//]: # ()
[//]: # (⚠️ Deprecated since API 30.)

[//]: # ()
[//]: # (✅ **Methods:**)

[//]: # ()
[//]: # (* onPreExecute&#40;&#41;)

[//]: # (* doInBackground&#40;&#41;)

[//]: # (* onPostExecute&#40;&#41;)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyTask : AsyncTask<Void, Void, String>&#40;&#41; {)

[//]: # (    override fun doInBackground&#40;vararg params: Void?&#41;: String {)

[//]: # (        return "Result")

[//]: # (    })

[//]: # ()
[//]: # (    override fun onPostExecute&#40;result: String&#41; {)

[//]: # (        println&#40;result&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; Problems with AsyncTask)

[//]: # ()
[//]: # (❌ Memory leaks)

[//]: # (❌ Lifecycle issues)

[//]: # (❌ Not cancellation-safe)

[//]: # (❌ Poor error handling)

[//]: # (❌ Not scalable)

[//]: # (❌ Deprecated)

[//]: # ()
[//]: # (✅ Replacement:)

[//]: # ()
[//]: # (* Kotlin Coroutines)

[//]: # (* WorkManager)

[//]: # (* ExecutorService)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; What is Loader?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Loader was used to load data asynchronously in Activities/Fragments.)

[//]: # ()
[//]: # (⚠️ Deprecated in AndroidX.)

[//]: # ()
[//]: # (✅ **Types:**)

[//]: # ()
[//]: # (* CursorLoader)

[//]: # (* AsyncTaskLoader)

[//]: # ()
[//]: # (❌ Issues:)

[//]: # ()
[//]: # (* Complex API)

[//]: # (* Lifecycle problems)

[//]: # ()
[//]: # (✅ Replacement:)

[//]: # ()
[//]: # (* ViewModel + LiveData + Coroutines)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; Explain Looper, Handler, and HandlerThread)

[//]: # ()
[//]: # (### 🌀 Looper)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Looper manages a message queue for a thread.)

[//]: # ()
[//]: # (📌 Main thread has a Looper by default.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 📨 Handler)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Handler posts tasks/messages to a thread’s Looper.)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val handler = Handler&#40;Looper.getMainLooper&#40;&#41;&#41;)

[//]: # (handler.post {)

[//]: # (    // update UI)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🧵 HandlerThread)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A background thread with its own Looper.)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val handlerThread = HandlerThread&#40;"MyThread"&#41;)

[//]: # (handlerThread.start&#40;&#41;)

[//]: # (val handler = Handler&#40;handlerThread.looper&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8&#41; Different types of threads in Android)

[//]: # ()
[//]: # (| Type              | Description        |)

[//]: # (| ----------------- | ------------------ |)

[//]: # (| Main Thread       | UI thread          |)

[//]: # (| Worker Thread     | Background tasks   |)

[//]: # (| HandlerThread     | Thread with Looper |)

[//]: # (| Thread Pool       | ExecutorService    |)

[//]: # (| Coroutine Threads | Dispatchers        |)

[//]: # (| Binder Thread     | IPC communication  |)

[//]: # (| Render Thread     | UI rendering       |)

[//]: # (| GC Thread         | Garbage Collection |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9&#41; Which thread does Dispatchers.Default use?)

[//]: # ()
[//]: # (✅ **Answer:**)

[//]: # (`Dispatchers.Default` uses a shared pool of background threads optimized for CPU-intensive tasks.)

[//]: # ()
[//]: # (📌 Backed by:)

[//]: # ()
[//]: # (* ForkJoinPool &#40;JVM&#41;)

[//]: # (* CPU core-based thread pool)

[//]: # ()
[//]: # (✅ Use cases:)

[//]: # ()
[//]: # (* Heavy computations)

[//]: # (* Sorting)

[//]: # (* JSON parsing)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 10&#41; Best way to update UI periodically)

[//]: # ()
[//]: # (✅ Recommended approaches:)

[//]: # ()
[//]: # (### ✅ a&#41; Coroutine + delay&#40;&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (lifecycleScope.launch {)

[//]: # (    while &#40;true&#41; {)

[//]: # (        delay&#40;1000&#41;)

[//]: # (        updateUI&#40;&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; Handler)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val handler = Handler&#40;Looper.getMainLooper&#40;&#41;&#41;)

[//]: # (val runnable = object : Runnable {)

[//]: # (    override fun run&#40;&#41; {)

[//]: # (        updateUI&#40;&#41;)

[//]: # (        handler.postDelayed&#40;this, 1000&#41;)

[//]: # (    })

[//]: # (})

[//]: # (handler.post&#40;runnable&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; Flow / LiveData &#40;Best practice&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (flow.collect {)

[//]: # (    updateUI&#40;&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 11&#41; How to detect blocking UI thread?)

[//]: # ()
[//]: # (✅ Tools & Techniques:)

[//]: # ()
[//]: # (### ✅ a&#41; StrictMode)

[//]: # ()
[//]: # (```kotlin)

[//]: # (StrictMode.setThreadPolicy&#40;)

[//]: # (    StrictMode.ThreadPolicy.Builder&#40;&#41;)

[//]: # (        .detectAll&#40;&#41;)

[//]: # (        .penaltyLog&#40;&#41;)

[//]: # (        .build&#40;&#41;)

[//]: # (&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; Android Profiler)

[//]: # ()
[//]: # (* CPU Profiler)

[//]: # (* Main thread monitoring)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; ANR Reports)

[//]: # ()
[//]: # (* Play Console)

[//]: # (* Logcat)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ d&#41; Systrace / Perfetto)

[//]: # ()
[//]: # (* System-level tracing)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ e&#41; Choreographer / Frame drops)

[//]: # ()
[//]: # (* Detect UI jank)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ♻️ RecyclerView in Android)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is RecyclerView?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (RecyclerView is an advanced and flexible version of ListView used to display large sets of data efficiently.)

[//]: # ()
[//]: # (✅ **Package:**)

[//]: # ()
[//]: # (```text)

[//]: # (androidx.recyclerview.widget.RecyclerView)

[//]: # (```)

[//]: # ()
[//]: # (✅ **Key Components:**)

[//]: # ()
[//]: # (* Adapter)

[//]: # (* ViewHolder)

[//]: # (* LayoutManager)

[//]: # (* ItemAnimator)

[//]: # (* ItemDecoration)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (recyclerView.layoutManager = LinearLayoutManager&#40;this&#41;)

[//]: # (recyclerView.adapter = MyAdapter&#40;list&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; Difference between RecyclerView and ListView)

[//]: # ()
[//]: # (| Feature            | RecyclerView | ListView      |)

[//]: # (| ------------------ | ------------ | ------------- |)

[//]: # (| ViewHolder pattern | Mandatory    | Optional      |)

[//]: # (| Layout types       | Multiple     | Only vertical |)

[//]: # (| Performance        | High         | Low           |)

[//]: # (| Animations         | Built-in     | Limited       |)

[//]: # (| Flexibility        | Very high    | Low           |)

[//]: # (| Optimization       | Advanced     | Basic         |)

[//]: # (| Nested scrolling   | Better       | Poor          |)

[//]: # ()
[//]: # (✅ Interview Line:)

[//]: # ()
[//]: # (> RecyclerView is more flexible, efficient, and extensible than ListView.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; What is ViewHolder Pattern?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (ViewHolder pattern caches item views to avoid repeated `findViewById&#40;&#41;` calls.)

[//]: # ()
[//]: # (✅ **Purpose:**)

[//]: # ()
[//]: # (* Improve performance)

[//]: # (* Reduce view inflation cost)

[//]: # (* Faster scrolling)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyViewHolder&#40;view: View&#41; : RecyclerView.ViewHolder&#40;view&#41; {)

[//]: # (    val title = view.findViewById<TextView>&#40;R.id.title&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; How does RecyclerView work internally?)

[//]: # ()
[//]: # (### ♻️ Core Concept: View Recycling)

[//]: # ()
[//]: # (RecyclerView reuses item views instead of creating new ones.)

[//]: # ()
[//]: # (### 🔄 Steps:)

[//]: # ()
[//]: # (1. LayoutManager requests views.)

[//]: # (2. Adapter binds data to ViewHolder.)

[//]: # (3. Off-screen views are recycled.)

[//]: # (4. Recycled views are reused for new items.)

[//]: # ()
[//]: # (### 🧠 Internal Components:)

[//]: # ()
[//]: # (* Recycler &#40;view cache pool&#41;)

[//]: # (* Adapter)

[//]: # (* LayoutManager)

[//]: # (* ItemAnimator)

[//]: # ()
[//]: # (### 📊 View Cache Levels:)

[//]: # ()
[//]: # (| Cache Type           | Description             |)

[//]: # (| -------------------- | ----------------------- |)

[//]: # (| Attached Scrap       | Currently visible views |)

[//]: # (| Cached Views         | Recently detached views |)

[//]: # (| Recycled View Pool   | Shared recycled views   |)

[//]: # (| View Cache Extension | Custom cache            |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; RecyclerView Scrolling Optimization Techniques)

[//]: # ()
[//]: # (### ✅ 1&#41; Use ViewHolder properly)

[//]: # ()
[//]: # (Avoid expensive operations in `onBindViewHolder&#40;&#41;`.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 2&#41; Use DiffUtil instead of notifyDataSetChanged&#40;&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (DiffUtil.calculateDiff&#40;callback&#41;)

[//]: # (```)

[//]: # ()
[//]: # (✔ Efficient updates)

[//]: # (✔ Avoid full redraw)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 3&#41; Enable stable IDs)

[//]: # ()
[//]: # (```kotlin)

[//]: # (setHasStableIds&#40;true&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 4&#41; Avoid nested layouts &#40;ConstraintLayout recommended&#41;)

[//]: # ()
[//]: # (❌ LinearLayout inside LinearLayout)

[//]: # (✅ ConstraintLayout)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 5&#41; Use ListAdapter instead of RecyclerView.Adapter)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyAdapter : ListAdapter<Item, VH>&#40;DiffCallback&#40;&#41;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 6&#41; Disable unnecessary animations)

[//]: # ()
[//]: # (```kotlin)

[//]: # (recyclerView.itemAnimator = null)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 7&#41; Increase RecyclerView cache size)

[//]: # ()
[//]: # (```kotlin)

[//]: # (recyclerView.setItemViewCacheSize&#40;20&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 8&#41; Use ViewBinding instead of findViewById&#40;&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 9&#41; Avoid heavy operations in onBindViewHolder&#40;&#41;)

[//]: # ()
[//]: # (❌ Network calls)

[//]: # (❌ Image decoding)

[//]: # (❌ Complex calculations)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; How to optimize Nested RecyclerView?)

[//]: # ()
[//]: # (Nested RecyclerView = RecyclerView inside RecyclerView)

[//]: # (&#40;e.g., horizontal list inside vertical list&#41;)

[//]: # ()
[//]: # (### 🚨 Problems:)

[//]: # ()
[//]: # (* Laggy scrolling)

[//]: # (* High memory usage)

[//]: # (* View inflation overhead)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ Optimization Techniques:)

[//]: # ()
[//]: # (### ✅ 1&#41; Share RecycledViewPool)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val pool = RecyclerView.RecycledViewPool&#40;&#41;)

[//]: # (parentRecyclerView.setRecycledViewPool&#40;pool&#41;)

[//]: # (childRecyclerView.setRecycledViewPool&#40;pool&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 2&#41; Use setHasFixedSize&#40;true&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (recyclerView.setHasFixedSize&#40;true&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 3&#41; Disable nested scrolling)

[//]: # ()
[//]: # (```kotlin)

[//]: # (childRecyclerView.isNestedScrollingEnabled = false)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 4&#41; Use ViewPager2 instead of nested RecyclerView &#40;if possible&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 5&#41; Preload items &#40;Prefetch&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (LinearLayoutManager&#40;context&#41;.apply {)

[//]: # (    initialPrefetchItemCount = 4)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 6&#41; Use Paging 3 library for large data)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ 7&#41; Avoid deep view hierarchy)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is View?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (`View` is the basic building block of UI in Android. It represents a single UI component.)

[//]: # ()
[//]: # (✅ **Class:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (android.view.View)

[//]: # (```)

[//]: # ()
[//]: # (✅ **Examples of View:**)

[//]: # ()
[//]: # (* TextView)

[//]: # (* Button)

[//]: # (* ImageView)

[//]: # (* EditText)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```xml)

[//]: # (<TextView)

[//]: # (    android:layout_width="wrap_content")

[//]: # (    android:layout_height="wrap_content")

[//]: # (    android:text="Hello"/>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; What is ViewGroup?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (ViewGroup is a special type of View that can contain other Views &#40;child views&#41;.)

[//]: # ()
[//]: # (✅ **Class:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (android.view.ViewGroup)

[//]: # (```)

[//]: # ()
[//]: # (✅ **Examples:**)

[//]: # ()
[//]: # (* LinearLayout)

[//]: # (* ConstraintLayout)

[//]: # (* RelativeLayout)

[//]: # (* FrameLayout)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```xml)

[//]: # (<LinearLayout)

[//]: # (    android:layout_width="match_parent")

[//]: # (    android:layout_height="wrap_content">)

[//]: # ()
[//]: # (    <TextView)

[//]: # (        android:text="Child View"/>)

[//]: # (</LinearLayout>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; Difference between View.GONE and View.INVISIBLE)

[//]: # ()
[//]: # (| Property       | View.GONE           | View.INVISIBLE       |)

[//]: # (| -------------- | ------------------- | -------------------- |)

[//]: # (| Visibility     | Hidden              | Hidden               |)

[//]: # (| Space occupied | ❌ No                | ✅ Yes                |)

[//]: # (| Layout impact  | Removed from layout | Layout space remains |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (view.visibility = View.GONE)

[//]: # (view.visibility = View.INVISIBLE)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; What is SurfaceView?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (SurfaceView is a View that provides a dedicated drawing surface for rendering graphics in a separate thread.)

[//]: # ()
[//]: # (✅ **Use Cases:**)

[//]: # ()
[//]: # (* Games)

[//]: # (* Video playback)

[//]: # (* Camera preview)

[//]: # (* OpenGL rendering)

[//]: # ()
[//]: # (✅ **Difference from View:**)

[//]: # ()
[//]: # (* Runs on separate thread)

[//]: # (* Better performance for heavy rendering)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; What is Spannable?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Spannable is used to apply multiple styles to parts of a text.)

[//]: # ()
[//]: # (✅ **Class:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (SpannableString)

[//]: # (```)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val text = SpannableString&#40;"Hello Android"&#41;)

[//]: # (text.setSpan&#40;ForegroundColorSpan&#40;Color.RED&#41;, 0, 5, Spanned.SPAN_EXCLUSIVE&#41;)

[//]: # (textView.text = text)

[//]: # (```)

[//]: # ()
[//]: # (📌 Use cases:)

[//]: # ()
[//]: # (* Rich text)

[//]: # (* Highlighting text)

[//]: # (* Clickable links)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; What is Overdraw?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Overdraw happens when the system draws the same pixel multiple times in a single frame.)

[//]: # ()
[//]: # (❌ Causes:)

[//]: # ()
[//]: # (* Deep layout hierarchy)

[//]: # (* Backgrounds on multiple views)

[//]: # (* Overlapping views)

[//]: # ()
[//]: # (✅ **Impact:**)

[//]: # ()
[//]: # (* UI lag)

[//]: # (* Battery drain)

[//]: # ()
[//]: # (✅ **Detection:**)

[//]: # ()
[//]: # (* Developer Options → Debug GPU Overdraw)

[//]: # ()
[//]: # (✅ **Solution:**)

[//]: # ()
[//]: # (* Remove unnecessary backgrounds)

[//]: # (* Use ConstraintLayout)

[//]: # (* Flatten layouts)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; Difference between @id and @+id)

[//]: # ()
[//]: # (| Syntax          | Meaning                  |)

[//]: # (| --------------- | ------------------------ |)

[//]: # (| `@+id/viewName` | Create a new ID          |)

[//]: # (| `@id/viewName`  | Reference an existing ID |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```xml)

[//]: # (<TextView)

[//]: # (    android:id="@+id/title"/>)

[//]: # (```)

[//]: # ()
[//]: # (```xml)

[//]: # (<Button)

[//]: # (    android:layout_toRightOf="@id/title"/>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8&#41; What is Widget?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A Widget is a reusable UI component that allows user interaction.)

[//]: # ()
[//]: # (✅ **Examples:**)

[//]: # ()
[//]: # (* Button)

[//]: # (* EditText)

[//]: # (* Switch)

[//]: # (* RecyclerView)

[//]: # ()
[//]: # (📌 Also:)

[//]: # (App Widgets = Home screen widgets.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9&#41; How to support different screen sizes?)

[//]: # ()
[//]: # (### ✅ Techniques:)

[//]: # ()
[//]: # (### ✅ a&#41; Responsive Layouts)

[//]: # ()
[//]: # (* ConstraintLayout)

[//]: # (* FlexboxLayout)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; Resource qualifiers)

[//]: # ()
[//]: # (| Folder         | Purpose        |)

[//]: # (| -------------- | -------------- |)

[//]: # (| layout-sw600dp | Tablets        |)

[//]: # (| layout-land    | Landscape      |)

[//]: # (| drawable-hdpi  | Screen density |)

[//]: # (| values-night   | Dark mode      |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; Use dp & sp instead of px)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ d&#41; Vector Drawables)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ e&#41; Jetpack Compose responsive UI)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 10&#41; Difference between raw and assets folder)

[//]: # ()
[//]: # (| Feature       | raw            | assets       |)

[//]: # (| ------------- | -------------- | ------------ |)

[//]: # (| Folder path   | res/raw        | assets/      |)

[//]: # (| Resource ID   | Yes            | No           |)

[//]: # (| Access method | R.raw.filename | AssetManager |)

[//]: # (| File types    | Limited        | Any file     |)

[//]: # (| Subfolders    | ❌ No           | ✅ Yes        |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (### raw:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val inputStream = resources.openRawResource&#40;R.raw.file&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### assets:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val inputStream = assets.open&#40;"file.txt"&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 11&#41; What is Dark Theme?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Dark Theme is a UI mode where the app uses dark colors to reduce eye strain and battery consumption.)

[//]: # ()
[//]: # (✅ **Implementation:**)

[//]: # ()
[//]: # (### ✅ a&#41; Theme XML)

[//]: # ()
[//]: # (```xml)

[//]: # (<style name="Theme.MyApp" parent="Theme.MaterialComponents.DayNight">)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ b&#41; Resource folder:)

[//]: # ()
[//]: # (```)

[//]: # (values-night/colors.xml)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ c&#41; Enable dark mode:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (AppCompatDelegate.setDefaultNightMode&#40;AppCompatDelegate.MODE_NIGHT_YES&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # (Here you go 💾)

[//]: # (Below is **Data Storage in Android** explained in **clean Markdown format** &#40;interview-ready + GitHub-friendly&#41;.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# 💾 Data Storage in Android)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; Ways to store data in Android)

[//]: # ()
[//]: # (Android provides multiple ways to store data depending on size, security, and use case.)

[//]: # ()
[//]: # (### ✅ Types of Data Storage)

[//]: # ()
[//]: # (| Storage Type        | Use Case                                |)

[//]: # (| ------------------- | --------------------------------------- |)

[//]: # (| SharedPreferences   | Small key-value data                    |)

[//]: # (| DataStore &#40;Jetpack&#41; | Modern replacement of SharedPreferences |)

[//]: # (| Internal Storage    | Private app files                       |)

[//]: # (| External Storage    | Public/shared files                     |)

[//]: # (| SQLite Database     | Structured relational data              |)

[//]: # (| Room Database       | ORM over SQLite                         |)

[//]: # (| ContentProvider     | Data sharing between apps               |)

[//]: # (| Network Storage     | Cloud / API                             |)

[//]: # (| Cache               | Temporary data                          |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; What is SharedPreferences?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (SharedPreferences is a lightweight storage mechanism to store key-value pairs.)

[//]: # ()
[//]: # (✅ **Used for:**)

[//]: # ()
[//]: # (* User settings)

[//]: # (* Login state)

[//]: # (* Theme preferences)

[//]: # (* Tokens)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val prefs = getSharedPreferences&#40;"MyPrefs", Context.MODE_PRIVATE&#41;)

[//]: # (prefs.edit&#40;&#41;.putString&#40;"username", "Aasim"&#41;.apply&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (Read data:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val name = prefs.getString&#40;"username", ""&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; Difference between commit&#40;&#41; and apply&#40;&#41;)

[//]: # ()
[//]: # (| Feature     | commit&#40;&#41;                | apply&#40;&#41;           |)

[//]: # (| ----------- | ----------------------- | ----------------- |)

[//]: # (| Thread      | Main thread             | Background thread |)

[//]: # (| Return type | boolean                 | void              |)

[//]: # (| Blocking    | Yes                     | No                |)

[//]: # (| Performance | Slower                  | Faster            |)

[//]: # (| Use case    | Immediate result needed | Preferred         |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (prefs.edit&#40;&#41;.putString&#40;"key", "value"&#41;.commit&#40;&#41;)

[//]: # (prefs.edit&#40;&#41;.putString&#40;"key", "value"&#41;.apply&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (📌 Interview Line:)

[//]: # ()
[//]: # (> apply&#40;&#41; is asynchronous and recommended, while commit&#40;&#41; is synchronous.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; What is ContentProvider?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (ContentProvider is an Android component used to share data between different applications.)

[//]: # ()
[//]: # (✅ **Class:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (android.content.ContentProvider)

[//]: # (```)

[//]: # ()
[//]: # (✅ **Examples:**)

[//]: # ()
[//]: # (* Contacts Provider)

[//]: # (* Media Provider)

[//]: # (* Calendar Provider)

[//]: # ()
[//]: # (✅ **Use Case:**)

[//]: # ()
[//]: # (* Inter-app data sharing)

[//]: # (* Secure data access)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; What is Content URI?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Content URI is the unique identifier used to access data from a ContentProvider.)

[//]: # ()
[//]: # (✅ **Format:**)

[//]: # ()
[//]: # (```text)

[//]: # (content://authority/path/id)

[//]: # (```)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (content://com.example.app.provider/users/1)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; CRUD operations in ContentProvider)

[//]: # ()
[//]: # (CRUD = Create, Read, Update, Delete)

[//]: # ()
[//]: # (### ✅ a&#41; Insert &#40;Create&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (contentResolver.insert&#40;uri, values&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ b&#41; Query &#40;Read&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (contentResolver.query&#40;uri, null, null, null, null&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ c&#41; Update)

[//]: # ()
[//]: # (```kotlin)

[//]: # (contentResolver.update&#40;uri, values, null, null&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ d&#41; Delete)

[//]: # ()
[//]: # (```kotlin)

[//]: # (contentResolver.delete&#40;uri, null, null&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; Can SQLite DB be accessed for debugging?)

[//]: # ()
[//]: # (✅ **Yes, SQLite DB can be accessed for debugging.**)

[//]: # ()
[//]: # (### ✅ Methods:)

[//]: # ()
[//]: # (### ✅ a&#41; Android Studio Device File Explorer)

[//]: # ()
[//]: # (Path:)

[//]: # ()
[//]: # (```)

[//]: # (/data/data/<package_name>/databases/)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; adb shell)

[//]: # ()
[//]: # (```bash)

[//]: # (adb shell)

[//]: # (cd /data/data/com.example.app/databases/)

[//]: # (sqlite3 mydb.db)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; Stetho / Debug DB / Flipper)

[//]: # ()
[//]: # (Libraries:)

[//]: # ()
[//]: # (* Facebook Stetho)

[//]: # (* DebugDB)

[//]: # (* Flipper)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ d&#41; Room Database Inspector &#40;Android Studio&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (Here you go 🌐)

[//]: # (Below is **Networking in Android &#40;Retrofit, OkHttp, HTTP, REST&#41;** explained in **clean Markdown format** — perfect for interviews, GitHub, and notes.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# 🌐 Networking in Android &#40;Retrofit, OkHttp, REST, HTTP&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is Retrofit?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Retrofit is a type-safe HTTP client library for Android used to call REST APIs.)

[//]: # ()
[//]: # (✅ **Developed by:** Square)

[//]: # ()
[//]: # (✅ **Built on:** OkHttp)

[//]: # ()
[//]: # (✅ **Features:**)

[//]: # ()
[//]: # (* REST API support)

[//]: # (* JSON parsing &#40;Gson, Moshi&#41;)

[//]: # (* Annotations-based API)

[//]: # (* Coroutine support)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (interface ApiService {)

[//]: # (    @GET&#40;"users"&#41;)

[//]: # (    suspend fun getUsers&#40;&#41;: List<User>)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; How to handle multiple network calls using Retrofit?)

[//]: # ()
[//]: # (### ✅ a&#41; Sequential calls &#40;Coroutines&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val user = api.getUser&#40;&#41;)

[//]: # (val posts = api.getPosts&#40;user.id&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; Parallel calls &#40;Coroutines async&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (coroutineScope {)

[//]: # (    val user = async { api.getUser&#40;&#41; })

[//]: # (    val posts = async { api.getPosts&#40;&#41; })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; RxJava)

[//]: # ()
[//]: # (```kotlin)

[//]: # (Observable.zip&#40;api.getUser&#40;&#41;, api.getPosts&#40;&#41;, ...&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ d&#41; Callback-based)

[//]: # ()
[//]: # (```kotlin)

[//]: # (Call.enqueue&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; What is OkHttp Interceptor?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Interceptor is a mechanism in OkHttp to intercept, modify, or log HTTP requests and responses.)

[//]: # ()
[//]: # (✅ **Use cases:**)

[//]: # ()
[//]: # (* Logging)

[//]: # (* Authentication)

[//]: # (* Headers)

[//]: # (* Caching)

[//]: # (* Retry logic)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val interceptor = Interceptor { chain ->)

[//]: # (    val request = chain.request&#40;&#41;.newBuilder&#40;&#41;)

[//]: # (        .addHeader&#40;"Authorization", "Bearer token"&#41;)

[//]: # (        .build&#40;&#41;)

[//]: # (    chain.proceed&#40;request&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; Types of OkHttp Interceptors)

[//]: # ()
[//]: # (| Type                    | Description                               |)

[//]: # (| ----------------------- | ----------------------------------------- |)

[//]: # (| Application Interceptor | Intercepts before request reaches network |)

[//]: # (| Network Interceptor     | Intercepts after network response         |)

[//]: # ()
[//]: # (### ✅ Examples:)

[//]: # ()
[//]: # (* LoggingInterceptor)

[//]: # (* HeaderInterceptor)

[//]: # (* AuthInterceptor)

[//]: # (* CacheInterceptor)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; HTTP caching in OkHttp)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (OkHttp supports HTTP response caching using cache headers.)

[//]: # ()
[//]: # (### ✅ Setup Cache:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val cacheSize = 10 * 1024 * 1024 // 10 MB)

[//]: # (val cache = Cache&#40;File&#40;context.cacheDir, "http_cache"&#41;, cacheSize&#41;)

[//]: # ()
[//]: # (val client = OkHttpClient.Builder&#40;&#41;)

[//]: # (    .cache&#40;cache&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ Cache Control:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (CacheControl.Builder&#40;&#41;)

[//]: # (    .maxAge&#40;1, TimeUnit.HOURS&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; HTTP libraries used and why &#40;12.1&#41;)

[//]: # ()
[//]: # (| Library           | Why used                 |)

[//]: # (| ----------------- | ------------------------ |)

[//]: # (| Retrofit          | REST API calls           |)

[//]: # (| OkHttp            | Low-level HTTP client    |)

[//]: # (| Volley            | Fast request handling    |)

[//]: # (| Ktor              | Kotlin-first HTTP client |)

[//]: # (| Fuel              | Lightweight HTTP         |)

[//]: # (| HttpURLConnection | Native Java API          |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; How REST APIs work &#40;12.2&#41;)

[//]: # ()
[//]: # (✅ **REST &#40;Representational State Transfer&#41;** is an architectural style for communication between client and server.)

[//]: # ()
[//]: # (### ✅ Flow:)

[//]: # ()
[//]: # (1. Client sends HTTP request.)

[//]: # (2. Server processes request.)

[//]: # (3. Server returns response &#40;JSON/XML&#41;.)

[//]: # (4. Client consumes data.)

[//]: # ()
[//]: # (### ✅ Key Principles:)

[//]: # ()
[//]: # (* Stateless)

[//]: # (* Client-server architecture)

[//]: # (* Resource-based URLs)

[//]: # (* HTTP methods)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8&#41; HTTP Methods &#40;12.3&#41;)

[//]: # ()
[//]: # (| Method | Purpose                 |)

[//]: # (| ------ | ----------------------- |)

[//]: # (| GET    | Fetch data              |)

[//]: # (| POST   | Create data             |)

[//]: # (| PUT    | Update entire resource  |)

[//]: # (| PATCH  | Update partial resource |)

[//]: # (| DELETE | Delete data             |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```http)

[//]: # (GET /users)

[//]: # (POST /users)

[//]: # (PUT /users/1)

[//]: # (PATCH /users/1)

[//]: # (DELETE /users/1)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 9&#41; Advantage of Retrofit over Volley &#40;12.4&#41;)

[//]: # ()
[//]: # (✅ Advantages:)

[//]: # ()
[//]: # (* Type-safe API)

[//]: # (* Better REST support)

[//]: # (* Annotation-based)

[//]: # (* Coroutine & RxJava support)

[//]: # (* Cleaner architecture)

[//]: # (* Easy testing)

[//]: # ()
[//]: # (📌 Interview line:)

[//]: # ()
[//]: # (> Retrofit is better for structured REST APIs.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 10&#41; Advantage of Volley over Retrofit &#40;12.5&#41;)

[//]: # ()
[//]: # (✅ Advantages:)

[//]: # ()
[//]: # (* Built-in request queue)

[//]: # (* Automatic scheduling)

[//]: # (* Better for small/simple requests)

[//]: # (* Image loading support)

[//]: # (* Faster for frequent small calls)

[//]: # ()
[//]: # (📌 Interview line:)

[//]: # ()
[//]: # (> Volley is better for frequent lightweight requests.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 11&#41; Advantage of Retrofit over AsyncTask &#40;12.6&#41;)

[//]: # ()
[//]: # (| Retrofit             | AsyncTask               |)

[//]: # (| -------------------- | ----------------------- |)

[//]: # (| Built for networking | Generic background task |)

[//]: # (| Thread-safe          | Poor thread handling    |)

[//]: # (| Error handling       | Weak                    |)

[//]: # (| Scalable             | Not scalable            |)

[//]: # (| Coroutine support    | ❌                       |)

[//]: # (| Maintained           | Deprecated              |)

[//]: # ()
[//]: # (✅ Interview line:)

[//]: # ()
[//]: # (> Retrofit is designed for networking, while AsyncTask is deprecated and not suitable for API calls.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # ()
[//]: # (Here you go 🔐)

[//]: # (Below is **Android Permissions & Security** in **clean Markdown format**, interview-ready and GitHub-friendly.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# 🔐 Android Permissions & Security)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.1&#41; What are the different protection levels in permissions?)

[//]: # ()
[//]: # (Android permissions have **protection levels** that define how sensitive a permission is.)

[//]: # ()
[//]: # (### ✅ Types of Protection Levels)

[//]: # ()
[//]: # (| Level             | Description                                   |)

[//]: # (| ----------------- | --------------------------------------------- |)

[//]: # (| normal            | Low-risk permissions, granted automatically   |)

[//]: # (| dangerous         | Sensitive permissions, require user approval  |)

[//]: # (| signature         | Granted only if apps share same signature     |)

[//]: # (| signatureOrSystem | Granted to system apps or same-signature apps |)

[//]: # ()
[//]: # (### ✅ Examples:)

[//]: # ()
[//]: # (| Permission          | Level            |)

[//]: # (| ------------------- | ---------------- |)

[//]: # (| INTERNET            | normal           |)

[//]: # (| CAMERA              | dangerous        |)

[//]: # (| READ_CONTACTS       | dangerous        |)

[//]: # (| SYSTEM_ALERT_WINDOW | signature/system |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.2&#41; Types of permissions)

[//]: # ()
[//]: # (### ✅ Based on granting method:)

[//]: # ()
[//]: # (1. **Normal permissions**)

[//]: # (2. **Dangerous permissions**)

[//]: # (3. **Signature permissions**)

[//]: # (4. **Special permissions**)

[//]: # ()
[//]: # (### ✅ Dangerous permission groups:)

[//]: # ()
[//]: # (| Group      | Example               |)

[//]: # (| ---------- | --------------------- |)

[//]: # (| Location   | ACCESS_FINE_LOCATION  |)

[//]: # (| Camera     | CAMERA                |)

[//]: # (| Storage    | READ_EXTERNAL_STORAGE |)

[//]: # (| Microphone | RECORD_AUDIO          |)

[//]: # (| Contacts   | READ_CONTACTS         |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.3&#41; How to handle runtime permissions in Android?)

[//]: # ()
[//]: # (Since Android 6.0 &#40;API 23&#41;, dangerous permissions must be requested at runtime.)

[//]: # ()
[//]: # (### ✅ Steps:)

[//]: # ()
[//]: # (1. Check permission)

[//]: # (2. Request permission)

[//]: # (3. Handle result)

[//]: # ()
[//]: # (### ✅ Example &#40;Kotlin&#41;:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (if &#40;ContextCompat.checkSelfPermission&#40;this, Manifest.permission.CAMERA&#41;)

[//]: # (    != PackageManager.PERMISSION_GRANTED&#41; {)

[//]: # ()
[//]: # (    ActivityCompat.requestPermissions&#40;)

[//]: # (        this,)

[//]: # (        arrayOf&#40;Manifest.permission.CAMERA&#41;,)

[//]: # (        100)

[//]: # (    &#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (Handle result:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (override fun onRequestPermissionsResult&#40;)

[//]: # (    requestCode: Int,)

[//]: # (    permissions: Array<out String>,)

[//]: # (    grantResults: IntArray)

[//]: # (&#41; {)

[//]: # (    if &#40;requestCode == 100 && grantResults.isNotEmpty&#40;&#41;)

[//]: # (        && grantResults[0] == PackageManager.PERMISSION_GRANTED&#41; {)

[//]: # (        // Permission granted)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.4&#41; Android security best practices)

[//]: # ()
[//]: # (### ✅ Key Best Practices:)

[//]: # ()
[//]: # (* Use HTTPS instead of HTTP)

[//]: # (* Avoid hardcoding API keys)

[//]: # (* Use ProGuard / R8 obfuscation)

[//]: # (* Use EncryptedSharedPreferences)

[//]: # (* Validate SSL certificates)

[//]: # (* Restrict exported components)

[//]: # (* Use scoped storage)

[//]: # (* Minimize permissions)

[//]: # (* Secure WebView)

[//]: # (* Detect root / tampering)

[//]: # (* Use SafetyNet / Play Integrity API)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.5&#41; How do you know if the device is rooted?)

[//]: # ()
[//]: # (### ✅ Common root detection methods:)

[//]: # ()
[//]: # (1. Check su binary)

[//]: # (2. Check root apps)

[//]: # (3. Check system properties)

[//]: # (4. Check writable system paths)

[//]: # ()
[//]: # (### ✅ Example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (fun isDeviceRooted&#40;&#41;: Boolean {)

[//]: # (    val paths = arrayOf&#40;)

[//]: # (        "/system/bin/su",)

[//]: # (        "/system/xbin/su",)

[//]: # (        "/sbin/su",)

[//]: # (        "/system/app/Superuser.apk")

[//]: # (    &#41;)

[//]: # (    return paths.any { File&#40;it&#41;.exists&#40;&#41; })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.6&#41; What is Symmetric Encryption?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Symmetric encryption uses the same key for encryption and decryption.)

[//]: # ()
[//]: # (### ✅ Examples:)

[//]: # ()
[//]: # (* AES)

[//]: # (* DES)

[//]: # (* Triple DES)

[//]: # ()
[//]: # (### ✅ Diagram:)

[//]: # ()
[//]: # (```)

[//]: # (Plain Text → &#40;Key&#41; → Cipher Text → &#40;Same Key&#41; → Plain Text)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.7&#41; What is Asymmetric Encryption?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Asymmetric encryption uses two keys:)

[//]: # ()
[//]: # (* Public Key &#40;encryption&#41;)

[//]: # (* Private Key &#40;decryption&#41;)

[//]: # ()
[//]: # (### ✅ Examples:)

[//]: # ()
[//]: # (* RSA)

[//]: # (* ECC)

[//]: # ()
[//]: # (### ✅ Diagram:)

[//]: # ()
[//]: # (```)

[//]: # (Plain Text → Public Key → Cipher Text → Private Key → Plain Text)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.8&#41; How do you encrypt data in Java?)

[//]: # ()
[//]: # (### ✅ Example using AES:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (fun encrypt&#40;data: String, secret: String&#41;: String {)

[//]: # (    val key = SecretKeySpec&#40;secret.toByteArray&#40;&#41;, "AES"&#41;)

[//]: # (    val cipher = Cipher.getInstance&#40;"AES"&#41;)

[//]: # (    cipher.init&#40;Cipher.ENCRYPT_MODE, key&#41;)

[//]: # (    return Base64.encodeToString&#40;cipher.doFinal&#40;data.toByteArray&#40;&#41;&#41;, Base64.DEFAULT&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.9&#41; What is SSL Pinning?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (SSL Pinning is a security technique that binds the app to a specific server certificate or public key.)

[//]: # ()
[//]: # (✅ **Purpose:**)

[//]: # ()
[//]: # (* Prevent Man-in-the-Middle &#40;MITM&#41; attacks)

[//]: # (* Ensure server authenticity)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 13.10&#41; How do you implement SSL pinning in Android?)

[//]: # ()
[//]: # (### ✅ Method 1: OkHttp Certificate Pinning)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val certificatePinner = CertificatePinner.Builder&#40;&#41;)

[//]: # (    .add&#40;"example.com", "sha256/AAAAAAAAAAAAAAAAAAAA..."&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # ()
[//]: # (val client = OkHttpClient.Builder&#40;&#41;)

[//]: # (    .certificatePinner&#40;certificatePinner&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ Method 2: Network Security Config &#40;Recommended&#41;)

[//]: # ()
[//]: # (📁 res/xml/network_security_config.xml)

[//]: # ()
[//]: # (```xml)

[//]: # (<network-security-config>)

[//]: # (    <domain-config>)

[//]: # (        <domain includeSubdomains="true">example.com</domain>)

[//]: # (        <pin-set expiration="2027-01-01">)

[//]: # (            <pin digest="SHA-256">AAAAAAAAAAAA...</pin>)

[//]: # (        </pin-set>)

[//]: # (    </domain-config>)

[//]: # (</network-security-config>)

[//]: # (```)

[//]: # ()
[//]: # (📄 AndroidManifest.xml)

[//]: # ()
[//]: # (```xml)

[//]: # (<application)

[//]: # (    android:networkSecurityConfig="@xml/network_security_config">)

[//]: # (</application>)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (Here you go 🧠⚡)

[//]: # (Below is **Memory, Performance & Battery Optimization in Android** explained in **clean Markdown format** — interview-ready and GitHub-friendly.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# 🧠 Android Memory, Performance & Battery Optimization)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 1&#41; What is Memory Leak?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (A memory leak happens when objects are no longer needed but still referenced, so the Garbage Collector cannot free memory.)

[//]: # ()
[//]: # (✅ **Result:**)

[//]: # ()
[//]: # (* Increased memory usage)

[//]: # (* App slowdown)

[//]: # (* OutOfMemoryError &#40;OOM&#41;)

[//]: # (* App crash)

[//]: # ()
[//]: # (✅ **Example:**)

[//]: # ()
[//]: # (```kotlin)

[//]: # (object Singleton {)

[//]: # (    var activity: Activity? = null // ❌ memory leak)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 2&#41; Garbage Collection &#40;GC&#41; in Android)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Garbage Collection is the process of automatically freeing unused memory.)

[//]: # ()
[//]: # (✅ **How it works:**)

[//]: # ()
[//]: # (1. Identifies unreachable objects.)

[//]: # (2. Frees heap memory.)

[//]: # (3. Compacts memory.)

[//]: # ()
[//]: # (✅ **Types of GC in Android &#40;ART&#41;:**)

[//]: # ()
[//]: # (* Minor GC)

[//]: # (* Major GC)

[//]: # (* Full GC)

[//]: # ()
[//]: # (✅ **Impact:**)

[//]: # ()
[//]: # (* UI jank)

[//]: # (* Frame drops &#40;if GC runs frequently&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 3&#41; Causes of Memory Leaks)

[//]: # ()
[//]: # (### ✅ Common Causes:)

[//]: # ()
[//]: # (* Static references to Activity/Context)

[//]: # (* Anonymous inner classes)

[//]: # (* Long-running threads)

[//]: # (* Handlers with delayed messages)

[//]: # (* Unclosed resources &#40;Cursor, InputStream&#41;)

[//]: # (* Bitmap memory misuse)

[//]: # (* Listeners not removed)

[//]: # (* Memory leaks in singletons)

[//]: # ()
[//]: # (### ✅ Example &#40;Handler leak&#41;:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyActivity : Activity&#40;&#41; {)

[//]: # (    private val handler = Handler&#40;&#41; // ❌ leak risk)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (✅ Fix:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (private val handler = Handler&#40;Looper.getMainLooper&#40;&#41;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 4&#41; What is Bitmap Pool?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Bitmap Pool is a memory optimization technique where bitmaps are reused instead of allocating new memory.)

[//]: # ()
[//]: # (✅ **Used in libraries:**)

[//]: # ()
[//]: # (* Glide)

[//]: # (* Fresco)

[//]: # (* Coil)

[//]: # (* Picasso)

[//]: # ()
[//]: # (✅ **Benefit:**)

[//]: # ()
[//]: # (* Reduce GC pressure)

[//]: # (* Faster image loading)

[//]: # (* Lower memory usage)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 5&#41; How to handle large bitmaps efficiently?)

[//]: # ()
[//]: # (### ✅ Techniques:)

[//]: # ()
[//]: # (### ✅ a&#41; Downsampling images)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val options = BitmapFactory.Options&#40;&#41;.apply {)

[//]: # (    inSampleSize = 4)

[//]: # (})

[//]: # (BitmapFactory.decodeResource&#40;resources, R.drawable.image, options&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; Use image loading libraries)

[//]: # ()
[//]: # (* Glide)

[//]: # (* Coil)

[//]: # (* Picasso)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; Use RGB_565 instead of ARGB_8888)

[//]: # ()
[//]: # (```kotlin)

[//]: # (options.inPreferredConfig = Bitmap.Config.RGB_565)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ d&#41; Avoid loading full-size images into memory)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ e&#41; Use Bitmap Pool &#40;Glide&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 6&#41; How to use Android Memory Profiler?)

[//]: # ()
[//]: # (✅ **Tool:** Android Studio → Profiler → Memory)

[//]: # ()
[//]: # (### ✅ Steps:)

[//]: # ()
[//]: # (1. Run app in Android Studio.)

[//]: # (2. Open Profiler.)

[//]: # (3. Select Memory tab.)

[//]: # (4. Monitor:)

[//]: # ()
[//]: # (   * Heap usage)

[//]: # (   * Object allocation)

[//]: # (   * GC events)

[//]: # (   * Leaks)

[//]: # ()
[//]: # (### ✅ Features:)

[//]: # ()
[//]: # (* Heap dump)

[//]: # (* Allocation tracking)

[//]: # (* Leak detection)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 7&#41; How to measure method execution time?)

[//]: # ()
[//]: # (### ✅ a&#41; System.currentTimeMillis&#40;&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val start = System.currentTimeMillis&#40;&#41;)

[//]: # (// method call)

[//]: # (val end = System.currentTimeMillis&#40;&#41;)

[//]: # (Log.d&#40;"Time", "Execution time = ${end - start} ms"&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ b&#41; System.nanoTime&#40;&#41; &#40;more accurate&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val start = System.nanoTime&#40;&#41;)

[//]: # (// method call)

[//]: # (val end = System.nanoTime&#40;&#41;)

[//]: # (Log.d&#40;"Time", "Execution time = ${&#40;end - start&#41;/1_000_000} ms"&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ c&#41; Kotlin measureTimeMillis&#40;&#41;)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val time = measureTimeMillis {)

[//]: # (    myMethod&#40;&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ d&#41; Trace API)

[//]: # ()
[//]: # (```kotlin)

[//]: # (Trace.beginSection&#40;"MyMethod"&#41;)

[//]: # (// code)

[//]: # (Trace.endSection&#40;&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 8&#41; How to reduce battery consumption?)

[//]: # ()
[//]: # (### ✅ Best Practices:)

[//]: # ()
[//]: # (### 🔋 a&#41; Optimize network calls)

[//]: # ()
[//]: # (* Batch requests)

[//]: # (* Use caching)

[//]: # (* Avoid polling)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 b&#41; Use WorkManager instead of background services)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 c&#41; Optimize location updates)

[//]: # ()
[//]: # (* Reduce frequency)

[//]: # (* Use balanced accuracy)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 d&#41; Avoid wake locks)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 e&#41; Optimize animations & UI rendering)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 f&#41; Use JobScheduler / WorkManager)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 g&#41; Reduce overdraw)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 h&#41; Avoid unnecessary background tasks)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 i&#41; Use Doze mode & App Standby properly)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### 🔋 j&#41; Optimize alarms &#40;setExact vs setInexact&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (Here you go 🏗️)

[//]: # (Below is **Gradle, Build System & App Delivery in Android** explained in **clean Markdown format** — interview-ready and GitHub-friendly.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# 🏗️ Android Gradle, Build System & App Delivery)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.1&#41; What is Gradle?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Gradle is a build automation tool used to compile, test, package, and deploy Android applications.)

[//]: # ()
[//]: # (✅ **Features:**)

[//]: # ()
[//]: # (* Dependency management)

[//]: # (* Build variants)

[//]: # (* Plugin-based system)

[//]: # (* Incremental builds)

[//]: # ()
[//]: # (✅ **Key Files:**)

[//]: # ()
[//]: # (* `build.gradle` / `build.gradle.kts`)

[//]: # (* `settings.gradle`)

[//]: # (* `gradle.properties`)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.2&#41; What do you mean by Gradle Wrapper?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Gradle Wrapper ensures that the project uses a specific Gradle version, independent of the system-installed Gradle.)

[//]: # ()
[//]: # (✅ **Files:**)

[//]: # ()
[//]: # (* `gradlew`)

[//]: # (* `gradlew.bat`)

[//]: # (* `gradle/wrapper/gradle-wrapper.properties`)

[//]: # ()
[//]: # (✅ **Benefit:**)

[//]: # ()
[//]: # (* Consistent builds across environments)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.3&#41; Difference between implementation and api)

[//]: # ()
[//]: # (| Feature           | implementation     | api                          |)

[//]: # (| ----------------- | ------------------ | ---------------------------- |)

[//]: # (| Visibility        | Internal to module | Exposed to dependent modules |)

[//]: # (| Compilation speed | Faster             | Slower                       |)

[//]: # (| Encapsulation     | Better             | Less                         |)

[//]: # (| Use case          | Default choice     | Library APIs                 |)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```gradle)

[//]: # (dependencies {)

[//]: # (    implementation&#40;"com.squareup.retrofit2:retrofit:2.9.0"&#41;)

[//]: # (    api&#40;"com.google.guava:guava:31.0"&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.4&#41; Difference between Build Type, Product Flavor, and Build Variant)

[//]: # ()
[//]: # (### ✅ Build Type)

[//]: # ()
[//]: # (Defines how the app is built.)

[//]: # ()
[//]: # (Examples:)

[//]: # ()
[//]: # (* debug)

[//]: # (* release)

[//]: # ()
[//]: # (### ✅ Product Flavor)

[//]: # ()
[//]: # (Defines different versions of the app.)

[//]: # ()
[//]: # (Examples:)

[//]: # ()
[//]: # (* free / paid)

[//]: # (* dev / prod)

[//]: # ()
[//]: # (### ✅ Build Variant)

[//]: # ()
[//]: # (Combination of build type + product flavor.)

[//]: # ()
[//]: # (Example:)

[//]: # ()
[//]: # (```)

[//]: # (freeDebug)

[//]: # (paidRelease)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ Comparison Table:)

[//]: # ()
[//]: # (| Concept        | Purpose          |)

[//]: # (| -------------- | ---------------- |)

[//]: # (| Build Type     | Debug vs Release |)

[//]: # (| Product Flavor | App variants     |)

[//]: # (| Build Variant  | Combination      |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.5&#41; What do you know about Version Catalog?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Version Catalog is a Gradle feature to centralize dependency versions in one place.)

[//]: # ()
[//]: # (✅ **File:**)

[//]: # ()
[//]: # (```)

[//]: # (gradle/libs.versions.toml)

[//]: # (```)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```toml)

[//]: # ([versions])

[//]: # (retrofit = "2.9.0")

[//]: # ()
[//]: # ([libraries])

[//]: # (retrofit = { module = "com.squareup.retrofit2:retrofit", version.ref = "retrofit" })

[//]: # (```)

[//]: # ()
[//]: # (Use in Gradle:)

[//]: # ()
[//]: # (```gradle)

[//]: # (implementation&#40;libs.retrofit&#41;)

[//]: # (```)

[//]: # ()
[//]: # (✅ Benefits:)

[//]: # ()
[//]: # (* Centralized dependency management)

[//]: # (* Clean build.gradle)

[//]: # (* Easy upgrades)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.6&#41; Android ProGuard)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (ProGuard is a tool used to:)

[//]: # ()
[//]: # (* Shrink code)

[//]: # (* Obfuscate code)

[//]: # (* Optimize bytecode)

[//]: # (* Remove unused classes)

[//]: # ()
[//]: # (⚠️ Replaced by R8 &#40;default in modern Android&#41;.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.7&#41; Android ProGuard Rules)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Rules that define what code should be kept or removed.)

[//]: # ()
[//]: # (✅ Example:)

[//]: # ()
[//]: # (```proguard)

[//]: # (-keep class com.example.model.** { *; })

[//]: # (-dontwarn okhttp3.**)

[//]: # (-keepattributes Signature)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.8&#41; ProGuard applied at which stage of build?)

[//]: # ()
[//]: # (✅ **Answer:**)

[//]: # (ProGuard/R8 runs during the **release build** stage after compilation and before APK/AAB packaging.)

[//]: # ()
[//]: # (### ✅ Build Flow:)

[//]: # ()
[//]: # (```)

[//]: # (Kotlin/Java → DEX → R8&#40;ProGuard&#41; → APK/AAB → Signing → Packaging)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.9&#41; Ways to reduce application size)

[//]: # ()
[//]: # (### ✅ Techniques:)

[//]: # ()
[//]: # (* Enable R8 / ProGuard)

[//]: # (* Use Android App Bundle &#40;AAB&#41;)

[//]: # (* Remove unused resources)

[//]: # (* Use vector drawables)

[//]: # (* Enable resource shrinking)

[//]: # (* Split APK by ABI, density, language)

[//]: # (* Optimize images &#40;WebP&#41;)

[//]: # (* Avoid heavy libraries)

[//]: # (* Use dynamic feature modules)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.10&#41; What do you know about App Bundles?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Android App Bundle &#40;AAB&#41; is a publishing format that allows Google Play to generate optimized APKs for devices.)

[//]: # ()
[//]: # (✅ Benefits:)

[//]: # ()
[//]: # (* Smaller downloads)

[//]: # (* Device-specific APKs)

[//]: # (* Faster installs)

[//]: # ()
[//]: # (✅ Difference:)

[//]: # ()
[//]: # (| APK            | AAB                     |)

[//]: # (| -------------- | ----------------------- |)

[//]: # (| Single package | Multiple optimized APKs |)

[//]: # (| Larger size    | Smaller size            |)

[//]: # (| Manual splits  | Automatic splits        |)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.11&#41; What do you know about Play Feature Delivery?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Play Feature Delivery allows delivering app features dynamically using dynamic feature modules.)

[//]: # ()
[//]: # (✅ Types:)

[//]: # ()
[//]: # (* Install-time delivery)

[//]: # (* On-demand delivery)

[//]: # (* Conditional delivery)

[//]: # ()
[//]: # (✅ Example Use Cases:)

[//]: # ()
[//]: # (* Games levels)

[//]: # (* Chat module)

[//]: # (* Payment module)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 14.12&#41; What is Play App Signing?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Play App Signing is a Google Play service that manages and protects your app signing key.)

[//]: # ()
[//]: # (✅ Benefits:)

[//]: # ()
[//]: # (* Secure key storage)

[//]: # (* Key recovery)

[//]: # (* Optimized APK signing)

[//]: # ()
[//]: # (✅ Flow:)

[//]: # ()
[//]: # (1. Developer uploads AAB.)

[//]: # (2. Google Play signs APK with app signing key.)

[//]: # (3. Users download signed APK.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (Here you go 🚀)

[//]: # (Below is **Android Performance, Startup & Memory** in **clean Markdown format** — interview-ready and GitHub-friendly.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ⚡ Android Performance, Startup & Memory Optimization)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.1&#41; What is ANR?)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (ANR &#40;Application Not Responding&#41; occurs when the main thread is blocked for too long.)

[//]: # ()
[//]: # (⏱️ Time limits:)

[//]: # ()
[//]: # (* Activity: 5 seconds)

[//]: # (* BroadcastReceiver: 10 seconds)

[//]: # (* Service: 20 seconds)

[//]: # ()
[//]: # (### ✅ Causes:)

[//]: # ()
[//]: # (* Long-running tasks on main thread)

[//]: # (* Network calls on UI thread)

[//]: # (* Deadlocks / infinite loops)

[//]: # (* Heavy layout rendering)

[//]: # ()
[//]: # (### ✅ Prevention:)

[//]: # ()
[//]: # (* Use background threads / coroutines)

[//]: # (* Optimize UI rendering)

[//]: # (* Avoid blocking main thread)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.2&#41; App Startup Time)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (App startup time is the time taken from launching the app to displaying the first screen.)

[//]: # ()
[//]: # (### ✅ Types of Startup:)

[//]: # ()
[//]: # (| Type       | Description             |)

[//]: # (| ---------- | ----------------------- |)

[//]: # (| Cold Start | App not in memory       |)

[//]: # (| Warm Start | App partially in memory |)

[//]: # (| Hot Start  | App already in memory   |)

[//]: # ()
[//]: # (### ✅ Optimization Techniques:)

[//]: # ()
[//]: # (* Lazy initialization)

[//]: # (* Avoid heavy work in Application/Activity `onCreate&#40;&#41;`)

[//]: # (* Use SplashScreen API properly)

[//]: # (* Enable Baseline Profiles)

[//]: # (* Optimize layout)

[//]: # (* Use ViewBinding instead of DataBinding)

[//]: # (* Defer non-critical initialization)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.3&#41; Creating a Memory Leak in Android)

[//]: # ()
[//]: # (⚠️ Example &#40;Bad Code&#41;:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (object MySingleton {)

[//]: # (    var activity: Activity? = null // ❌ Memory Leak)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (Another example:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class MyActivity : Activity&#40;&#41; {)

[//]: # (    private val handler = Handler&#40;&#41; // ❌ may cause leak)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.4&#41; Avoiding Memory Leak)

[//]: # ()
[//]: # (### ✅ Best Practices:)

[//]: # ()
[//]: # (* Avoid static references to Activity/Context)

[//]: # (* Use WeakReference when needed)

[//]: # (* Clear listeners in onDestroy&#40;&#41;)

[//]: # (* Use lifecycle-aware components)

[//]: # (* Use applicationContext instead of activityContext when possible)

[//]: # (* Cancel coroutines/jobs properly)

[//]: # (* Avoid anonymous inner classes)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.5&#41; Identifying Memory Leak)

[//]: # ()
[//]: # (### ✅ Tools:)

[//]: # ()
[//]: # (* Android Studio Memory Profiler)

[//]: # (* LeakCanary)

[//]: # (* MAT &#40;Memory Analyzer Tool&#41;)

[//]: # (* Logcat &#40;GC logs&#41;)

[//]: # ()
[//]: # (### ✅ Example with LeakCanary:)

[//]: # ()
[//]: # (```gradle)

[//]: # (debugImplementation "com.squareup.leakcanary:leakcanary-android:2.12")

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.6&#41; Reducing App Size)

[//]: # ()
[//]: # (### ✅ Techniques:)

[//]: # ()
[//]: # (* Enable R8 / ProGuard)

[//]: # (* Use Android App Bundle &#40;AAB&#41;)

[//]: # (* Remove unused resources)

[//]: # (* Enable resource shrinking)

[//]: # (* Use vector drawables)

[//]: # (* Optimize images &#40;WebP&#41;)

[//]: # (* Split APK by ABI, density, language)

[//]: # (* Avoid heavy libraries)

[//]: # (* Use dynamic feature modules)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.7&#41; Downloadable Fonts)

[//]: # ()
[//]: # (✅ **Definition:**)

[//]: # (Downloadable Fonts allow apps to download fonts from Google Play services instead of bundling them.)

[//]: # ()
[//]: # (### ✅ Benefits:)

[//]: # ()
[//]: # (* Reduce APK size)

[//]: # (* Dynamic font loading)

[//]: # (* Faster updates)

[//]: # ()
[//]: # (### ✅ Example &#40;XML&#41;:)

[//]: # ()
[//]: # (```xml)

[//]: # (<TextView)

[//]: # (    android:fontFamily="@font/roboto" />)

[//]: # (```)

[//]: # ()
[//]: # (Font request:)

[//]: # ()
[//]: # (```xml)

[//]: # (<font-family)

[//]: # (    app:fontProviderAuthority="com.google.android.gms.fonts")

[//]: # (    app:fontProviderPackage="com.google.android.gms")

[//]: # (    app:fontProviderQuery="Roboto" />)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (## 16.8&#41; Splash Screen and SplashScreen API)

[//]: # ()
[//]: # (### ✅ Traditional Splash Screen &#40;Old Way&#41;)

[//]: # ()
[//]: # (* Separate SplashActivity)

[//]: # (* Delay using Handler)

[//]: # (* ❌ Bad practice &#40;slow startup&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (### ✅ SplashScreen API &#40;Android 12+&#41;)

[//]: # ()
[//]: # (✅ Official Jetpack API for splash screen.)

[//]: # ()
[//]: # (### ✅ Implementation:)

[//]: # ()
[//]: # (Gradle:)

[//]: # ()
[//]: # (```gradle)

[//]: # (implementation "androidx.core:core-splashscreen:1.0.1")

[//]: # (```)

[//]: # ()
[//]: # (Theme:)

[//]: # ()
[//]: # (```xml)

[//]: # (<style name="Theme.MyApp" parent="Theme.SplashScreen">)

[//]: # (    <item name="windowSplashScreenBackground">@color/white</item>)

[//]: # (    <item name="windowSplashScreenAnimatedIcon">@drawable/logo</item>)

[//]: # (</style>)

[//]: # (```)

[//]: # ()
[//]: # (Activity:)

[//]: # ()
[//]: # (```kotlin)

[//]: # (override fun onCreate&#40;savedInstanceState: Bundle?&#41; {)

[//]: # (    installSplashScreen&#40;&#41;)

[//]: # (    super.onCreate&#40;savedInstanceState&#41;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (### ✅ Benefits:)

[//]: # ()
[//]: # (* Faster startup)

[//]: # (* System-managed splash screen)

[//]: # (* Consistent UX)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (Here are **clear, interview-ready answers** for your Android topics 👇)

[//]: # (&#40;I wrote them in simple language + technical depth so you can directly use them in interviews.&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ 17.1 Android Notification System)

[//]: # ()
[//]: # (The Android Notification System allows apps to display messages outside the app UI in the notification bar.)

[//]: # ()
[//]: # (### 🔹 Key Components)

[//]: # ()
[//]: # (1. **NotificationManager**)

[//]: # ()
[//]: # (   * System service used to show notifications.)

[//]: # ()
[//]: # (2. **NotificationChannel &#40;Android 8.0+&#41;**)

[//]: # ()
[//]: # (   * Required for notifications.)

[//]: # (   * Defines importance, sound, vibration, etc.)

[//]: # ()
[//]: # (3. **NotificationCompat.Builder**)

[//]: # ()
[//]: # (   * Builds the notification.)

[//]: # ()
[//]: # (4. **PendingIntent**)

[//]: # ()
[//]: # (   * Defines action when user taps the notification.)

[//]: # ()
[//]: # (### 🔹 Flow)

[//]: # ()
[//]: # (```)

[//]: # (Create Channel → Build Notification → Notify via NotificationManager)

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val channelId = "my_channel")

[//]: # ()
[//]: # (val channel = NotificationChannel&#40;)

[//]: # (    channelId,)

[//]: # (    "My Notifications",)

[//]: # (    NotificationManager.IMPORTANCE_HIGH)

[//]: # (&#41;)

[//]: # ()
[//]: # (val manager = getSystemService&#40;NotificationManager::class.java&#41;)

[//]: # (manager.createNotificationChannel&#40;channel&#41;)

[//]: # ()
[//]: # (val intent = Intent&#40;this, MainActivity::class.java&#41;)

[//]: # (val pendingIntent = PendingIntent.getActivity&#40;this, 0, intent, 0&#41;)

[//]: # ()
[//]: # (val notification = NotificationCompat.Builder&#40;this, channelId&#41;)

[//]: # (    .setSmallIcon&#40;R.drawable.ic_notification&#41;)

[//]: # (    .setContentTitle&#40;"Hello"&#41;)

[//]: # (    .setContentText&#40;"This is a notification"&#41;)

[//]: # (    .setContentIntent&#40;pendingIntent&#41;)

[//]: # (    .setAutoCancel&#40;true&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # ()
[//]: # (manager.notify&#40;1, notification&#41;)

[//]: # (```)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ 17.2 Communication Between Notification Bar and Service)

[//]: # ()
[//]: # (A notification often communicates with a **Service** &#40;especially Foreground Service&#41;.)

[//]: # ()
[//]: # (### 🔹 Common Use Cases)

[//]: # ()
[//]: # (* Music player 🎵)

[//]: # (* Download manager ⬇️)

[//]: # (* Location tracking 📍)

[//]: # (* Background tasks)

[//]: # ()
[//]: # (### 🔹 How Communication Works)

[//]: # ()
[//]: # (### ✅ 1. Using Intent + Service)

[//]: # ()
[//]: # (Notification triggers a Service action.)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val intent = Intent&#40;this, MyService::class.java&#41;)

[//]: # (intent.action = "PLAY")

[//]: # ()
[//]: # (val pendingIntent = PendingIntent.getService&#40;this, 0, intent, 0&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ 2. Foreground Service with Notification)

[//]: # ()
[//]: # (```kotlin)

[//]: # (startForeground&#40;1, notification&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ 3. BroadcastReceiver)

[//]: # ()
[//]: # (Notification button → Broadcast → Service reacts.)

[//]: # ()
[//]: # (### ✅ 4. ViewModel / LiveData / EventBus &#40;advanced&#41;)

[//]: # ()
[//]: # (Used when UI and service must sync state.)

[//]: # ()
[//]: # (### 🔹 Interview Answer &#40;Short&#41;)

[//]: # ()
[//]: # (> Notification communicates with a Service using PendingIntent, BroadcastReceiver, or Foreground Service. The notification sends actions to the service, and the service updates the notification or app state.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ 17.3 App Shortcuts)

[//]: # ()
[//]: # (App Shortcuts provide quick actions from the app icon &#40;long press&#41;.)

[//]: # ()
[//]: # (### 🔹 Types of App Shortcuts)

[//]: # ()
[//]: # (### ✅ 1. Static Shortcuts)

[//]: # ()
[//]: # (Defined in XML &#40;Manifest&#41;.)

[//]: # ()
[//]: # (```xml)

[//]: # (<shortcuts xmlns:android="http://schemas.android.com/apk/res/android">)

[//]: # (    <shortcut)

[//]: # (        android:shortcutId="compose")

[//]: # (        android:shortLabel="Compose")

[//]: # (        android:icon="@drawable/ic_compose")

[//]: # (        android:intentAction="android.intent.action.VIEW")

[//]: # (        android:targetClass="com.example.ComposeActivity" />)

[//]: # (</shortcuts>)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ 2. Dynamic Shortcuts)

[//]: # ()
[//]: # (Created programmatically.)

[//]: # ()
[//]: # (```kotlin)

[//]: # (val shortcut = ShortcutInfo.Builder&#40;this, "id1"&#41;)

[//]: # (    .setShortLabel&#40;"Profile"&#41;)

[//]: # (    .setIntent&#40;Intent&#40;this, ProfileActivity::class.java&#41;&#41;)

[//]: # (    .build&#40;&#41;)

[//]: # ()
[//]: # (shortcutManager.dynamicShortcuts = listOf&#40;shortcut&#41;)

[//]: # (```)

[//]: # ()
[//]: # (### ✅ 3. Pinned Shortcuts)

[//]: # ()
[//]: # (Added directly to home screen.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ Interview-Ready Summary &#40;Very Useful 🔥&#41;)

[//]: # ()
[//]: # (### 🔹 Android Notification System)

[//]: # ()
[//]: # (* Displays messages outside the app.)

[//]: # (* Uses NotificationManager, Channel, Builder, PendingIntent.)

[//]: # ()
[//]: # (### 🔹 Notification ↔ Service Communication)

[//]: # ()
[//]: # (* PendingIntent)

[//]: # (* Foreground Service)

[//]: # (* BroadcastReceiver)

[//]: # (* Event-based communication)

[//]: # ()
[//]: # (### 🔹 App Shortcuts)

[//]: # ()
[//]: # (* Static &#40;XML&#41;)

[//]: # (* Dynamic &#40;Runtime&#41;)

[//]: # (* Pinned &#40;Home screen&#41;)

[//]: # ()
[//]: # (---)

[//]: # (Here are **clear, interview-ready explanations** of Kotlin JVM annotations 👇)

[//]: # (&#40;I wrote them in a way that fits perfectly in Android interviews.&#41;)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ 18.1 `@JvmStatic`)

[//]: # ()
[//]: # (### 🔹 What is `@JvmStatic`?)

[//]: # ()
[//]: # (`@JvmStatic` tells Kotlin to generate a **static method or field** for Java interoperability.)

[//]: # ()
[//]: # (### 🔹 Why needed?)

[//]: # ()
[//]: # (In Kotlin, functions inside `companion object` are not static by default.)

[//]: # (Java cannot call them like static methods unless we use `@JvmStatic`.)

[//]: # ()
[//]: # (### 🔹 Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class Utils {)

[//]: # (    companion object {)

[//]: # (        @JvmStatic)

[//]: # (        fun showMessage&#40;&#41; {)

[//]: # (            println&#40;"Hello"&#41;)

[//]: # (        })

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Java call)

[//]: # ()
[//]: # (```java)

[//]: # (Utils.showMessage&#40;&#41;;)

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Without `@JvmStatic`)

[//]: # ()
[//]: # (Java would call:)

[//]: # ()
[//]: # (```java)

[//]: # (Utils.Companion.showMessage&#40;&#41;;)

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Interview Answer)

[//]: # ()
[//]: # (> `@JvmStatic` makes Kotlin functions or properties behave like static members for Java interoperability.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ 18.2 `@JvmField`)

[//]: # ()
[//]: # (### 🔹 What is `@JvmField`?)

[//]: # ()
[//]: # (`@JvmField` exposes a Kotlin property as a **public field** instead of getter/setter.)

[//]: # ()
[//]: # (### 🔹 Why needed?)

[//]: # ()
[//]: # (By default, Kotlin generates getter/setter methods.)

[//]: # (Java cannot directly access fields without them.)

[//]: # ()
[//]: # (### 🔹 Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class Constants {)

[//]: # (    companion object {)

[//]: # (        @JvmField)

[//]: # (        val API_URL = "https://api.example.com")

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Java call)

[//]: # ()
[//]: # (```java)

[//]: # (String url = Constants.API_URL;)

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Without `@JvmField`)

[//]: # ()
[//]: # (Java would call:)

[//]: # ()
[//]: # (```java)

[//]: # (Constants.Companion.getAPI_URL&#40;&#41;;)

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Interview Answer)

[//]: # ()
[//]: # (> `@JvmField` prevents Kotlin from generating getter/setter and exposes the property as a Java field.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ 18.3 `@JvmOverloads`)

[//]: # ()
[//]: # (### 🔹 What is `@JvmOverloads`?)

[//]: # ()
[//]: # (`@JvmOverloads` generates multiple overloaded methods for Java when Kotlin uses default parameters.)

[//]: # ()
[//]: # (### 🔹 Why needed?)

[//]: # ()
[//]: # (Java does not support default arguments like Kotlin.)

[//]: # ()
[//]: # (### 🔹 Example)

[//]: # ()
[//]: # (```kotlin)

[//]: # (class User {)

[//]: # (    @JvmOverloads)

[//]: # (    fun greet&#40;name: String = "Guest", age: Int = 18&#41; {)

[//]: # (        println&#40;"Hello $name, age $age"&#41;)

[//]: # (    })

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Generated Java methods)

[//]: # ()
[//]: # (```java)

[//]: # (greet&#40;&#41;;)

[//]: # (greet&#40;String name&#41;;)

[//]: # (greet&#40;String name, int age&#41;;)

[//]: # (```)

[//]: # ()
[//]: # (### 🔹 Interview Answer)

[//]: # ()
[//]: # (> `@JvmOverloads` generates overloaded methods for Java when Kotlin functions have default parameters.)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (# ✅ Quick Interview Comparison Table 🔥)

[//]: # ()
[//]: # (| Annotation      | Purpose                        | Use Case                 |)

[//]: # (| --------------- | ------------------------------ | ------------------------ |)

[//]: # (| `@JvmStatic`    | Makes function/property static | Companion object methods |)

[//]: # (| `@JvmField`     | Exposes property as field      | Constants                |)

[//]: # (| `@JvmOverloads` | Generates overloaded methods   | Default parameters       |)

[//]: # ()
[//]: # (---)
Great 👍
Below is a **deep, senior-level explanation** of Android Architecture with **clear concepts, diagrams, examples, and interview-ready answers** in **Markdown format** (you can directly use this in GitHub `.md` files).

---

# 🧠 Android Architecture – Complete Guide (Senior Level)

---

## 1️⃣ What are Android Architecture Components?

### ✅ Definition

Android Architecture Components are part of **Android Jetpack** that help developers build **robust, scalable, maintainable, and lifecycle-aware** applications.

### ✅ Why do we need them?

Before Architecture Components:

* Memory leaks were common
* UI state was lost on rotation
* Tight coupling between UI and data
* Difficult testing
* Lifecycle issues

### ✅ Main Components

| Component       | Purpose                      |
| --------------- | ---------------------------- |
| ViewModel       | Holds UI-related data        |
| LiveData / Flow | Observable data              |
| Lifecycle       | Lifecycle-aware components   |
| Room            | Database layer               |
| DataStore       | Modern SharedPreferences     |
| Navigation      | Fragment navigation          |
| Paging          | Efficient large data loading |

### ✅ Example

```kotlin
class MainViewModel : ViewModel() {
    val count = MutableLiveData(0)
}
```

### ✅ Interview Answer

> Android Architecture Components provide lifecycle-aware tools that help manage UI data, improve code structure, and reduce memory leaks.

---

## 2️⃣ MVVM Architecture (Model–View–ViewModel)

### ✅ What is MVVM?

MVVM is a design pattern that separates UI logic from business logic.

### ✅ Layers

* **Model** → Data (API, DB, Repository)
* **View** → UI (Activity, Fragment, Compose)
* **ViewModel** → Business logic & state holder

### ✅ Data Flow

```
View → ViewModel → Repository → API/DB
ViewModel → LiveData/Flow → View
```

### ✅ Example

```kotlin
class UserViewModel(private val repo: UserRepository) : ViewModel() {
    val users = repo.getUsers()
}
```

### ✅ Benefits

* Loose coupling
* Better testability
* Lifecycle awareness
* Clean code

### ✅ Interview Answer

> MVVM separates UI and business logic, making applications scalable and testable.

---

## 3️⃣ MVC vs MVP vs MVVM

| Feature             | MVC    | MVP           | MVVM           |
| ------------------- | ------ | ------------- | -------------- |
| Coupling            | High   | Medium        | Low            |
| Testability         | Low    | Medium        | High           |
| Android suitability | ❌ Poor | ⚠️ Moderate   | ✅ Best         |
| Communication       | Direct | Via Presenter | Via Observable |

### ✅ Key Insight

> MVVM is preferred in Android because it works well with LiveData, Flow, and ViewModel.

---

## 4️⃣ Separation of Concerns (SoC)

### ✅ Meaning

Each layer should have only one responsibility.

### ✅ Example

* UI Layer → Activities/Fragments
* Business Logic → ViewModel
* Data Layer → Repository

### ❌ Bad Practice

Activity contains:

* UI logic ❌
* API calls ❌
* Database logic ❌

### ✅ Good Practice

Each responsibility is separated.

### ✅ Interview Answer

> Separation of concerns improves maintainability, readability, and scalability.

---

## 5️⃣ Clean Architecture in Android

### ✅ What is Clean Architecture?

A layered architecture that enforces dependency rules and separates business logic from frameworks.

### ✅ Layers

```
Presentation Layer → ViewModel
Domain Layer → UseCases (Business Logic)
Data Layer → Repository, API, DB
```

### ✅ Dependency Rule

```
Outer layers depend on inner layers, not vice versa.
```

### ✅ Example Structure

```
app/
 ├── presentation/
 ├── domain/
 ├── data/
```

### ✅ Interview Answer

> Clean Architecture ensures that business logic is independent of frameworks and UI.

---

## 6️⃣ Role of Repository in MVVM

### ✅ What is Repository?

Repository is a mediator between ViewModel and data sources.

### ✅ Responsibilities

* Fetch data from API
* Cache data in DB
* Decide data source

### ✅ Example

```kotlin
class UserRepository(
    private val api: ApiService,
    private val dao: UserDao
) {
    suspend fun getUsers() = api.getUsers()
}
```

### ✅ Interview Answer

> Repository abstracts data sources and provides a clean API to ViewModel.

---

## 7️⃣ Problems Solved by Architecture Components

| Problem               | Solution               |
| --------------------- | ---------------------- |
| Memory leaks          | ViewModel              |
| Lifecycle issues      | Lifecycle              |
| Data loss on rotation | SavedStateHandle       |
| Tight coupling        | MVVM                   |
| Hard testing          | Repository + ViewModel |

---

## 8️⃣ How MVVM Improves Testability

### ✅ Reasons

* ViewModel has no Android UI dependency
* Business logic is isolated
* Easy to write unit tests

### ✅ Example

```kotlin
@Test
fun testUserList() {
    val viewModel = UserViewModel(fakeRepo)
    assert(viewModel.users.isNotEmpty())
}
```

---

## 9️⃣ What is Presenter?

### ✅ Presenter (MVP)

* Handles business logic
* Acts as middle layer between View and Model
* Does not depend on Android UI

---

## 🔟 Repository Pattern

### ✅ Definition

Repository pattern hides complexity of data sources.

### ✅ Example

```
ViewModel → Repository → API / DB
```

### ✅ Benefits

* Decoupling
* Flexibility
* Maintainability

---

## 1️⃣1️⃣ Clean Code in Android

### ✅ Meaning

Code that is:

* Readable
* Maintainable
* Testable
* Simple

### ✅ Principles

* Meaningful naming
* Small functions
* DRY (Don’t Repeat Yourself)
* SOLID principles

---

## 1️⃣2️⃣ SOLID Principles in Android

| Principle | Meaning               | Example                         |
| --------- | --------------------- | ------------------------------- |
| S         | Single Responsibility | ViewModel only handles UI logic |
| O         | Open/Closed           | Extend classes                  |
| L         | Liskov Substitution   | Replace subclass                |
| I         | Interface Segregation | Small interfaces                |
| D         | Dependency Inversion  | Use DI (Hilt/Dagger)            |

---

## 1️⃣3️⃣ MVVM vs Clean Architecture

| MVVM               | Clean Architecture    |
| ------------------ | --------------------- |
| UI pattern         | System architecture   |
| Focus on ViewModel | Focus on Domain layer |
| Simple             | Complex but scalable  |
| Common in Android  | Used in large apps    |

✅ Key Point:

> MVVM can be part of Clean Architecture.

---

## 1️⃣4️⃣ Designing Scalable Android Architecture

### ✅ Best Practices

* Feature-based architecture
* Multi-module setup
* Dependency Injection (Hilt)
* Repository pattern
* Reactive programming (Flow)
* Offline-first approach

---

## 1️⃣5️⃣ Structuring Large Android Projects

### ✅ Feature-based Structure (Recommended)

```
features/
 ├── login/
 ├── home/
 ├── profile/
core/
data/
domain/
```

### ✅ Benefits

* Scalability
* Team collaboration
* Reusability

---

## 1️⃣6️⃣ Multi-Module Architecture

### ✅ What is it?

Splitting app into multiple Gradle modules.

### ✅ Types

* app module
* feature modules
* core module
* domain module
* data module

### ✅ Benefits

* Faster builds
* Better separation
* Independent development

---

## 1️⃣7️⃣ Single Source of Truth (SSOT)

### ✅ Meaning

Only one authoritative data source.

### ✅ Example

```
API → Room DB → UI
```

### ✅ Benefits

* Consistency
* Offline support
* Predictable state

---

## 1️⃣8️⃣ Offline-First Architecture

### ✅ Concept

App works without internet.

### ✅ Flow

```
API → Cache in DB → UI reads from DB
```

### ✅ Tools

* Room
* Retrofit
* WorkManager

### ✅ Interview Answer

> Offline-first architecture ensures data availability by using local storage as the primary source and syncing with the server when online.

---

Below is a **clear, deep, interview-ready explanation** in **Markdown format** (perfect for GitHub `.md` notes).
I explained concepts + differences + examples like a senior Android developer.

---

# 📌 Data Binding & View Binding in Android

---

## 1️⃣ What is Data Binding?

### ✅ Definition

**Data Binding** is a Jetpack library that allows you to bind UI components in XML layouts directly to data sources (like ViewModel, LiveData, or variables) without writing `findViewById()` or manual UI updates.

### ✅ Key Idea

> UI automatically updates when data changes.

### ✅ Example (XML)

```xml
<layout xmlns:android="http://schemas.android.com/apk/res/android">
    <data>
        <variable
            name="user"
            type="com.example.User" />
    </data>

    <TextView
        android:text="@{user.name}"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
</layout>
```

### ✅ Example (Kotlin)

```kotlin
val binding: ActivityMainBinding = DataBindingUtil.setContentView(this, R.layout.activity_main)
binding.user = User("Aasim")
```

### ✅ Benefits

* Less boilerplate code
* Reactive UI
* Better MVVM support
* Clean architecture

### ✅ Interview Answer

> Data Binding connects UI directly with data sources, reducing boilerplate code and enabling reactive UI updates.

---

## 2️⃣ What is View Binding?

### ✅ Definition

**View Binding** is a feature that generates a binding class for each XML layout file, allowing type-safe access to views without `findViewById()`.

### ✅ Example (Kotlin)

```kotlin
val binding = ActivityMainBinding.inflate(layoutInflater)
setContentView(binding.root)

binding.textView.text = "Hello Android"
```

### ✅ Key Points

* No XML expressions
* No two-way binding
* Faster and simpler than Data Binding
* Type-safe

### ✅ Interview Answer

> View Binding provides a safer and simpler way to access views without using findViewById().

---

## 3️⃣ Difference Between View Binding and Data Binding

| Feature              | View Binding    | Data Binding       |
| -------------------- | --------------- | ------------------ |
| XML expressions      | ❌ Not supported | ✅ Supported        |
| Two-way binding      | ❌ No            | ✅ Yes              |
| Binding logic in XML | ❌ No            | ✅ Yes              |
| Performance          | ✅ Faster        | ⚠️ Slightly slower |
| Complexity           | ✅ Simple        | ⚠️ Complex         |
| MVVM support         | ⚠️ Limited      | ✅ Strong           |
| Build time           | ✅ Faster        | ❌ Slower           |
| Learning curve       | ✅ Easy          | ❌ Hard             |

### ✅ Interview Answer (Short)

> View Binding is simpler and only binds views, while Data Binding allows binding data and logic directly in XML, supporting MVVM and two-way binding.

---

## 4️⃣ One-Way vs Two-Way Data Binding

### ✅ One-Way Data Binding

#### 🔹 Definition

Data flows only from **data → UI**.

#### 🔹 Example

```xml
<TextView
    android:text="@{viewModel.title}" />
```

#### 🔹 Flow

```
ViewModel → UI
```

#### 🔹 Use Case

Displaying data.

---

### ✅ Two-Way Data Binding

#### 🔹 Definition

Data flows in both directions:

* Data → UI
* UI → Data

#### 🔹 Example

```xml
<EditText
    android:text="@={viewModel.name}" />
```

#### 🔹 Flow

```
ViewModel ↔ UI
```

#### 🔹 Use Case

Forms, input fields.

---

### ✅ Difference Table

| Feature         | One-Way Binding | Two-Way Binding |
| --------------- | --------------- | --------------- |
| Data flow       | Data → UI       | Data ↔ UI       |
| Syntax          | `@{}`           | `@={}`          |
| UI updates data | ❌ No            | ✅ Yes           |
| Use case        | Display data    | User input      |

### ✅ Interview Answer

> One-way binding updates UI from data, while two-way binding synchronizes data between UI and ViewModel.

---

## 5️⃣ How to Load Image Using Data Binding

### ✅ Problem

Data Binding cannot directly load images from URLs.

### ✅ Solution

Use **Binding Adapter**.

---

### ✅ Step 1: Create Binding Adapter

```kotlin
@BindingAdapter("imageUrl")
fun loadImage(view: ImageView, url: String?) {
    if (!url.isNullOrEmpty()) {
        Glide.with(view.context)
            .load(url)
            .into(view)
    }
}
```

---

### ✅ Step 2: Use in XML

```xml
<ImageView
    android:layout_width="100dp"
    android:layout_height="100dp"
    app:imageUrl="@{viewModel.imageUrl}" />
```

---

### ✅ Interview Answer

> We use a BindingAdapter to extend Data Binding functionality and load images using libraries like Glide or Coil.

---

# 🧠 Senior-Level Insight (🔥)

### ✅ When to use View Binding?

* Simple UI
* No MVVM
* Better performance

### ✅ When to use Data Binding?

* MVVM architecture
* Reactive UI
* Complex UI logic

### ✅ Real-world practice

> Most modern Android apps use View Binding + ViewModel + Flow, and Data Binding only when necessary.

---
Perfect! Let’s go **deep and structured**. I’ll explain **ViewModel in Android** with **beginner → intermediate → advanced topics**, interview-ready, in **Markdown format** that you can directly use in GitHub notes.

---

# 🧠 Android ViewModel – Complete Guide

---

## 1️⃣ What is ViewModel and Why Do We Need It?

### ✅ Definition

**ViewModel** is a Jetpack Architecture Component that **stores and manages UI-related data** in a lifecycle-conscious way.

### ✅ Why do we need it?

1. Survives configuration changes (e.g., screen rotation)
2. Decouples UI from business logic
3. Reduces memory leaks
4. Simplifies MVVM architecture

### ✅ Example

```kotlin
class UserViewModel : ViewModel() {
    val userName = MutableLiveData<String>()
}
```

### ✅ Interview Answer

> ViewModel holds UI data and survives configuration changes, reducing boilerplate and preventing memory leaks.

---

## 2️⃣ How is ViewModel Different from Activity/Fragment?

| Feature              | Activity/Fragment    | ViewModel                        |
| -------------------- | -------------------- | -------------------------------- |
| Lifecycle            | Tied to UI component | Independent of UI lifecycle      |
| Configuration change | Recreated            | Survives rotation/config changes |
| Responsibility       | UI + logic           | Holds UI data & business logic   |
| Memory leaks         | Risky                | Safer if no context held         |

---

## 3️⃣ Does ViewModel Survive Configuration Changes?

✅ Yes.
Example: Screen rotation does **not destroy ViewModel**, only the Activity/Fragment is recreated.

---

## 4️⃣ Can ViewModel Hold a Context?

❌ **No!**

* Holding an Activity/Fragment context causes memory leaks.
* Safe to use **application context** via `AndroidViewModel`.

---

## 5️⃣ What is ViewModelProvider?

`ViewModelProvider` is used to **create or retrieve a ViewModel instance** tied to a scope (Activity/Fragment).

### Example

```kotlin
val viewModel = ViewModelProvider(this).get(UserViewModel::class.java)
```

---

## 6️⃣ Difference Between ViewModel and AndroidViewModel

| Feature  | ViewModel     | AndroidViewModel                      |
| -------- | ------------- | ------------------------------------- |
| Context  | ❌ No context  | ✅ Application context available       |
| Use case | UI state only | Needs access to Application resources |

### Example

```kotlin
class MyViewModel(application: Application) : AndroidViewModel(application) {
    val appContext = getApplication<Application>().applicationContext
}
```

---

## 7️⃣ What is SavedStateHandle?

### ✅ Definition

A **key-value store** that allows ViewModel to **save and restore UI state** across process death.

### Example

```kotlin
class MyViewModel(private val state: SavedStateHandle) : ViewModel() {
    val username: MutableLiveData<String> = state.getLiveData("username")
}
```

---

## 8️⃣ How Do You Share ViewModel Between Fragments?

Use **activityViewModels()** delegate or ViewModelProvider with Activity scope:

```kotlin
val sharedViewModel: SharedViewModel by activityViewModels()
```

> Both fragments access the **same ViewModel instance** tied to the parent Activity.

---

## 9️⃣ What is ViewModel Scope?

* ViewModel exists **as long as its owner (Activity/Fragment) exists**.
* Tied to `ViewModelStore` of the owner.
* Cleared automatically when owner is finished.

---

## 🔟 Why Should ViewModel Not Reference Views?

* Avoid memory leaks
* View lifecycle is shorter than ViewModel
* Views should observe LiveData/Flow, not be stored

---

## 1️⃣1️⃣ How is ViewModel Lifecycle-Aware?

* Automatically survives configuration changes
* Cleared only when `onCleared()` is called
* Works with LiveData and Flow to update UI safely

---

# ⚡ Intermediate Topics

## 12️⃣ What Happens When Activity is Destroyed?

* **If configuration change:** ViewModel survives
* **If Activity finishes permanently:** `onCleared()` is called and ViewModel is destroyed

---

## 13️⃣ How Do You Test ViewModel?

* Unit test by injecting **fake repository or use cases**
* Example with LiveData:

```kotlin
@Test
fun testUserNameUpdate() {
    val viewModel = UserViewModel()
    viewModel.userName.value = "Aasim"
    assertEquals("Aasim", viewModel.userName.value)
}
```

---

## 14️⃣ How to Handle Memory Leaks in ViewModel?

* Do **not hold Activity/Fragment context**
* Use **application context** if needed
* Use **weak references** for listeners or callbacks

---

## 15️⃣ Difference Between ViewModelStore and ViewModelStoreOwner

| Feature | ViewModelStore              | ViewModelStoreOwner              |
| ------- | --------------------------- | -------------------------------- |
| Purpose | Holds ViewModel instances   | Provides ViewModelStore to scope |
| Example | Internal object in Activity | Activity/Fragment implements it  |

---

## 16️⃣ ViewModel in Multi-Module Projects

* ViewModel class can reside in **feature module**
* Repositories can be injected via **DI (Hilt/Dagger)**
* Keep ViewModel **independent** of UI module for testability

---

## 17️⃣ ViewModel vs StateFlow vs LiveData

| Feature         | LiveData          | StateFlow                | ViewModel                  |
| --------------- | ----------------- | ------------------------ | -------------------------- |
| Observable      | ✅ Lifecycle-aware | ✅ Flow, requires collect | ❌ Holds data               |
| Lifecycle aware | ✅ Yes             | ❌ No                     | ✅ Depends on LiveData/Flow |
| Cold/Hot        | Hot               | Cold                     | N/A                        |
| Use case        | UI data           | Reactive streams         | Holds UI state             |

> ViewModel can expose LiveData or StateFlow.

---

## 18️⃣ How to Persist Data Across Process Death Using ViewModel?

* **SavedStateHandle** allows persisting small UI state across process death
* Combine with **Room** or **DataStore** for long-term persistence

```kotlin
class MyViewModel(private val state: SavedStateHandle) : ViewModel() {
    val count = state.getLiveData("count", 0)
}
```

---

# 🔥 Advanced Interview Notes

* ViewModel survives configuration changes but is **destroyed when Activity finishes permanently**
* Use ViewModel with **DI** in multi-module architecture
* Avoid references to **Context or Views**
* ViewModel + LiveData + StateFlow → reactive, lifecycle-aware architecture
* Use **SavedStateHandle** + DB/DataStore → offline support + process death recovery

---

# ✅ Quick Summary Table

| Concept          | Key Points                                      |
| ---------------- | ----------------------------------------------- |
| ViewModel        | Holds UI data, survives config changes          |
| AndroidViewModel | Has Application context                         |
| SavedStateHandle | Persist UI state across process death           |
| Scope            | Tied to ViewModelStoreOwner (Activity/Fragment) |
| Sharing          | Use activityViewModels() for fragments          |
| Memory leaks     | Don’t hold View/Context                         |
| Testing          | Inject fake repo, assert LiveData/Flow          |

---

Perfect! Let’s cover **LiveData in Android** comprehensively—from **basic → intermediate → advanced**—with **examples, differences, and interview-ready explanations** in Markdown.

---

# 📌 LiveData in Android – Complete Guide

---

## 1️⃣ Basics of LiveData

### ✅ What is LiveData?

**LiveData** is a lifecycle-aware observable data holder class.
It lets **UI components observe data** changes without manual lifecycle handling.

```kotlin
val userName: LiveData<String> = MutableLiveData()
```

---

### ✅ Why do we use LiveData?

1. Lifecycle-aware → avoids memory leaks
2. Automatic UI updates when data changes
3. Works seamlessly with MVVM architecture
4. Reduces boilerplate observer code

---

### ✅ Difference between LiveData and Observable

| Feature           | LiveData        | Observable                   |
| ----------------- | --------------- | ---------------------------- |
| Lifecycle-aware   | ✅ Yes           | ❌ No                         |
| UI safety         | ✅ Safe          | ❌ Needs manual handling      |
| Automatic cleanup | ✅ Yes           | ❌ No                         |
| Part of           | Android Jetpack | Java/Kotlin standard library |

---

### ✅ What is MutableLiveData?

`MutableLiveData` is a **LiveData subclass** that allows **updating data**.

```kotlin
val user = MutableLiveData<String>()
user.value = "Aasim" // setValue
user.postValue("Aasim") // postValue
```

---

### ✅ Difference between LiveData and MutableLiveData

| Feature    | LiveData                     | MutableLiveData                     |
| ---------- | ---------------------------- | ----------------------------------- |
| Modifiable | ❌ Read-only                  | ✅ Can update                        |
| Use case   | Observers                    | Data source                         |
| Example    | `val name: LiveData<String>` | `val name: MutableLiveData<String>` |

---

### ✅ Is LiveData Lifecycle-Aware?

✅ Yes.
It observes **LifecycleOwner** (Activity/Fragment) and **automatically stops updating inactive components**.

---

### ✅ How LiveData Prevents Memory Leaks

* Observers are **automatically removed** when LifecycleOwner is destroyed
* No need to manually unregister observers

---

### ✅ Difference between setValue() and postValue()

| Method      | Thread            | Immediate?                    |
| ----------- | ----------------- | ----------------------------- |
| setValue()  | Main thread       | ✅ Yes                         |
| postValue() | Background thread | ❌ Posts update asynchronously |

---

## 2️⃣ Intermediate LiveData Concepts

### ✅ Difference between LiveData and Flow

| Feature         | LiveData                          | Flow                           |
| --------------- | --------------------------------- | ------------------------------ |
| Lifecycle-aware | ✅ Yes                             | ❌ No (need lifecycleScope)     |
| Reactive        | ✅ Observer pattern                | ✅ Cold stream                  |
| Cancellation    | ✅ Auto-cancel with LifecycleOwner | ❌ Manual cancellation required |
| Use case        | UI state                          | Reactive data streams          |

---

### ✅ Difference between LiveData and RxJava

| Feature         | LiveData   | RxJava                      |
| --------------- | ---------- | --------------------------- |
| Lifecycle-aware | ✅ Yes      | ❌ No                        |
| Complexity      | Simple     | Complex, supports operators |
| Threading       | Limited    | Advanced                    |
| Use case        | UI updates | Complex reactive flows      |

---

### ✅ How does LiveData handle configuration changes?

* Observers automatically reconnect when **Activity/Fragment is recreated**
* No data loss during screen rotation

---

### ✅ What is MediatorLiveData?

* LiveData that **observes other LiveData sources**
* Combines or transforms multiple LiveData objects

```kotlin
val mediator = MediatorLiveData<String>()
mediator.addSource(user1) { mediator.value = it }
mediator.addSource(user2) { mediator.value = it }
```

---

### ✅ What is Transformations.map() and switchMap()?

```kotlin
val userId: LiveData<Int> = ...
val userName: LiveData<String> = Transformations.map(userId) { id ->
    "User$id"
}

val userLiveData: LiveData<User> = Transformations.switchMap(userId) { id ->
    repository.getUser(id)
}
```

* **map()** → transforms data
* **switchMap()** → switches to new LiveData

---

### ✅ How do you observe LiveData?

```kotlin
viewModel.user.observe(viewLifecycleOwner) { user ->
    textView.text = user.name
}
```

---

### ✅ Can LiveData be observed without LifecycleOwner?

✅ Yes, using `observeForever()`

> Must manually remove observer to avoid leaks.

```kotlin
liveData.observeForever { ... }
liveData.removeObserver(observer)
```

---

### ✅ What is SingleLiveEvent?

* Used for **one-time events** like navigation or Toast
* Avoids multiple emissions on configuration changes
* Custom implementation often used

---

## 3️⃣ Advanced LiveData Topics

### ✅ Problems with LiveData

* One-time events are tricky
* Only works on main thread for `setValue()`
* Cannot handle backpressure like Flow/RxJava
* Hard to compose multiple LiveData sources without MediatorLiveData

---

### ✅ How to handle one-time events?

* Use **SingleLiveEvent** or **Event wrapper**

```kotlin
class Event<out T>(private val content: T) {
    var handled = false
    fun getContentIfNotHandled(): T? =
        if (handled) null else { handled = true; content }
}
```

---

### ✅ LiveData vs StateFlow

| Feature          | LiveData | StateFlow     |
| ---------------- | -------- | ------------- |
| Lifecycle-aware  | ✅ Yes    | ❌ No          |
| Reactive streams | ❌        | ✅ Cold stream |
| Default value    | Optional | Required      |
| Backpressure     | ❌        | ✅             |

---

### ✅ Threading (setValue vs postValue)

* `setValue()` → main thread, immediate update
* `postValue()` → background thread, posts asynchronously

---

### ✅ Combine multiple LiveData sources

* Use **MediatorLiveData**

```kotlin
val combined = MediatorLiveData<String>()
combined.addSource(a) { combined.value = it }
combined.addSource(b) { combined.value += it }
```

---

### ✅ How to Test LiveData

* Use **InstantTaskExecutorRule** for synchronous execution

```kotlin
@get:Rule
val instantTaskExecutorRule = InstantTaskExecutorRule()

@Test
fun testLiveData() {
    val viewModel = MyViewModel()
    viewModel.data.observeForever {
        assertEquals("Hello", it)
    }
    viewModel.updateData("Hello")
}
```

---

### ✅ LiveData in Background Thread

* Use `postValue()` for background updates
* Can combine with **coroutines + LiveData builder**:

```kotlin
val data = liveData(Dispatchers.IO) {
    emit(repository.fetchData())
}
```

---

### ✅ Custom LiveData Implementation

```kotlin
class TimerLiveData : LiveData<Int>() {
    private var counter = 0
    private val handler = Handler(Looper.getMainLooper())
    
    private val runnable = object : Runnable {
        override fun run() {
            counter++
            value = counter
            handler.postDelayed(this, 1000)
        }
    }

    override fun onActive() {
        handler.post(runnable)
    }

    override fun onInactive() {
        handler.removeCallbacks(runnable)
    }
}
```

---

# ✅ Quick Summary Table

| Concept            | Key Points                                   |
| ------------------ | -------------------------------------------- |
| LiveData           | Lifecycle-aware, observable UI data holder   |
| MutableLiveData    | Allows data updates                          |
| MediatorLiveData   | Combines multiple sources                    |
| Transformations    | Map or switch LiveData                       |
| SingleLiveEvent    | Handles one-time events                      |
| LiveData vs Flow   | LiveData lifecycle-aware, Flow more reactive |
| LiveData vs RxJava | LiveData simple, RxJava advanced streams     |
| Threading          | setValue → main, postValue → background      |

---

Perfect! Let’s create a **full, structured explanation of Android Lifecycle and related concepts** in **Markdown**, suitable for GitHub notes or interview prep.

---

# 📌 Android Lifecycle – Complete Guide

---

## 1️⃣ What is Lifecycle?

**Lifecycle** in Android represents the **states and events of a component** (Activity/Fragment) from creation to destruction.

* Helps components **observe lifecycle changes** safely.
* Prevents **memory leaks** by knowing when a component is active/inactive.
* Introduced as part of **Android Jetpack Lifecycle library**.

```kotlin
lifecycle.addObserver(MyObserver())
```

---

## 2️⃣ What is LifecycleOwner?

* **LifecycleOwner** is an interface implemented by classes that have a lifecycle (Activity, Fragment, or custom classes).
* Provides access to the component’s **Lifecycle object**.

```kotlin
class MainActivity : AppCompatActivity(), LifecycleOwner {
    // lifecycle property is available by default
}
```

> Most Activities and Fragments already implement LifecycleOwner.

---

## 3️⃣ What is LifecycleObserver?

* **LifecycleObserver** allows a class to **observe lifecycle events** of a LifecycleOwner.
* It avoids putting lifecycle logic directly inside Activity/Fragment.

```kotlin
class MyObserver : LifecycleObserver {

    @OnLifecycleEvent(Lifecycle.Event.ON_RESUME)
    fun onResume() {
        // do something when resumed
    }
}
```

---

## 4️⃣ Lifecycle Events

**Lifecycle Events** correspond to **changes in the lifecycle state** of Activity/Fragment:

| Event        | Trigger                            |
| ------------ | ---------------------------------- |
| `ON_CREATE`  | Activity/Fragment is created       |
| `ON_START`   | Component is visible               |
| `ON_RESUME`  | Component is interacting with user |
| `ON_PAUSE`   | Component partially hidden         |
| `ON_STOP`    | Component completely hidden        |
| `ON_DESTROY` | Component is destroyed             |
| `ON_ANY`     | Triggered on any event             |

---

## 5️⃣ Lifecycle States

| State         | Description                           |
| ------------- | ------------------------------------- |
| `INITIALIZED` | Object created but not started        |
| `CREATED`     | `onCreate()` called                   |
| `STARTED`     | Visible to user (`onStart()`)         |
| `RESUMED`     | Active and interacting (`onResume()`) |
| `DESTROYED`   | Component destroyed                   |

---

## 6️⃣ DefaultLifecycleObserver vs LifecycleEventObserver

| Feature   | DefaultLifecycleObserver       | LifecycleEventObserver         |
| --------- | ------------------------------ | ------------------------------ |
| Interface | Default methods for each event | Single callback for all events |
| Usage     | `onCreate`, `onResume` etc.    | `onStateChanged(owner, event)` |
| Syntax    | Cleaner, modern                | Flexible but verbose           |

```kotlin
class MyObserver : DefaultLifecycleObserver {
    override fun onResume(owner: LifecycleOwner) {
        println("Resumed")
    }
}
```

---

## 7️⃣ Lifecycle with ViewModel

* **ViewModel** is lifecycle-aware **but not tied to UI states like onPause/onResume**.
* Survives configuration changes.
* Works together with Lifecycle to prevent memory leaks:

```kotlin
val viewModel = ViewModelProvider(this).get(MyViewModel::class.java)
```

> onCleared() is called when LifecycleOwner is finished permanently.

---

## 8️⃣ Lifecycle with LiveData

* **LiveData** observes LifecycleOwner.
* Only sends updates **when owner is in STARTED/RESUMED state**.
* Automatically removes observers when owner is destroyed.

```kotlin
viewModel.user.observe(viewLifecycleOwner) { user ->
    textView.text = user.name
}
```

> No need to manually unregister observers → prevents memory leaks.

---

## 9️⃣ LifecycleScope

* **LifecycleScope** is a **CoroutineScope** tied to LifecycleOwner.
* Automatically cancels coroutines when LifecycleOwner is destroyed.

```kotlin
lifecycleScope.launch {
    repeat(5) { delay(1000); println("Tick $it") }
}
```

### Variants

| Scope                               | Lifetime                                |
| ----------------------------------- | --------------------------------------- |
| `lifecycleScope`                    | Active during LifecycleOwner lifetime   |
| `viewLifecycleOwner.lifecycleScope` | Fragment view lifetime                  |
| `repeatOnLifecycle`                 | Coroutine runs only in a specific state |

```kotlin
lifecycleScope.launch {
    repeatOnLifecycle(Lifecycle.State.STARTED) {
        flow.collect { println(it) }
    }
}
```

---

# ✅ Quick Summary Table

| Concept                  | Key Points                                                    |
| ------------------------ | ------------------------------------------------------------- |
| Lifecycle                | Represents states/events of Activity/Fragment                 |
| LifecycleOwner           | Provides Lifecycle object (Activity/Fragment)                 |
| LifecycleObserver        | Observes lifecycle events externally                          |
| DefaultLifecycleObserver | Clean, default methods for each event                         |
| LifecycleEventObserver   | Generic, handles all events                                   |
| Lifecycle Events         | ON_CREATE, ON_START, ON_RESUME, ON_PAUSE, ON_STOP, ON_DESTROY |
| Lifecycle States         | INITIALIZED, CREATED, STARTED, RESUMED, DESTROYED             |
| ViewModel + Lifecycle    | Survives config changes, cleared on finish                    |
| LiveData + Lifecycle     | Updates UI only in active states, auto cleans up              |
| LifecycleScope           | CoroutineScope tied to Lifecycle, auto cancels                |

---

Perfect! Let’s cover **Room Database** in Android comprehensively in **Markdown format**, structured for **basic → intermediate topics** with examples and interview-ready explanations.

---

# 📌 Room Database – Complete Guide

---

## 1️⃣ Basics of Room

### ✅ What is Room Database?

**Room** is a **Jetpack persistence library** that provides an **abstraction layer over SQLite** to allow **robust database access** while harnessing SQLite’s full power.

* Type-safe queries
* Compile-time verification of SQL queries
* Integration with LiveData and Coroutines

```kotlin
@Entity(tableName = "users")
data class User(
    @PrimaryKey val id: Int,
    val name: String,
    val age: Int
)
```

---

### ✅ Why use Room instead of SQLite?

| Feature                       | SQLite   | Room                      |
| ----------------------------- | -------- | ------------------------- |
| Boilerplate                   | High     | Low                       |
| Compile-time SQL verification | ❌ No     | ✅ Yes                     |
| Observable queries            | ❌ No     | ✅ LiveData / Flow support |
| Coroutines support            | ❌ Manual | ✅ Built-in                |
| Type safety                   | ❌ Weak   | ✅ Strong                  |

> Room reduces errors and improves maintainability compared to raw SQLite.

---

### ✅ What are the Main Components of Room?

1. **Entity** – Represents a table in the database.
2. **DAO (Data Access Object)** – Defines SQL queries and methods to access data.
3. **Database class** – The main access point to the database.

---

### ✅ What is Entity in Room?

* Annotated class representing a **table**
* Fields represent **columns**

```kotlin
@Entity(tableName = "users")
data class User(
    @PrimaryKey val id: Int,
    val name: String
)
```

---

### ✅ What is DAO?

* **DAO** (Data Access Object) defines database operations
* Methods annotated with `@Insert`, `@Update`, `@Delete`, `@Query`

```kotlin
@Dao
interface UserDao {
    @Insert
    suspend fun insertUser(user: User)

    @Query("SELECT * FROM users WHERE id = :id")
    fun getUserById(id: Int): LiveData<User>
}
```

---

### ✅ What is Database Class in Room?

* Abstract class annotated with `@Database`
* Provides **singleton database instance**
* Defines **entities and version**

```kotlin
@Database(entities = [User::class], version = 1)
abstract class AppDatabase : RoomDatabase() {
    abstract fun userDao(): UserDao
}
```

---

### ✅ Difference Between Room and SQLite

| Feature                  | SQLite | Room |
| ------------------------ | ------ | ---- |
| Boilerplate code         | High   | Low  |
| Compile-time query check | ❌      | ✅    |
| LiveData / Flow support  | ❌      | ✅    |
| Coroutine support        | ❌      | ✅    |
| Type safety              | ❌      | ✅    |

---

## 2️⃣ Intermediate Room Concepts

### ✅ What is Migration in Room?

* Migration handles **schema changes** between database versions
* Prevents data loss

```kotlin
val MIGRATION_1_2 = object : Migration(1, 2) {
    override fun migrate(database: SupportSQLiteDatabase) {
        database.execSQL("ALTER TABLE users ADD COLUMN phone TEXT")
    }
}
```

---

### ✅ What is PrimaryKey in Room?

* Annotates a column as the **primary key**
* Can be auto-generated

```kotlin
@PrimaryKey(autoGenerate = true)
val id: Int
```

---

### ✅ Difference Between suspend Functions and LiveData in DAO

| Feature   | suspend Function      | LiveData               |
| --------- | --------------------- | ---------------------- |
| Execution | Needs Coroutine       | Observed automatically |
| Threading | Can run in background | Observes lifecycle     |
| Use case  | Single operation      | UI updates reactively  |

---

### ✅ How Does Room Support Coroutines?

* DAO methods can be `suspend`
* Works with **Flow** for reactive streams

```kotlin
@Dao
interface UserDao {
    @Query("SELECT * FROM users")
    fun getUsersFlow(): Flow<List<User>>
}
```

---

### ✅ How Does Room Handle Threading?

* Database queries **cannot run on main thread**
* Room throws **RuntimeException** if you attempt main thread access
* Use Coroutines or Executors for background threads

```kotlin
GlobalScope.launch {
    userDao.insertUser(user)
}
```

---

### ✅ What is @Query Annotation?

* Defines **custom SQL queries** in DAO
* Can return `LiveData`, `Flow`, or direct results

```kotlin
@Query("SELECT * FROM users WHERE age > :minAge")
fun getUsersAbove(minAge: Int): LiveData<List<User>>
```

---

### ✅ What is @Insert, @Update, @Delete?

| Annotation | Purpose                                        |
| ---------- | ---------------------------------------------- |
| @Insert    | Inserts entity/entities into table             |
| @Update    | Updates existing entities based on primary key |
| @Delete    | Deletes entities from table                    |

```kotlin
@Insert
suspend fun addUser(user: User)

@Update
suspend fun updateUser(user: User)

@Delete
suspend fun deleteUser(user: User)
```

---

# ✅ Quick Summary Table

| Concept            | Key Points                                |
| ------------------ | ----------------------------------------- |
| Room Database      | Jetpack library, abstraction over SQLite  |
| Entity             | Table representation                      |
| DAO                | Defines database operations               |
| Database class     | Main access point, provides DAO           |
| Migration          | Handles schema changes                    |
| Coroutines support | `suspend` functions, Flow                 |
| Threading          | Not allowed on main thread                |
| Annotations        | `@Insert`, `@Update`, `@Delete`, `@Query` |

---
Perfect! Let’s create a **comprehensive guide for Android Navigation Component** in **Markdown format**, structured for **basic → intermediate topics** with examples and interview-ready explanations.

---

# 📌 Android Navigation Component – Complete Guide

---

## 1️⃣ Basics of Navigation Component

### ✅ What is Navigation Component?

**Navigation Component** is a **Jetpack library** that handles **fragment navigation, argument passing, and backstack management** in a consistent and safe way.

* Reduces boilerplate code for fragment transactions
* Ensures **type-safe navigation**
* Supports **Deep Linking** and **animations**

```kotlin
// Example of navigating from Fragment A to Fragment B
findNavController().navigate(R.id.action_fragmentA_to_fragmentB)
```

---

### ✅ Why Use Navigation Component?

1. **Simplifies fragment transactions**
2. **Automatic back stack handling**
3. **Safe argument passing** (Safe Args)
4. **Supports deep linking and nested navigation**
5. **Integrates with UI components** like BottomNavigationView

---

### ✅ What is NavHostFragment?

* A **container for fragments** managed by Navigation Component
* Acts as the **navigation graph host**

```xml
<fragment
    android:id="@+id/nav_host_fragment"
    android:name="androidx.navigation.fragment.NavHostFragment"
    app:navGraph="@navigation/nav_graph"
    app:defaultNavHost="true"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

> `defaultNavHost="true"` ensures **back button handling** is delegated to NavController.

---

### ✅ What is NavController?

* **NavController** is the **central API** for navigation operations
* Controls **navigation actions**, **back stack**, and **deep links**

```kotlin
val navController = findNavController(R.id.nav_host_fragment)
navController.navigate(R.id.fragmentB)
```

---

### ✅ What is Navigation Graph?

* XML file that **defines all possible destinations** and actions
* Provides **visual representation** of app navigation
* Supports **nested graphs, actions, and arguments**

```xml
<navigation xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/nav_graph"
    app:startDestination="@id/fragmentA">

    <fragment
        android:id="@+id/fragmentA"
        android:name="com.example.FragmentA"
        android:label="Fragment A" >
        <action
            android:id="@+id/action_fragmentA_to_fragmentB"
            app:destination="@id/fragmentB" />
    </fragment>

    <fragment
        android:id="@+id/fragmentB"
        android:name="com.example.FragmentB"
        android:label="Fragment B" />
</navigation>
```

---

### ✅ Difference between FragmentManager and NavController

| Feature             | FragmentManager              | NavController          |
| ------------------- | ---------------------------- | ---------------------- |
| Navigation handling | Manual fragment transactions | Declarative navigation |
| Back stack          | Manual management            | Automatic              |
| Type-safe args      | ❌                            | ✅ (Safe Args)          |
| Deep linking        | Manual                       | ✅ Built-in             |
| Animations          | Manual                       | Easy via graph         |

---

## 2️⃣ Intermediate Navigation Component Concepts

### ✅ Safe Args in Navigation

* **Gradle plugin** that generates **type-safe classes** for fragment arguments
* Avoids runtime crashes due to wrong argument types

```kotlin
// Passing data
val action = FragmentADirections.actionFragmentAToFragmentB(userId = 101)
findNavController().navigate(action)

// Receiving data
val args: FragmentBArgs by navArgs()
val userId = args.userId
```

---

### ✅ How to Pass Data Between Fragments

1. Using **Safe Args (recommended)**
2. Using **Bundle**
3. Using **Shared ViewModel** (Activity scope)

```kotlin
// Bundle approach
val bundle = bundleOf("userId" to 101)
findNavController().navigate(R.id.fragmentB, bundle)
```

---

### ✅ Deep Linking in Navigation

* Allows **launching fragments from external URLs or notifications**
* Defined in **navigation graph**

```xml
<fragment
    android:id="@+id/fragmentB"
    android:name="com.example.FragmentB"
    android:label="Fragment B">
    <deepLink
        android:id="@+id/deepLink"
        app:uri="https://www.example.com/details/{id}" />
</fragment>
```

```kotlin
// NavController automatically parses deep link arguments
```

---

### ✅ Difference between popBackStack() and navigateUp()

| Method           | Description                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------------------- |
| `popBackStack()` | Pops the back stack to a specific destination or just the current destination                   |
| `navigateUp()`   | Navigates **up in the navigation hierarchy**, respecting **parent graphs and drawer hierarchy** |

```kotlin
// Pop current fragment
navController.popBackStack()

// Navigate up in graph
navController.navigateUp()
```

---

# ✅ Quick Summary Table

| Concept              | Key Points                                      |
| -------------------- | ----------------------------------------------- |
| Navigation Component | Jetpack library for fragment navigation         |
| NavHostFragment      | Container for fragments in graph                |
| NavController        | Manages navigation, back stack, deep links      |
| Navigation Graph     | Defines destinations, actions, and arguments    |
| Safe Args            | Type-safe argument passing                      |
| Deep Linking         | Open fragments from external URLs/notifications |
| popBackStack()       | Pops back stack programmatically                |
| navigateUp()         | Navigates up in hierarchy respecting graph      |

---


Perfect! Let’s cover **Android DataStore** comprehensively in **Markdown**, with examples, differences, and interview-ready explanations.

---

# 📌 Android DataStore – Complete Guide

---

## 1️⃣ What is DataStore?

**DataStore** is a Jetpack library for **storing key-value pairs or typed objects**.
It is designed to **replace SharedPreferences** with a modern, **asynchronous, and safer API**.

* Works with **Kotlin Coroutines** and **Flow**
* Handles **data consistency** automatically
* Provides two types: **Preferences DataStore** and **Proto DataStore**

```kotlin
val dataStore: DataStore<Preferences> = context.createDataStore(name = "settings")
```

---

## 2️⃣ Difference Between SharedPreferences and DataStore

| Feature         | SharedPreferences | DataStore                 |
| --------------- | ----------------- | ------------------------- |
| Threading       | Synchronous       | Asynchronous (Coroutines) |
| Data Safety     | No type safety    | Type-safe (Proto)         |
| API             | Blocking I/O      | Non-blocking (Flow)       |
| Transactions    | Manual            | Atomic & safe             |
| Modern approach | ❌                 | ✅ Jetpack library         |

---

## 3️⃣ Types of DataStore

1. **Preferences DataStore** – Stores **key-value pairs**, similar to SharedPreferences
2. **Proto DataStore** – Stores **typed objects** defined via **ProtoBuf schema**

---

## 4️⃣ Proto DataStore vs Preferences DataStore

| Feature       | Preferences DataStore | Proto DataStore               |
| ------------- | --------------------- | ----------------------------- |
| Type          | Key-value             | Typed objects (ProtoBuf)      |
| Schema        | No schema             | Strong schema                 |
| Type Safety   | ❌                     | ✅                             |
| Migration     | Simple                | Needs Proto schema definition |
| Serialization | Automatic             | Uses ProtoBuf                 |

```kotlin
// Proto DataStore example
val Context.userDataStore: DataStore<UserPreferences> by dataStore(
    fileName = "user_prefs.pb",
    serializer = UserPreferencesSerializer
)
```

---

## 5️⃣ Why is DataStore Asynchronous?

* Built with **Kotlin Coroutines & Flow**
* Avoids **blocking main thread**
* Supports **non-blocking reads/writes**

```kotlin
val userNameFlow: Flow<String> = dataStore.data
    .map { preferences -> preferences[USER_NAME_KEY] ?: "" }
```

---

## 6️⃣ DataStore vs Room

| Feature       | DataStore                   | Room                       |
| ------------- | --------------------------- | -------------------------- |
| Use case      | Small key-value or settings | Complex relational data    |
| Threading     | Async by default            | Needs Coroutines/Executors |
| Type safety   | Preferences: No, Proto: Yes | ✅ Strong                   |
| Querying      | Key-value access            | SQL queries                |
| Observability | Flow                        | LiveData / Flow            |

> Use **DataStore** for **app settings**, **Room** for **structured relational data**.

---

## 7️⃣ DataStore with Flow

* DataStore **emits data as Flow**
* Supports **reactive programming**

```kotlin
val userAgeFlow: Flow<Int> = dataStore.data
    .map { preferences -> preferences[USER_AGE_KEY] ?: 0 }

lifecycleScope.launch {
    userAgeFlow.collect { age ->
        textView.text = "Age: $age"
    }
}
```

---

## 8️⃣ Migration from SharedPreferences to DataStore

* Jetpack provides **automatic migration**

```kotlin
val dataStore: DataStore<Preferences> = context.createDataStore(
    name = "settings",
    migrations = listOf(SharedPreferencesMigration(context, "old_prefs"))
)
```

* Reads **old SharedPreferences** and writes to **DataStore** automatically

---

# ✅ Quick Summary Table

| Concept                        | Key Points                                          |
| ------------------------------ | --------------------------------------------------- |
| DataStore                      | Modern Jetpack library for key-value or typed data  |
| Types                          | Preferences (key-value), Proto (typed objects)      |
| Asynchronous                   | Coroutines-based, non-blocking                      |
| Flow Integration               | Reactive updates for UI                             |
| SharedPreferences vs DataStore | Async, type-safe, safer API                         |
| DataStore vs Room              | Settings → DataStore, Complex DB → Room             |
| Migration                      | Supports automatic migration from SharedPreferences |

---

Perfect! Let’s cover **WorkManager in Android** comprehensively in **Markdown format**, structured into **Basic → Intermediate → Advanced**, with examples and interview-ready explanations.

---

# 📌 Android WorkManager – Complete Guide

---

## 1️⃣ Basics of WorkManager

### ✅ What is WorkManager?

**WorkManager** is a Jetpack library for **deferrable, guaranteed background work** that **needs to run even if the app exits or the device restarts**.

* Handles **background tasks** safely
* Supports **constraints**, **chaining**, and **retry policies**
* Recommended for **persistent background work**

```kotlin
class MyWorker(
    context: Context,
    params: WorkerParameters
) : Worker(context, params) {
    override fun doWork(): Result {
        // Background task
        return Result.success()
    }
}

// Enqueue work
val workRequest = OneTimeWorkRequestBuilder<MyWorker>().build()
WorkManager.getInstance(context).enqueue(workRequest)
```

---

### ✅ Difference Between WorkManager, JobScheduler, AlarmManager, and Services

| Feature                | WorkManager                 | JobScheduler    | AlarmManager     | Services               |
| ---------------------- | --------------------------- | --------------- | ---------------- | ---------------------- |
| Guaranteed execution   | ✅ Yes                       | ✅ Yes (API 21+) | ❌ Not guaranteed | ❌ Depends on app alive |
| Backward compatibility | ✅ API 14+                   | ❌ API 21+       | ✅ All            | ✅ All                  |
| Constraints            | ✅ Yes                       | ✅ Yes           | ❌ Limited        | ❌ Limited              |
| Chaining tasks         | ✅ Yes                       | ❌ No            | ❌ No             | ❌ No                   |
| Use case               | Deferrable background tasks | Scheduled jobs  | Alarms/timers    | Long-running tasks     |

---

### ✅ When to Use WorkManager?

* Background data sync
* Upload logs or files
* Send analytics events
* Periodic tasks with constraints
* Tasks that must **run even if app is killed or device restarts**

---

### ✅ What is Worker Class?

* **Worker** is the **base class** for all WorkManager tasks
* Override `doWork()` to define task logic

```kotlin
class UploadWorker(
    context: Context,
    params: WorkerParameters
) : Worker(context, params) {
    override fun doWork(): Result {
        uploadFile()
        return Result.success()
    }
}
```

---

## 2️⃣ Intermediate WorkManager Concepts

### ✅ Constraints in WorkManager

* Work can be constrained based on:

```kotlin
val constraints = Constraints.Builder()
    .setRequiredNetworkType(NetworkType.CONNECTED)
    .setRequiresBatteryNotLow(true)
    .setRequiresCharging(true)
    .build()
```

* Example: only run task when **device is charging and network is connected**

---

### ✅ OneTimeWorkRequest vs PeriodicWorkRequest

| Feature          | OneTimeWorkRequest | PeriodicWorkRequest     |
| ---------------- | ------------------ | ----------------------- |
| Runs             | Once               | Repeatedly at intervals |
| Example          | Upload logs        | Sync database every 24h |
| Minimum interval | N/A                | 15 minutes              |

```kotlin
val periodicWork = PeriodicWorkRequestBuilder<MyWorker>(24, TimeUnit.HOURS).build()
WorkManager.getInstance(context).enqueue(periodicWork)
```

---

### ✅ Chaining Work in WorkManager

* Tasks can run **sequentially or in parallel**

```kotlin
val work1 = OneTimeWorkRequestBuilder<WorkerA>().build()
val work2 = OneTimeWorkRequestBuilder<WorkerB>().build()

WorkManager.getInstance(context)
    .beginWith(work1)
    .then(work2)
    .enqueue()
```

---

### ✅ WorkManager with Coroutines

* Use **CoroutineWorker** for coroutine support

```kotlin
class MyCoroutineWorker(
    context: Context,
    params: WorkerParameters
) : CoroutineWorker(context, params) {
    override suspend fun doWork(): Result {
        fetchDataFromNetwork()
        return Result.success()
    }
}
```

---

### ✅ WorkManager vs ForegroundService

| Feature              | WorkManager                | ForegroundService                           |
| -------------------- | -------------------------- | ------------------------------------------- |
| Guaranteed execution | ✅ Yes                      | ❌ Only while service is alive               |
| Lifecycle-aware      | ✅ Managed                  | ❌ Needs manual handling                     |
| Constraints          | ✅ Yes                      | ❌ Limited                                   |
| Use case             | Deferrable background work | Real-time tasks requiring user notification |

---

## 3️⃣ Advanced WorkManager Concepts

### ✅ WorkManager for Background Sync

* Ideal for **syncing server data periodically**
* Respects **device constraints and backoff policies**

```kotlin
val syncWork = PeriodicWorkRequestBuilder<SyncWorker>(12, TimeUnit.HOURS)
    .setConstraints(constraints)
    .build()
WorkManager.getInstance(context).enqueue(syncWork)
```

---

### ✅ WorkManager with Room

* Combine WorkManager with Room for **offline-first architecture**

```kotlin
class SyncWorker(
    context: Context,
    params: WorkerParameters
) : CoroutineWorker(context, params) {

    val db = AppDatabase.getInstance(context)

    override suspend fun doWork(): Result {
        val unsyncedData = db.dao().getUnsyncedData()
        uploadToServer(unsyncedData)
        db.dao().markAsSynced(unsyncedData)
        return Result.success()
    }
}
```

---

### ✅ Handling Retries and Failures

* Use **Result.retry()** for transient errors
* Use **Result.failure()** for permanent failure

```kotlin
override suspend fun doWork(): Result {
    return try {
        uploadFile()
        Result.success()
    } catch (e: IOException) {
        Result.retry()
    }
}
```

---

### ✅ WorkManager vs Firebase JobDispatcher

| Feature                  | WorkManager | Firebase JobDispatcher    |
| ------------------------ | ----------- | ------------------------- |
| Official Jetpack library | ✅ Yes       | ❌ Deprecated              |
| API support              | API 14+     | API 14+ (Firebase only)   |
| Reliability              | High        | Moderate                  |
| Constraints & chaining   | ✅ Yes       | Limited                   |
| Recommendation           | ✅ Preferred | ❌ Use WorkManager instead |

---

### ✅ Testing WorkManager

* Use **TestDriver** and **WorkManagerTestRule**
* Example: check work execution

```kotlin
@get:Rule
val workManagerTestRule = WorkManagerTestRule()

@Test
fun testWork() {
    val workRequest = OneTimeWorkRequestBuilder<MyWorker>().build()
    WorkManager.getInstance(context).enqueue(workRequest)
    workManagerTestRule.testDriver.setAllConstraintsMet(workRequest.id)
}
```

---

# ✅ Quick Summary Table

| Concept                          | Key Points                                     |
| -------------------------------- | ---------------------------------------------- |
| WorkManager                      | Jetpack library for deferrable background work |
| Worker                           | Base class defining tasks                      |
| Constraints                      | Network, charging, battery, storage            |
| OneTime vs Periodic              | Single vs repeated execution                   |
| Chaining                         | Sequential or parallel work                    |
| CoroutineWorker                  | Coroutine-based background work                |
| Retry & Failure                  | Result.retry(), Result.failure()               |
| WorkManager + Room               | Offline-first data sync                        |
| WorkManager vs ForegroundService | Guaranteed vs real-time                        |
| WorkManager vs JobDispatcher     | WorkManager preferred                          |

---

Perfect! Let’s create a **complete Markdown guide** for the **Repository Pattern in Android**, with **basic → advanced concepts**, examples, and explanations for MVVM and Clean Architecture.

---

# 📌 Repository Pattern – Complete Guide

---

## 1️⃣ Basics of Repository Pattern

### ✅ What is Repository Pattern?

The **Repository Pattern** is a design pattern that **abstracts data access**, providing a **clean API for the rest of the app**.

* Acts as a **single source of truth**
* Hides whether data comes from **Room, Retrofit, Cache, or other sources**
* Makes **MVVM and Clean Architecture** maintainable and testable

```kotlin
class UserRepository(
    private val userDao: UserDao,
    private val apiService: ApiService
) {

    val users: Flow<List<User>> = userDao.getAllUsers()

    suspend fun refreshUsers() {
        val usersFromApi = apiService.getUsers()
        userDao.insertUsers(usersFromApi)
    }
}
```

---

### ✅ Why Do We Need Repository in MVVM?

* MVVM **ViewModel should not know data source details**
* Repository **centralizes data access** and provides a clean API to ViewModel

```kotlin
class UserViewModel(private val repository: UserRepository) : ViewModel() {

    val users = repository.users.asLiveData()

    fun refresh() = viewModelScope.launch {
        repository.refreshUsers()
    }
}
```

---

### ✅ Repository vs DAO

| Feature        | DAO                     | Repository                       |
| -------------- | ----------------------- | -------------------------------- |
| Layer          | Data access only        | Data abstraction layer           |
| Scope          | Single table/entity     | Multiple tables, remote + local  |
| Responsibility | Executes SQL / queries  | Exposes unified API to ViewModel |
| Example        | `userDao.getAllUsers()` | `userRepository.users`           |

---

### ✅ Repository vs UseCase

| Feature | Repository              | UseCase (Interactor)        |
| ------- | ----------------------- | --------------------------- |
| Purpose | Provides data           | Encapsulates business logic |
| Layer   | Data layer              | Domain layer                |
| Example | Fetch users from DB/API | Filter users older than 18  |

---

### ✅ Single Source of Truth

* Repository ensures **all data comes from a single source**
* Prevents inconsistencies between **local cache and remote data**

```kotlin
fun getUsers(): Flow<List<User>> = flow {
    val localData = userDao.getAllUsersOnce()
    emit(localData)
    val remoteData = apiService.getUsers()
    userDao.insertUsers(remoteData)
    emit(userDao.getAllUsersOnce())
}
```

---

## 2️⃣ Intermediate Concepts

### ✅ Repository with Multiple Data Sources

* Repository can **combine Room + Retrofit + Cache**

```kotlin
class PostRepository(
    private val postDao: PostDao,
    private val apiService: ApiService,
    private val cache: Cache
) {
    fun getPosts(): Flow<List<Post>> = flow {
        emit(cache.getPosts())
        val postsFromDb = postDao.getAllPosts()
        emit(postsFromDb)
        val postsFromApi = apiService.getPosts()
        postDao.insertPosts(postsFromApi)
        emit(postsFromApi)
    }
}
```

---

### ✅ Offline-First Architecture

* Repository **checks local database first**, fetches remote if needed
* Ensures **app works without network**

```kotlin
fun getUserProfile(userId: Int): Flow<User> = flow {
    val localUser = userDao.getUserById(userId)
    emit(localUser)
    try {
        val remoteUser = apiService.getUser(userId)
        userDao.updateUser(remoteUser)
        emit(remoteUser)
    } catch (e: Exception) {
        // fallback to local data
        emit(localUser)
    }
}
```

---

### ✅ Repository with Retrofit and Room

* Common pattern: **NetworkBoundResource**

```kotlin
class NetworkBoundRepository(
    private val userDao: UserDao,
    private val apiService: ApiService
) {
    fun getUsers(): Flow<List<User>> = flow {
        val cachedUsers = userDao.getAllUsers()
        emit(cachedUsers)
        val apiUsers = apiService.getUsers()
        userDao.insertUsers(apiUsers)
        emit(userDao.getAllUsers())
    }
}
```

---

### ✅ Repository in Clean Architecture

* **Domain layer** calls **Repository interface**
* **Data layer** implements repository
* Allows **dependency inversion**

```kotlin
// Domain layer
interface UserRepository {
    fun getUsers(): Flow<List<User>>
}

// Data layer
class UserRepositoryImpl(
    private val userDao: UserDao,
    private val apiService: ApiService
) : UserRepository {
    override fun getUsers(): Flow<List<User>> = TODO()
}
```

---

## 3️⃣ Advanced Topics

### ✅ Testing Repository

* Can **mock DAO and API** for unit tests

```kotlin
@Test
fun `getUsers returns combined data`() = runBlockingTest {
    val fakeDao = FakeUserDao()
    val fakeApi = FakeApiService()
    val repo = UserRepository(fakeDao, fakeApi)

    val result = repo.getUsers().first()
    assertEquals(fakeDao.users, result)
}
```

---

### ✅ Benefits of Repository Pattern

* Decouples **data sources from ViewModel**
* Enables **offline-first architecture**
* Provides **single source of truth**
* Makes **testing easier**

---

# ✅ Quick Summary Table

| Concept                      | Key Points                                             |
| ---------------------------- | ------------------------------------------------------ |
| Repository Pattern           | Abstraction over data sources for clean API            |
| Repository in MVVM           | Centralizes data for ViewModel                         |
| Repository vs DAO            | DAO = data access, Repository = abstraction layer      |
| Repository vs UseCase        | Repository = data, UseCase = business logic            |
| Single source of truth       | All data flows through repository                      |
| Multiple data sources        | Combine Room + Retrofit + Cache                        |
| Offline-first                | Emit local data first, then fetch remote               |
| Repository + Retrofit + Room | Common pattern for syncing local + remote              |
| Clean Architecture           | Repository interface in domain, implementation in data |

---

Perfect! Let’s cover **Dependency Injection (DI) in Android** in a **Markdown-ready, interview-focused format**, including Hilt, Dagger, Koin, scopes, annotations, and Clean Architecture integration.

---

# 📌 Dependency Injection (DI) in Android – Complete Guide

---

## 1️⃣ Basics of Dependency Injection

### ✅ What is Dependency Injection?

**Dependency Injection (DI)** is a design pattern in which **an object receives its dependencies from an external source rather than creating them itself**.

* Promotes **loose coupling**
* Improves **testability and maintainability**
* Makes it easier to **swap implementations**

```kotlin
// Without DI
class UserRepository {
    private val apiService = ApiService() // tightly coupled
}

// With DI
class UserRepository @Inject constructor(private val apiService: ApiService)
```

---

### ✅ Problems Without DI

* **Tight coupling** between classes
* Hard to **test components independently**
* **Difficult to scale** large applications
* **Manual object creation** across app layers

---

## 2️⃣ Hilt vs Dagger vs Koin

| Feature             | Dagger                           | Hilt                          | Koin                                     |
| ------------------- | -------------------------------- | ----------------------------- | ---------------------------------------- |
| Type                | Compile-time DI                  | Dagger wrapper for Android    | Runtime DI                               |
| Boilerplate         | High                             | Reduced                       | Low                                      |
| Android Integration | Manual                           | Automatic                     | Manual                                   |
| Scopes              | Yes                              | Yes                           | Yes                                      |
| Learning Curve      | High                             | Medium                        | Low                                      |
| Advantages          | Performance, Compile-time safety | Simplifies Dagger for Android | Simple to setup, DSL-based               |
| Drawbacks           | Verbose, complex                 | Still uses annotations        | Runtime overhead, no compile-time safety |

---

### ✅ What is Hilt?

* **Hilt** is a **dependency injection library built on top of Dagger**
* Simplifies DI in Android by providing:

  * Predefined **scopes**
  * Automatic **component management**
  * Integration with **Activity, Fragment, ViewModel**

```kotlin
@HiltAndroidApp
class MyApplication : Application()

@AndroidEntryPoint
class MainActivity : AppCompatActivity() {

    @Inject lateinit var repository: UserRepository
}
```

---

### ✅ What is Dagger?

* **Dagger** is a **compile-time dependency injection framework**
* Requires **manual component creation and module setup**

```kotlin
@Module
@InstallIn(SingletonComponent::class)
object AppModule {
    @Provides
    fun provideApiService(): ApiService = ApiService()
}
```

---

### ✅ How Does Hilt Work Internally?

1. Generates **Dagger components** under the hood
2. Creates **object graphs** based on annotations
3. Injects dependencies **automatically** into Android classes
4. Handles **scopes** like Singleton, Activity, and ViewModelScoped

---

### ✅ Scoping in Hilt

| Scope              | Lifetime            | Example                        |
| ------------------ | ------------------- | ------------------------------ |
| `@Singleton`       | Application-wide    | ApiService, Repository         |
| `@ActivityScoped`  | Activity lifecycle  | Activity-specific dependencies |
| `@FragmentScoped`  | Fragment lifecycle  | Fragment dependencies          |
| `@ViewModelScoped` | ViewModel lifecycle | Repository tied to ViewModel   |

```kotlin
@Singleton
@Provides
fun provideApiService(): ApiService = ApiService()
```

---

### ✅ DI in Clean Architecture

* Repository, UseCases, ViewModel are **injected via DI**
* Data layer modules (Retrofit, Room) are **provided in DI modules**
* Ensures **decoupling and testability**

```kotlin
@InstallIn(SingletonComponent::class)
@Module
object RepositoryModule {
    @Provides
    fun provideUserRepository(api: ApiService, dao: UserDao): UserRepository =
        UserRepository(api, dao)
}
```

---

### ✅ Singleton vs ViewModelScoped vs ActivityScoped

| Scope           | Lifetime    | Use Case                                     |
| --------------- | ----------- | -------------------------------------------- |
| Singleton       | Application | Shared Repository, ApiService                |
| ActivityScoped  | Activity    | Dependencies tied to activity                |
| ViewModelScoped | ViewModel   | Repository or UseCase for a single ViewModel |

---

### ✅ How Do You Design DI in Large Apps?

* **Module separation**: NetworkModule, DatabaseModule, RepositoryModule
* **Feature-specific components** using Hilt or Dagger
* **Use scopes wisely** (Singleton, ViewModelScoped)
* **Inject interfaces, not implementations**
* Combine with **Clean Architecture**: Domain → Data → Presentation layers

---

### ✅ DI Annotations in Hilt / Dagger

| Annotation           | Purpose                                               |
| -------------------- | ----------------------------------------------------- |
| `@HiltAndroidApp`    | Initializes Hilt in Application class                 |
| `@AndroidEntryPoint` | Injects dependencies into Activity/Fragment/ViewModel |
| `@Module`            | Provides objects for DI                               |
| `@Provides`          | Provides dependency instances                         |
| `@Inject`            | Marks constructor/field for injection                 |
| `@Singleton`         | Application-wide single instance                      |
| `@ViewModelScoped`   | Tied to ViewModel lifecycle                           |
| `@ActivityScoped`    | Tied to Activity lifecycle                            |

---

### ✅ Summary

* **DI** = Provide dependencies externally for **loose coupling & testability**
* **Hilt** = Simplifies Dagger for Android
* **Dagger** = Compile-time DI framework
* **Koin** = Runtime DI DSL-based
* **Scopes** control dependency lifetimes
* Used in **MVVM** and **Clean Architecture** to **inject Repository, UseCase, ViewModel**

---

Perfect! Let’s cover **Android Testing** in **Markdown-ready format**, structured from **basic → intermediate → advanced**, including examples for **ViewModel, Repository, Room, Flow, and test frameworks**.

---

# 📌 Android Testing – Complete Guide

---

## 1️⃣ Basics of Android Testing

### ✅ Unit Testing vs Instrumentation Testing

| Feature | Unit Testing                          | Instrumentation Testing                |
| ------- | ------------------------------------- | -------------------------------------- |
| Scope   | Test individual classes/methods       | Test app components on device/emulator |
| Runs On | JVM (local)                           | Android runtime                        |
| Speed   | Fast                                  | Slower                                 |
| Example | ViewModel logic, Repository functions | UI testing, database interactions      |
| Tools   | JUnit, Mockk, Mockito                 | Espresso, UI Automator, Robolectric    |

---

## 2️⃣ Testing ViewModel

* ViewModel is **testable without Android framework**
* Use **JUnit + Coroutine Test** for testing

```kotlin
class UserViewModelTest {

    private lateinit var repository: FakeUserRepository
    private lateinit var viewModel: UserViewModel

    @Before
    fun setup() {
        repository = FakeUserRepository()
        viewModel = UserViewModel(repository)
    }

    @Test
    fun `refresh users updates live data`() = runTest {
        repository.setUsers(listOf(User("John")))
        viewModel.refresh()
        val users = viewModel.users.getOrAwaitValue()
        assertEquals("John", users.first().name)
    }
}
```

> `getOrAwaitValue()` is a helper to test LiveData synchronously.

---

## 3️⃣ Testing Repository

* Repository often combines **Room + Retrofit**
* Use **fake DAO and API** for unit testing

```kotlin
@Test
fun `getUsers emits cached and remote data`() = runTest {
    val fakeDao = FakeUserDao()
    val fakeApi = FakeApiService()
    val repo = UserRepository(fakeDao, fakeApi)

    val result = repo.getUsers().first()
    assertEquals(fakeDao.users, result)
}
```

---

## 4️⃣ Testing Room Database

* Use **in-memory database** for testing
* No real disk operations, faster execution

```kotlin
@get:Rule
val instantTaskExecutorRule = InstantTaskExecutorRule()

private lateinit var db: AppDatabase
private lateinit var dao: UserDao

@Before
fun setup() {
    db = Room.inMemoryDatabaseBuilder(
        ApplicationProvider.getApplicationContext(),
        AppDatabase::class.java
    ).allowMainThreadQueries().build()
    dao = db.userDao()
}

@After
fun teardown() = db.close()

@Test
fun insertAndReadUser() = runTest {
    val user = User("John", 1)
    dao.insertUser(user)
    val users = dao.getAllUsers()
    assertEquals(1, users.size)
}
```

---

## 5️⃣ Mockk vs Mockito

| Feature                  | Mockk             | Mockito                      |
| ------------------------ | ----------------- | ---------------------------- |
| Kotlin support           | ✅ Excellent       | ✅ Good, needs inline mocking |
| Syntax                   | Kotlin-native DSL | Java-like syntax             |
| Static/Constructor mocks | ✅ Yes             | ❌ Limited                    |
| Coroutines               | ✅ Easy            | ✅ Supported with extra setup |

```kotlin
// Mockk example
val mockApi = mockk<ApiService>()
coEvery { mockApi.getUsers() } returns listOf(User("John"))
```

---

## 6️⃣ Testing Flow and StateFlow

* Flow is **asynchronous**, so use `runTest` or `Turbine`

```kotlin
@Test
fun `flow emits values`() = runTest {
    val flow = flowOf(1, 2, 3)
    val result = flow.toList()
    assertEquals(listOf(1,2,3), result)
}

// StateFlow example
val stateFlow = MutableStateFlow(0)
stateFlow.value = 10
assertEquals(10, stateFlow.value)
```

---

## 7️⃣ How to Design Testable Architecture

1. **Use Dependency Injection** – Inject dependencies for easy mocking
2. **Separate layers** – Repository, UseCase, ViewModel, UI
3. **Expose Flows or LiveData** – For reactive testing
4. **Avoid Android framework in ViewModel** – Unit-testable
5. **Use in-memory DB for Room** – Avoid disk access
6. **Use Coroutine Test and Dispatchers** – Control execution in tests
7. **Write small, isolated tests** – Unit test first, then integration/UI tests

---

# ✅ Quick Summary Table

| Concept                 | Key Points                                           |
| ----------------------- | ---------------------------------------------------- |
| Unit vs Instrumentation | Local JVM vs device/emulator                         |
| ViewModel testing       | Test logic without Android framework                 |
| Repository testing      | Use fake DAO/API, test Flow/LiveData                 |
| Room testing            | In-memory DB, allowMainThreadQueries                 |
| Mockk vs Mockito        | Kotlin-friendly mocking vs Java-style                |
| Flow & StateFlow        | Use `runTest` and `Turbine` for async tests          |
| Testable architecture   | DI, layered design, reactive streams, isolated tests |

---

Perfect! Let’s cover **Android Performance & Optimization** in a **comprehensive Markdown format**, structured for interview-readiness, including examples, tools, and best practices.

---

# 📌 Android Performance & Optimization – Complete Guide

---

## 1️⃣ Optimizing Android App Performance

### ✅ How Do You Optimize Android App Performance?

1. **Efficient Layouts**

   * Use **ConstraintLayout** instead of nested LinearLayouts
   * Avoid overdraw, unnecessary layout nesting
   * Use **ViewStub** for infrequently used views

2. **Memory Optimization**

   * Reuse objects instead of creating new ones frequently
   * Use **RecyclerView** with ViewHolder pattern
   * Avoid memory leaks (watch for static references)

3. **Threading**

   * Run long tasks on **background threads** (Coroutines, WorkManager, RxJava)
   * Avoid blocking **main thread** to prevent ANR

4. **Lazy Loading**

   * Load images/data **on-demand**
   * Use **paging** for large lists

5. **Network Optimization**

   * Use **OkHttp caching, Retrofit, compression**
   * Reduce number of network calls

6. **App Size Reduction**

   * Use **Proguard/R8**, remove unused resources
   * Split APKs by ABI, language, screen density

---

## 2️⃣ Memory Leak Detection Techniques

* **LeakCanary** – Detect memory leaks in real-time
* **Android Profiler** – Monitor memory allocations
* **StrictMode** – Detect accidental disk/network access on main thread
* **WeakReference** – Avoid strong references to Context/View
* **Avoid static references** to Activities or Views

```kotlin
class MyActivity : AppCompatActivity() {
    companion object {
        var context: Context? = null // ❌ Bad: causes memory leak
    }
}
```

---

## 3️⃣ ANR vs Crash

| Feature    | ANR (Application Not Responding)   | Crash                                  |
| ---------- | ---------------------------------- | -------------------------------------- |
| Cause      | Main thread blocked > 5s           | Uncaught exception                     |
| Effect     | System shows **ANR dialog**        | App terminates immediately             |
| Example    | Heavy DB query on UI thread        | NullPointerException                   |
| Prevention | Use background threads, coroutines | Proper exception handling, null checks |

---

## 4️⃣ Profiling Tools in Android

| Tool                            | Use Case                                                 |
| ------------------------------- | -------------------------------------------------------- |
| Android Studio Profiler         | CPU, Memory, Network profiling                           |
| LeakCanary                      | Detect memory leaks                                      |
| Systrace                        | Trace system calls & UI rendering                        |
| StrictMode                      | Detect accidental disk/network operations on main thread |
| Firebase Performance Monitoring | Monitor real user performance                            |

---

## 5️⃣ Handling Large-Scale Apps with Millions of Users

* **Scalable architecture**: MVVM + Clean Architecture
* **Multi-module projects** to reduce build times
* Use **WorkManager/JobScheduler** for background tasks
* **Caching**: Room, DataStore, Retrofit cache
* **Optimized network requests**: batch calls, pagination, throttling
* **Crash & performance monitoring**: Firebase Crashlytics & Performance

---

## 6️⃣ Architecture for Real-Time Apps

* **Chat / Live streaming apps**:

  * Use **WebSockets / MQTT / Firebase Realtime Database**
  * Background **service or WorkManager** to handle updates
  * Offline-first caching with **Room + Flow**
  * Use **Paging 3** for messages
  * Optimize **UI rendering** for smooth scrolling

---

## 7️⃣ Handling API Failures Gracefully

* Use **try-catch** and **sealed classes** for API result
* Provide **fallback or cached data**
* Retry failed requests using **Exponential backoff**
* Show **user-friendly error messages**

```kotlin
sealed class Resource<out T> {
    data class Success<T>(val data: T): Resource<T>()
    data class Error(val message: String): Resource<Nothing>()
    object Loading: Resource<Nothing>()
}
```

---

## 8️⃣ Caching Strategies in Android

1. **Memory cache**: LruCache for images/data
2. **Disk cache**: Room, DataStore, or file storage
3. **Network cache**: OkHttp cache + headers
4. **Hybrid approach**: Offline-first architecture

```kotlin
val cache = LruCache<String, Bitmap>(maxMemory / 8)
```

---

## 9️⃣ Network Optimization

* **Batch network requests** to reduce overhead
* Enable **gzip compression** for API responses
* Use **paging for large datasets**
* Limit frequency of requests: **debounce and throttle**
* Use **OkHttp interceptor** to cache GET responses

---

## 🔟 Reducing App Size

* **Proguard / R8** – Remove unused code
* **Remove unused resources** – images, layouts, strings
* **Split APK / App Bundles** – per ABI / screen density / language
* **Vector drawables** instead of PNG
* **Dynamic Feature Modules** – download features on demand

---

# ✅ Quick Summary Table

| Concept          | Key Points                                                  |
| ---------------- | ----------------------------------------------------------- |
| Performance      | Efficient layouts, lazy loading, background threads         |
| Memory Leaks     | LeakCanary, Profiler, WeakReference, avoid static Context   |
| ANR vs Crash     | ANR = UI blocked, Crash = uncaught exception                |
| Profiling Tools  | Profiler, Systrace, LeakCanary, Firebase Performance        |
| Large-scale apps | Modular architecture, caching, optimized network            |
| Real-time apps   | WebSockets, Firebase, offline-first Room + Flow             |
| API Failures     | Try-catch, Resource wrapper, retry with backoff             |
| Caching          | Memory, disk, network, hybrid approach                      |
| Network          | Batch calls, gzip, paging, OkHttp caching                   |
| Reduce App Size  | R8, remove unused resources, vector assets, dynamic modules |

---











































