## **1. What are the main components of an Android app?**

An Android application is built using four main components:

### **Activity**

* Represents a single screen UI.
* Handles user interaction.
  **Example:** Login screen, Home screen.

### **Service**

* Runs in the background without UI.
* Used for long-running tasks.
  **Example:** Music playback, file upload.

### **Broadcast Receiver**

* Listens for system-wide events.
* Responds to broadcasts.
  **Example:** Battery low, network change.

### **Content Provider**

* Manages and shares app data.
* Provides a standard interface for data access.
  **Example:** Contacts, MediaStore.

### **Other important components**

* **Intent** – Used to communicate between components.
* **Application class** – Manages global application state.
* **AndroidManifest.xml** – App configuration file.

---

## **2. Describe the Activity lifecycle**

The Activity lifecycle defines how an activity is created, paused, resumed, and destroyed.

| **Lifecycle Method** | **Description**                                            |
| -------------------- | ---------------------------------------------------------- |
| **onCreate()**       | Called when activity is created; initialize UI and data.   |
| **onStart()**        | Activity becomes visible.                                  |
| **onResume()**       | Activity comes to foreground; user can interact.           |
| **onPause()**        | Activity partially visible; save small state changes.      |
| **onStop()**         | Activity not visible; release heavy resources.             |
| **onDestroy()**      | Activity is destroyed; cleanup resources.                  |
| **onRestart()**      | Called before onStart() when returning from stopped state. |

---

## **3. What is a Fragment and why is it used?**

A **Fragment** is a reusable UI component that lives inside an Activity.

**Why use Fragments?**

* Modular and reusable UI.
* Support multi-pane layouts (tablets).
* Easier UI management.
* Navigation without recreating activities.

**Key Points**

* Fragment has its own lifecycle.
* Must be attached to an Activity.
* Managed using **FragmentManager**.

---

## **4. Difference between Activity and Service**

| Feature          | Activity         | Service         |
| ---------------- | ---------------- | --------------- |
| UI               | Has UI           | No UI           |
| Purpose          | User interaction | Background work |
| Lifecycle        | Short-lived      | Can run long    |
| User interaction | Yes              | No              |
| Example          | Login screen     | Music player    |

---

## **5. What is the Android Manifest file?**

**AndroidManifest.xml** is a configuration file providing essential info about the app to the system.

**It defines:**

* App components (Activity, Service, Receiver)
* App permissions
* Package name
* App theme and icon
* Minimum & target SDK version

**Example:**

```xml
<uses-permission android:name="android.permission.INTERNET"/>

<activity android:name=".MainActivity">
    <intent-filter>
        <action android:name="android.intent.action.MAIN"/>
        <category android:name="android.intent.category.LAUNCHER"/>
    </intent-filter>
</activity>
```

---

## **6. What is Context? Types of Context**

**Context** provides access to application resources and system services.

**Uses:**

* Access resources
* Start activities
* Show Toast
* Get system services

**Types of Context:**

1. **Application Context**

   * `getApplicationContext()`
   * Exists throughout app lifecycle
   * Use for long-lived operations

2. **Activity Context**

   * Activity instance
   * Tied to activity lifecycle
   * Use for UI-related operations

---

## **7. What is ANR? Common Causes**

**ANR (Application Not Responding)** occurs when the main thread is blocked too long.

**Time limits:**

* UI thread blocked > 5 seconds
* BroadcastReceiver > 10 seconds

**Common causes:**

* Network operations on main thread
* Heavy computation on UI thread
* Deadlocks or infinite loops
* Slow database operations

**Prevention:**

* Use background threads
* Use Coroutines / AsyncTask / WorkManager

---

## **8. Difference between dp, sp, and px**

| Unit | Meaning                    | Use          |
| ---- | -------------------------- | ------------ |
| px   | Pixels                     | Rarely used  |
| dp   | Density-independent pixels | Layout sizes |
| sp   | Scale-independent pixels   | Text sizes   |

**Recommendation:**

* Use **dp** for layouts
* Use **sp** for text
* Avoid **px**

---

## **9. What is an Intent? Implicit vs Explicit**

**Intent** – A messaging object used to request an action from another component.

**Types:**

1. **Explicit Intent**

   * Specifies the target component.
   * Used within the same app.

   ```kotlin
   Intent(this, MainActivity::class.java)
   ```

2. **Implicit Intent**

   * Does not specify component.
   * System chooses the best app.

   ```kotlin
   Intent(Intent.ACTION_VIEW, Uri.parse("https://google.com"))
   ```

---

## **10. Difference between View and ViewGroup**

| Aspect                  | View                 | ViewGroup                      |
| ----------------------- | -------------------- | ------------------------------ |
| Definition              | Basic UI element     | Container for views            |
| Can contain child views | ❌ No                 | ✅ Yes                          |
| Purpose                 | Display/handle input | Arrange/layout child views     |
| Example                 | TextView, Button     | LinearLayout, ConstraintLayout |

**In short:**

* **View** → single UI element
* **ViewGroup** → layout that holds views

---

## **11. What is ConstraintLayout and why is it preferred?**

**ConstraintLayout**

* Flexible layout allowing views to be positioned relative to each other and parent using constraints.

**Why preferred:**

* Flat view hierarchy → better performance
* Reduces nested layouts
* Easy to create complex UI
* Supported by visual editor

**Example Advantages:**

* Replace multiple LinearLayouts
* Faster UI rendering

---

## **12. Difference between LinearLayout, RelativeLayout, and FrameLayout**

| Layout         | Description                       | Use Case             |
| -------------- | --------------------------------- | -------------------- |
| LinearLayout   | Arranges views in row/column      | Simple UI            |
| RelativeLayout | Position views relative to others | Medium complexity    |
| FrameLayout    | Stacks views                      | Overlays / fragments |

**Key Notes:**

* LinearLayout → orientation
* RelativeLayout → below, alignParent
* FrameLayout → single child or overlays

---

## **13. What is RecyclerView? Why is it better than ListView?**

**RecyclerView** – A flexible, efficient view for displaying large lists.

**Advantages over ListView:**

* ViewHolder pattern enforced
* Better scrolling performance
* Supports animations, grids, staggered layouts
* Highly customizable

| Feature      | RecyclerView | ListView      |
| ------------ | ------------ | ------------- |
| ViewHolder   | Mandatory    | Optional      |
| Performance  | High         | Lower         |
| Layout types | Multiple     | Only vertical |
| Animations   | Yes          | Limited       |

---

## **14. ViewBinding vs DataBinding**

| Feature         | ViewBinding         | DataBinding       |
| --------------- | ------------------- | ----------------- |
| Purpose         | Access views safely | Bind UI with data |
| XML logic       | ❌ No                | ✅ Yes             |
| Two-way binding | ❌ No                | ✅ Yes             |
| Complexity      | Simple              | Complex           |

**Recommendation:**

* **ViewBinding** → simple apps
* **DataBinding** → MVVM & complex UI

---

## **15. Difference between VISIBLE, INVISIBLE, and GONE**

| Visibility | Description | Takes Space |
| ---------- | ----------- | ----------- |
| VISIBLE    | Shown       | ✅ Yes       |
| INVISIBLE  | Hidden      | ✅ Yes       |
| GONE       | Removed     | ❌ No        |

---

## **16. What is a Custom View?**

**Custom View** – A view created by extending `View` or existing views to draw custom UI or behavior.

**Why use custom views:**

* Unique UI design
* Custom animations
* Better performance

**Example:**

```kotlin
class MyCustomView(context: Context) : View(context) {
    override fun onDraw(canvas: Canvas) {
        super.onDraw(canvas)
        // custom drawing here
    }
}
```

---

## **17. What is Overdraw & how to reduce it?**

**Overdraw** – Occurs when the same pixel is drawn multiple times in one frame.

**Problems:**

* Poor performance
* Increased GPU load

**How to reduce:**

* Remove unnecessary backgrounds
* Use ConstraintLayout
* Avoid nested layouts
* Use `clipToPadding=false` carefully
* Enable GPU Overdraw in Developer Options

---

## **18. How does Android handle different screen sizes?**

**Techniques:**

* dp and sp units
* Multiple layout folders:

  * `layout-sw600dp`
  * `layout-land`
* Drawable folders:

  * `drawable-hdpi`, `xhdpi`, `xxhdpi`
* Use ConstraintLayout for responsive UI

---

## **19. What is LayoutInflater?**

**LayoutInflater** – Converts XML layout files into View objects at runtime.

**Usage:**

* Inflate layouts
* Used in Activities, Fragments, Adapters

**Example:**

```kotlin
val view = LayoutInflater.from(context)
    .inflate(R.layout.item_layout, parent, false)
```

---
Perfect! I’ll continue the **full Android interview Q&A** in the same polished Markdown format. I’ll cover **all remaining questions**, grouped into **UI, Lifecycle, System, Networking, Security/Data**, with **tables, code blocks, and bullet points** for clarity.

Here’s the continuation:

---

# **Android Interview Questions & Answers (Complete Set)**

---

## **20. What happens when the Home button is pressed?**

**Lifecycle flow:**

* `onPause()` is called
* Then `onStop()` is called

**Important points:**

* Activity is **not destroyed**
* App goes to background
* Activity remains in **back stack**
* Returning to app resumes the same state

---

## **21. How does Android handle configuration changes?**

**Configuration changes include:**

* Screen rotation
* Language change
* Screen size change
* Dark mode
* Keyboard availability

**Default behavior:**

* Activity is destroyed and recreated

**Lifecycle sequence:**

```
onPause() → onStop() → onDestroy() → onCreate() → onStart() → onResume()
```

**How to handle:**

* Use `onSaveInstanceState()`
* Use `ViewModel`
* Use `android:configChanges` (not generally recommended)

---

## **22. What is the activity back stack?**

**Activity Back Stack:**

* Stack of activities managed by Android
* Follows **LIFO** (Last In First Out)

**Behavior:**

* New activity → pushed on stack
* Back button → top activity popped
* Previous activity resumes

---

## **23. Difference between onPause() and onStop()**

| Feature       | onPause()         | onStop()          |
| ------------- | ----------------- | ----------------- |
| Visibility    | Partially visible | Completely hidden |
| Time          | Short             | Longer            |
| Heavy work    | ❌ No              | ✅ Yes             |
| Save UI state | Light             | Heavy             |

**Example:**

* Incoming dialog → `onPause()`
* New full screen activity → `onStop()`

---

## **24. What is onSaveInstanceState()?**

**onSaveInstanceState()** – Used to save temporary UI state before activity destruction.

**When called:**

* Screen rotation
* System kills activity

**Example:**

```kotlin
override fun onSaveInstanceState(outState: Bundle) {
    outState.putString("name", "Aasim")
    super.onSaveInstanceState(outState)
}
```

**Restore:**

* `onCreate()` or `onRestoreInstanceState()`

---

## **25. What is multitasking in Android?**

**Multitasking:** Android allows multiple apps to run simultaneously.

**Types:**

* Foreground app
* Background app
* Services running in background
* Picture-in-Picture

**Management:**

* Android manages memory using process priority
* Low memory → background apps killed first

---

## **26. Difference between finish() and finishAffinity()**

| Method               | Description                        |
| -------------------- | ---------------------------------- |
| **finish()**         | Closes current activity            |
| **finishAffinity()** | Closes all activities in same task |

**Use case:**

* Logout functionality
* Exit app completely

---

## **27. What is task and back stack?**

**Task:** Collection of activities users interact with; represents a user flow.
**Back Stack:** Stack of activities within a task.

**Example:**

```
Login → Home → Profile
```

* All belong to one task
* Back stack handles navigation

---

## **28. What are launch modes?**

**Launch modes** define how activities are launched and placed in back stack.

| Mode           | Description          |
| -------------- | -------------------- |
| standard       | Default behavior     |
| singleTop      | Reuse if on top      |
| singleTask     | One instance in task |
| singleInstance | Own separate task    |

**Defined in:**

* AndroidManifest.xml
* Intent flags

---

## **29. What is PendingIntent?**

**PendingIntent:** A token that allows another app or system to execute an intent on your app’s behalf.

**Used in:**

* Notifications
* Alarms
* Widgets

**Example:**

```kotlin
val pendingIntent = PendingIntent.getActivity(
    context,
    0,
    intent,
    PendingIntent.FLAG_UPDATE_CURRENT
)
```

---

## **30. Difference between Service, IntentService, and Foreground Service**

| Feature  | Service          | IntentService     | Foreground Service    |
| -------- | ---------------- | ----------------- | --------------------- |
| Thread   | Main thread      | Background thread | Background            |
| UI       | ❌ No             | ❌ No              | Notification required |
| Lifetime | Manual           | Auto-stops        | Long-running          |
| Use case | Background tasks | Sequential tasks  | User-visible work     |

**Notes:**

* `IntentService` is deprecated
* Use **WorkManager / Coroutine + Service**
* Foreground Service requires persistent notification

---

## **31. What is Handler, Looper, and MessageQueue?**

**Handler:** Posts tasks to a thread’s message queue
**Looper:** Runs a loop to process messages
**MessageQueue:** Holds messages to be executed

**Relationship:**

```
Message → MessageQueue → Looper → Handler
```

**Common use:** Update UI from background thread

---

## **32. What is a memory leak?**

**Memory Leak:** Occurs when objects are no longer needed but still referenced, preventing garbage collection.

**Common causes:**

* Static references to Context
* Long-running background tasks
* Anonymous inner classes
* Unregistered listeners

---

## **33. How do you detect memory leaks?**

**Tools:**

* LeakCanary
* Android Studio Profiler
* Heap dumps
* MAT (Memory Analyzer Tool)

**Signs:**

* Increasing memory usage
* OutOfMemoryError
* Sluggish app behavior

---

## **34. What is garbage collection in Android?**

**Garbage Collection (GC):**

* Automatically reclaims memory of unused objects
* Managed by ART runtime
* Pauses app execution briefly
* Frequent GC → performance issues

---

## **35. What is StrictMode?**

**StrictMode:** Developer tool to detect bad practices during development.

**Detects:**

* Disk I/O on main thread
* Network calls on UI thread
* Leaked resources

**Example:**

```kotlin
StrictMode.setThreadPolicy(
    StrictMode.ThreadPolicy.Builder()
        .detectAll()
        .penaltyLog()
        .build()
)
```

---

## **36. What is ANR watchdog?**

**ANR Watchdog:** Monitors the main thread to detect freezes before system ANR occurs.

**Purpose:**

* Detect UI thread blocks early
* Log stack traces

**Example library:**

* ANR-WatchDog by Salomon Brys

---

## **37. How do you improve app startup time?**

**Techniques:**

* Reduce work in `onCreate()`
* Lazy initialization
* Use SplashScreen API
* Defer heavy tasks
* Optimize layouts
* Remove unused dependencies
* Use Baseline Profiles

---

## **38. What is WorkManager and when to use it?**

**WorkManager:** Jetpack library for deferrable, guaranteed background work.

**Use when:**

* Work must complete even if app exits
* Needs constraints (network, charging)
* Sync tasks, uploads

**Not for:** Immediate or UI-related tasks

---

## **39. Difference between AsyncTask and Executor**

| Feature        | AsyncTask  | Executor    |
| -------------- | ---------- | ----------- |
| Status         | Deprecated | Recommended |
| Control        | Limited    | Full        |
| Thread mgmt    | Auto       | Custom      |
| Performance    | Poor       | Better      |
| Modern support | ❌ No       | ✅ Yes       |

**Modern replacements:**

* Kotlin Coroutines
* WorkManager
* ExecutorService

---

## **40. Different data storage options in Android**

**Storage options:**

1. **SharedPreferences / DataStore**

   * Key–value pairs
   * Small data (settings, flags)
2. **Internal Storage**

   * App-private files
   * Removed when app uninstalled
3. **External Storage**

   * Public or app-specific
   * Needs permission (older Android)
4. **SQLite Database**

   * Structured relational data
5. **Room Database**

   * Abstraction over SQLite
6. **Network / Cloud Storage**

   * Firebase, REST APIs

---

## **41. Difference between SharedPreferences and database**

| Feature       | SharedPreferences | Database          |
| ------------- | ----------------- | ----------------- |
| Data type     | Key–Value         | Structured tables |
| Size          | Small             | Large             |
| Query support | ❌ No              | ✅ Yes             |
| Performance   | Fast              | Slower            |
| Use case      | Settings, flags   | User data, cache  |

---

## **42. What is SQLite and Room?**

**SQLite**

* Lightweight relational database
* Embedded in Android
* Uses SQL queries

**Room**

* Jetpack ORM on top of SQLite
* Compile-time query validation
* Less boilerplate

**Room components:**

* **Entity** – table
* **DAO** – queries
* **Database** – holder

---

## **43. How does Android handle network operations?**

**Key rules:**

* Network calls **not allowed on main thread**
* Must use background threads

**Common approaches:**

* Retrofit / OkHttp
* Volley
* Coroutines (Dispatchers.IO)
* WorkManager (for background sync)

**Threading:** Background thread → UI thread update

---

## **44. What is BroadcastReceiver?**

**BroadcastReceiver:** Listens for system or app-wide broadcast messages.

**Examples:**

* Battery low
* Network change
* SMS received

**Types:**

* Manifest-declared
* Dynamic (runtime)

---

## **45. Difference between local and global broadcasts**

| Feature     | Local Broadcast | Global Broadcast |
| ----------- | --------------- | ---------------- |
| Scope       | Within app      | System-wide      |
| Security    | High            | Lower            |
| Performance | Fast            | Slower           |
| Use case    | App events      | System events    |

> ⚠️ `LocalBroadcastManager` is deprecated → use LiveData / Flow instead.

---

## **46. What is deep linking?**

**Deep Linking:** Allows a URL to open a specific screen inside an app.

**Types:**

* **Deep Link** – basic
* **App Link** – verified domain
* **Deferred Deep Link** – after install

**Example:**

```
myapp://profile/123
```

---

## **47. How does Android handle runtime permissions?**

**Runtime permissions:** Introduced in Android 6.0 (API 23)

**Flow:**

1. Declare permission in Manifest
2. Check permission at runtime
3. Request permission
4. Handle user response

**Permission types:**

* Normal (auto granted)
* Dangerous (user approval required)

---

## **48. What is ProGuard / R8?**

**ProGuard / R8:** Tools to optimize and secure APK.

**Features:**

* Code shrinking
* Obfuscation
* Resource optimization
* Removes unused code

**R8:** Faster, more efficient replacement for ProGuard

---

## **49. How do you secure sensitive data in Android?**

**Best practices:**

* Use EncryptedSharedPreferences
* Use Android Keystore
* Avoid hardcoding secrets
* Use HTTPS with SSL pinning
* Encrypt local database
* Use biometric authentication

**Never store:**

* API keys in plain text
* Passwords without encryption


