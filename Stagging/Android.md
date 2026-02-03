{
  "category": "Android",
  "format": "Markdown inside JSON",
  "questions": [
    {
      "id": 1,
      "section": "Android Basics",
      "question": "What is Android?",
      "difficulty": "Easy",
      "tags": [
        "basics",
        "introduction"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "Android is an **open-source operating system** developed by **Google**, built on top of the **Linux kernel**. It is mainly designed for **mobile devices**, but is also used across a wide range of smart devices.\n\n#### Where Android Is Used\nAndroid powers multiple types of devices, including:\n- **Smartphones and tablets**\n- **Smart TVs** (Android TV)\n- **Smartwatches** (Wear OS)\n- **Cars** (Android Auto)\n- **IoT and embedded devices** such as kiosks, POS systems, and smart displays\n\n#### Programming Languages Supported\nAndroid supports application development using multiple programming languages:\n- **Kotlin** – Officially recommended by Google, modern, concise, and safe\n- **Java** – Original Android language with a large existing codebase\n- **C++** – Used via the Android NDK for performance-critical tasks like games and media processing"
    },
    {
      "id": 2,
      "section": "Android Basics",
      "question": "What is Context? How is it used?",
      "difficulty": "Easy",
      "tags": [
        "basics",
        "context"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "In Android, **Context** is an abstract class that provides access to **application-specific resources and system services**. It allowing components to interact with resources like layouts, strings, databases, preferences, and system-level services.\n\n#### Context is commonly used to\n\n- Access application **resources** (strings, colors, dimensions)\n- Inflate **layouts** and create views\n- Start **activities** and **services**\n- Access **system services** (LocationManager, NotificationManager, etc.)\n- Show **UI elements** like Toasts, Dialogs, and Snackbars\n- Access **SharedPreferences**, files, and databases\n\n\n#### Types of Context in Android\n\nAndroid provides **three main types of Context**, each used for different purposes.\n\n#### 1. Application Context\n- `getApplicationContext()`\n- Lives for the **entire app lifecycle**\n- Used for **singletons, background work, and non-UI resources**\n\n#### 2. Activity Context\n- Provided by an **Activity**\n- Tied to the **Activity lifecycle**\n- Used for **UI work** like dialogs and layout inflation\n\n#### 3. Service Context\n- Provided by a **Service**\n- Used for **background operations**\n- Not suitable for UI"
    },
    {
      "id": 5,
      "section": "Android Basics",
      "question": "Tell all Android application components.",
      "difficulty": "Easy",
      "tags": [
        "components",
        "basics"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "Android application components are the **core building blocks** of an app. Each component has a specific role and lifecycle managed by the Android system.\n\nThere are **four main Android application components**:\n\n#### 1. Activity\n- Represents a **single UI screen**\n- Handles user interaction\n- Manages screen lifecycle\n\n\n#### 2. Service\n- Performs **background tasks**\n- Runs without a user interface\n- Used for long-running operations\n\n\n#### 3. Broadcast Receiver\n- Listens for **system or app events**\n- Responds to events like battery change or network status\n- Has no UI\n\n\n#### 4. Content Provider\n- Manages and shares **app data**\n- Supports CRUD operations\n- Ensures secure data access between apps"
    },
    {
      "id": 6,
      "section": "Android Basics",
      "question": "What is AndroidManifest.xml?",
      "difficulty": "Easy",
      "tags": [
        "manifest",
        "basics"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "\n#### Why It Is Used\nIt tells Android:\n- The app’s **package name**\n- Which **components** the app has\n- What **permissions** are required\n- The app’s **launcher (entry point)**\n- App-level settings and SDK support\n\n\n#### What It Contains\n- **Application info** (name, icon, theme)\n- **App components** (Activities, Services, Receivers, Providers)\n- **Permissions**\n- **Launcher Activity**\n- **Min & target SDK versions**"
    },
    {
      "id": 7,
      "section": "Android Basics",
      "question": "What is Application class?",
      "difficulty": "Easy",
      "tags": [
        "application",
        "lifecycle"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "45 sec",
      "markdown": "The **Application class** in Android is a **base class** that represents the **entire application**. It is created **before any Activity, Service, or other app component** and remains alive as long as the application process exists.\n\n#### Why It Is Used\nThe Application class is used to:\n- Maintain **global application state**\n- Initialize **app-wide libraries** (Firebase, analytics, DI, etc.)\n- Store objects that need to live throughout the app lifecycle\n- Access a **global context**\n\n#### Key Characteristics\n- Only **one instance** exists per app\n- Created **once** when the app starts\n- Destroyed when the app process is killed\n- Has the **longest lifecycle** in the app\n\n\n#### How It Is Used\nCreate a custom Application class and register it in the manifest.\n\n```kotlin\nclass MyApp : Application() {\n    override fun onCreate() {\n        super.onCreate()\n        // App-level initialization\n    }\n}\n```"
    },
    {
      "id": 8,
      "section": "Android Tools",
      "question": "What is ADB in Android?",
      "difficulty": "Easy",
      "tags": [
        "tools",
        "debugging"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "45 sec",
      "markdown": "**ADB (Android Debug Bridge)** is a **command-line tool** that allows developers to **communicate with an Android device or emulator** from a computer. It is mainly used for **debugging, testing, and managing** Android applications.\n\n#### Why It Is Used\nADB helps developers to:\n- Install and uninstall apps\n- Run shell commands on a device\n- View logs and debug issues\n- Transfer files between device and system\n- Control devices during development\n\n#### Key Features\n- Works with **real devices and emulators**\n- Supports app debugging and testing\n- Allows direct access to the device shell\n\n#### Common ADB Commands\n- `adb devices` – List connected devices\n- `adb install app.apk` – Install an app\n- `adb logcat` – View device logs\n- `adb shell` – Access device shell"
    },
    {
      "id": 9,
      "section": "Android Tools",
      "question": "What is AAPT (Android Asset Packaging Tool)?",
      "difficulty": "Medium",
      "tags": [
        "tools",
        "build"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "45 sec",
      "markdown": "**AAPT (Android Asset Packaging Tool)** is a **build tool** used by Android to **compile, package, and manage app resources** such as layouts, images, and the AndroidManifest.xml file.\n\n#### Why It Is Used\nAAPT is used to:\n- Compile **resource files** (XML, images, strings)\n- Generate the **R.java / R class** for resource access\n- Package resources into the **APK or AAB**\n- Validate resource references and manifest entries\n\n\n#### Key Responsibilities\n- Converts resources into a **binary format**\n- Links resources with application code\n- Ensures resource IDs are correctly assigned"
    },
    {
      "id": 10,
      "section": "Android Basics",
      "question": "What is DEX file?",
      "difficulty": "Easy",
      "tags": [
        "basics",
        "build"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "30 sec",
      "markdown": "A **DEX (Dalvik Executable) file** is a compiled file format used by Android to store an app’s **bytecode**. It is generated from Java or Kotlin code and is executed by the **Android Runtime (ART)** on the device.\n\n#### Why It Is Used\nDEX files are used to:\n- Convert Java/Kotlin bytecode into a format optimized for Android\n- Reduce memory usage on mobile devices\n- Allow efficient execution on Android runtime\n\n#### Key Characteristics\n- Contains all compiled classes of an app\n- Optimized for low memory and performance\n- Generated during the build process from `.class` files"
    },
    {
      "id": 11,
      "section": "Android Basics",
      "question": "What is Multidex?",
      "difficulty": "Medium",
      "tags": [
        "basics",
        "build"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "30 sec",
      "markdown": "**Multidex** is an Android feature that allows an application to **use more than one DEX file**. It is required when an app exceeds the **65,536 method limit** imposed on a single DEX file.\n\n#### Why Multidex Is Needed\nApps with many libraries (Firebase, Retrofit, Google Play Services, etc.) can cross the **65K method limit**. Multidex splits code into **multiple DEX files** so the app can build and run correctly.\n\n\n#### Example Configuration\n\n##### Enable Multidex\n```gradle\nandroid {\n    defaultConfig {\n        multiDexEnabled true\n    }\n}\n\ndependencies {\n    implementation \"androidx.multidex:multidex:2.0.1\"\n}\n```"
    },
    {
      "id": 12,
      "section": "Android Basics",
      "question": "What are processes in Android?",
      "difficulty": "Medium",
      "tags": [
        "lifecycle",
        "process"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "45 sec",
      "markdown": "A **process** is a running instance of an app with its **own memory space**. Android runs each app in a **separate Linux process** to ensure security and stability.\n\n#### Why Processes Are Used\n- Keeps apps **isolated and secure**\n- Manages **memory and performance**\n- Prevents one app crash from affecting others\n\n#### Process Priority Types\n- **Foreground** – App in use (highest priority)\n- **Visible** – Partially visible app\n- **Service** – Background work (e.g., music)\n- **Background** – Not visible\n- **Empty** – No active components (lowest priority)"
    },
    {
      "id": 13,
      "section": "Android Basics",
      "question": "Is it possible to run an Android app in multiple processes? How?",
      "difficulty": "Medium",
      "tags": [
        "process",
        "advanced"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "45 sec",
      "markdown": "**Yes**, an Android application **can run in multiple processes**.\n\nBy default, all components of an app run in a **single process**, but Android allows you to assign **different components to different processes** using the `android:process` attribute.\n\n---\n\n#### How to Run an App in Multiple Processes\n\nYou can specify a custom process name in **AndroidManifest.xml** for a component.\n\n```xml\n<service\n    android:name=\".MyService\"\n    android:process=\":background\" />\n````\n\n#### How It Works\n\n* The `:background` prefix creates a **private process** for the app\n* That component runs in a **separate process**\n* The rest of the app continues to run in the main process\n\n---\n\n#### Use Cases\n\n* Heavy background work\n* Isolating crash-prone components\n* Improving performance for specific tasks"
    },
    {
      "id": 14,
      "section": "Android Basics",
      "question": "How is memory managed in Android OS?",
      "difficulty": "Medium",
      "tags": [
        "memory",
        "lifecycle"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "Android manages memory automatically to ensure smooth performance and efficient use of system resources.\n\n#### Key Points:\n\n- **Linux-based Memory Management**  \n  Android runs on the Linux kernel, which handles low-level memory operations like paging and allocation.\n\n- **Garbage Collection (GC)**  \n  Android apps run on ART (Android Runtime), which automatically frees unused objects using garbage collection, so developers don’t manually manage memory.\n\n- **Process Priority & Lifecycle**  \n  Android assigns priority to apps based on their state:\n    - Foreground app (highest priority)\n    - Visible app\n    - Background app\n    - Cached app (lowest priority)\n\n- **Low Memory Killer (LMK)**  \n  When memory is low, Android kills low-priority background processes to free memory.\n\n- **Shared Resources**  \n  System resources like libraries are shared across apps to reduce memory usage.\n\n- **Developer Responsibility**  \n  Developers should:\n    - Avoid memory leaks\n    - Release resources (bitmaps, listeners)\n    - Use lifecycle-aware components"
    },
    {
      "id": 15,
      "section": "Android Tools",
      "question": "What is StrictMode?",
      "difficulty": "Medium",
      "tags": [
        "tools",
        "debugging"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "30 sec",
      "markdown": "**StrictMode** is a **debugging tool** that helps detect **performance issues** like disk/network calls on the main thread and **memory leaks**.\n\n#### Purpose\n- Catch bad coding practices  \n- Prevent ANRs  \n- Improve app responsiveness  \n\n#### How It Works\n- **Thread Policy:** Monitors main-thread operations  \n- **VM Policy:** Detects memory leaks  \n\n#### Key Points\n- Used only in **development**\n- Not recommended for **production**"
    },
    {
      "id": 16,
      "section": "Android Tools",
      "question": "What is Lint?",
      "difficulty": "Medium",
      "tags": [
        "tools",
        "analysis"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "30 sec",
      "markdown": "**Lint** is a **static code analysis tool** in Android that helps developers **identify and fix potential bugs, performance issues, and code quality problems** in their apps before runtime.\n\n#### Why It Is Used\n- Detect **common coding mistakes**\n- Identify **performance and usability issues**\n- Enforce **best practices and standards**\n- Prevent **runtime crashes**\n\n#### How It Works\n- Scans **Java, Kotlin, XML, and Gradle files**\n- Provides **warnings or errors** for:\n    - Unused resources\n    - Hardcoded text (i18n issues)\n    - Missing permissions\n    - Deprecated APIs\n    - Layout performance issues\n\n#### Key Points\n- Runs **at compile-time**\n- Integrated in **Android Studio**\n- Helps maintain **clean and efficient code**"
    },
    {
      "id": 17,
      "section": "Android Libraries",
      "question": "What is Support Library? Why was it introduced?",
      "difficulty": "Medium",
      "tags": [
        "libraries",
        "compatibility"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "The **Android Support Library** is a set of **code libraries** provided by Google to help developers **use newer Android features on older versions** of the platform. It provides **backward-compatible versions of APIs**, UI components, and utilities.\n\n---\n\n#### Why It Was Introduced\n- **Fragmented Android versions:** Not all devices run the latest Android OS.\n- **Backward compatibility:** Allows developers to use modern features on older devices.\n- **Consistent UI and functionality:** Ensures apps behave similarly across different Android versions.\n- **Faster development:** Provides ready-to-use components like RecyclerView, CardView, ViewPager, etc.\n\n---\n\n#### Key Features\n- Backward-compatible UI widgets (RecyclerView, CardView, Toolbar)\n- Support for newer APIs on older devices\n- Utility classes for tasks like notifications, media, and animations"
    },
    {
      "id": 18,
      "section": "Battery Optimization",
      "question": "What is Doze Mode? What is App Standby?",
      "difficulty": "Medium",
      "tags": [
        "battery",
        "optimization"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "Both **Doze Mode** and **App Standby** help **save battery** by limiting background work.\n\n#### Doze Mode\n- Activates when device is **idle, screen off**\n- Delays background tasks, syncs, and network\n- Allows **high-priority notifications**\n\n#### App Standby\n- Applies to **unused apps**\n- Restricts background jobs and network\n- Active apps are not affected\n\n#### In Short\n- **Doze Mode:** Affects the whole device  \n- **App Standby:** Affects unused apps only"
    },
    {
      "id": 19,
      "section": "Android Basics",
      "question": "What is File, Class, and Activity in Android?",
      "difficulty": "Easy",
      "tags": [
        "basics",
        "file",
        "class",
        "activity"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "#### File\n- Used to **store data** on the device (internal, external, cache)\n- Examples: text files, images, databases\n\n#### Class\n- A **blueprint** written in Kotlin/Java\n- Defines variables and functions\n- All Android components are classes\n\n#### Activity\n- Represents **one screen with UI**\n- Handles user interaction\n- Managed by the Android lifecycle"
    },
    {
      "id": 20,
      "section": "Android Basics",
      "question": "How to change parameters in an app without app update?",
      "difficulty": "Medium",
      "tags": [
        "remote config",
        "dynamic update"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "You can update app behavior **without releasing a new version** using **remote configuration**.\n\n#### Common Ways\n- **Firebase Remote Config:** Fetch key-value updates at runtime (UI text, feature flags)\n- **Backend API:** Load configurable values from your server\n- **Dynamic Feature Modules:** Enable or disable app features remotely\n\n#### Benefits\n- No app update required\n- Easy feature toggles & A/B testing\n- Quick content or behavior changes\n"
    },
    {
      "id": 1,
      "section": "Activity Lifecycle",
      "question": "What is Activity and its lifecycle?",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "An **Activity** is a single screen in Android that handles user interaction and displays the UI.\n\n#### Activity Lifecycle\n\n- **onCreate()** – Initialize UI and resources when Activity is first created.  \n- **onStart()** – Activity becomes visible.  \n- **onResume()** – Activity gains focus; user can interact.  \n- **onPause()** – Activity loses focus; pause tasks or save data.  \n- **onStop()** – Activity no longer visible; release resources.  \n- **onDestroy()** – Activity is destroyed; cleanup resources.  \n- **onRestart()** – Activity restarts after being stopped.\n\n\n\n#### Key Points\n- Manages **visibility, focus, and resources**.  \n- Prevents **crashes and data loss**.  \n- Lifecycle methods guide proper handling of UI and background tasks."
    },
    {
      "id": 2,
      "section": "Activity Lifecycle",
      "question": "Difference between onCreate() and onStart()",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "- **When Called:**\n    - `onCreate()` is called **once** when the Activity is first created.\n    - `onStart()` is called **every time** the Activity becomes visible.\n---\n\n- **Purpose:**\n    - `onCreate()` is used to **initialize UI, resources, and data**.\n    - `onStart()` prepares the Activity to **interact with the user**.\n---\n\n- **Typical Tasks:**\n    - `onCreate()` → set content view, bind views, initialize variables.\n    - `onStart()` → start animations, refresh UI, resume paused tasks.\n---\n\n- **Lifecycle Position:**\n    - `onCreate()` is the **first method** called in the Activity lifecycle.\n    - `onStart()` follows `onCreate()` or `onRestart()`."
    },
    {
      "id": 3,
      "section": "Activity Lifecycle",
      "question": "When is only onDestroy() called without onPause() and onStop()?",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "\nNormally, `onPause()` and `onStop()` run before `onDestroy()`, but they can be skipped in rare cases:\n\n- **Activity finishes early** (e.g., `finish()` during `onCreate()`)\n- **System kills the process** due to low memory\n- **App crash or fatal exception**\n\n#### Key Point\n- `onDestroy()` is **not always guaranteed**\n- Do important cleanup in `onPause()` or `onStop()`, not `onDestroy()`"
    },
    {
      "id": 4,
      "section": "Activity Lifecycle",
      "question": "Activity lifecycle when launched for the first time",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "When an Android Activity is launched for the **first time**, it goes through the following lifecycle methods in order:\n\n1. **onCreate()**  \n   - Called when the Activity is **first created**.  \n   - Used to **initialize UI, variables, and resources**.  \n   - Example: `setContentView(R.layout.activity_main)`\n\n2. **onStart()**  \n   - Called when the Activity **becomes visible** to the user.  \n   - Prepares the Activity to **enter the foreground**.\n\n3. **onResume()**  \n   - Called when the Activity **gains focus** and the user can interact with it.  \n   - Activity is now in the **foreground** and fully active."
    },
    {
      "id": 5,
      "section": "Activity Lifecycle",
      "question": "Activity lifecycle when back button is pressed",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "onCreate → onStart → onResume\n#### Key Points\n- The Activity is **fully created and visible** after `onResume()`.  \n- `onPause()` and `onStop()` are called only when the user **leaves or navigates away** from the Activity.  \n\n\n#### Activity Lifecycle When Back Button Is Pressed\n\nWhen the user **presses the Back button**, the current Activity is **finished** and removed from the screen. The system calls the following lifecycle methods in order:\n\n1. **onPause()**  \n   - Called first when the Activity **loses focus**.  \n   - Used to pause ongoing tasks, animations, or save unsaved data.\n\n2. **onStop()**  \n   - Called when the Activity is **no longer visible**.  \n   - Release resources that are not needed while the Activity is hidden.\n\n3. **onDestroy()**  \n   - Called when the Activity is **completely destroyed**.  \n   - Final cleanup of resources occurs here."
    },
    {
      "id": 6,
      "section": "Activity Lifecycle",
      "question": "Activity lifecycle when launched again after back press",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "onPause → onStop → onDestroy\n\n#### Key Points\n- Pressing Back **finishes the Activity**, unlike Home button which only pauses/stops it.  \n- After `onDestroy()`, the Activity **cannot be resumed**.\n\n\n#### Activity Lifecycle When Launched Again After Back Press\n\nWhen an Activity is **launched again after being finished with the Back button**, it is treated as a **new instance**. The previous instance was destroyed, so the lifecycle starts fresh:\n\n1. **onCreate()**  \n   - Called to **create a new Activity instance**.  \n   - Initialize UI, variables, and resources.\n\n2. **onStart()**  \n   - Called when the Activity **becomes visible** to the user.\n\n3. **onResume()**  \n   - Called when the Activity **gains focus** and the user can interact with it.  \n   - The Activity is now in the **foreground**."
    },
    {
      "id": 7,
      "section": "Activity Lifecycle",
      "question": "Activity lifecycle when home button is pressed",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "When the user **presses the Home button**, the current Activity **moves to the background** but is **not destroyed**. The system calls the following lifecycle methods:\n\n1. **onPause()**  \n   - Called first as the Activity **loses focus**.  \n   - Use to **pause animations, save data, or stop CPU-intensive tasks**.\n\n2. **onStop()**  \n   - Called when the Activity is **no longer visible**.  \n   - Release resources that are not needed while in the background.\n\n> Note: The Activity **remains in memory** and can be resumed later without being recreated.\n\n#### Lifecycle Flow When Home Pressed\n\nonPause → onStop\n\n#### Key Points\n- Activity is **paused and stopped**, but not destroyed.  \n- Pressing **Back button** would have destroyed it, unlike Home button.  \n- When the user returns, `onRestart()` → `onStart()` → `onResume()` is called."
    },
    {
      "id": 8,
      "section": "Activity Lifecycle",
      "question": "Activity lifecycle when app returns from background",
      "difficulty": "Easy",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "When an Android app **returns from the background** (e.g., user presses the app icon or switches back from recent apps), the previously stopped Activity is **resumed** without being recreated. The following lifecycle methods are called:\n\n1. **onRestart()**  \n   - Called first when the Activity is **coming back from stopped state**.  \n   - Prepares the Activity to become visible again.\n\n2. **onStart()**  \n   - Called as the Activity **becomes visible** to the user.\n\n3. **onResume()**  \n   - Called when the Activity **gains focus** and the user can interact with it.  \n   - Activity is now in the **foreground**.\n\n---\n\n#### Lifecycle Flow\n\nonRestart → onStart → onResume\n\n#### Key Points\n- Activity **was not destroyed**, so `onCreate()` is **not called**.  \n- Efficient memory and resource usage, since UI and data are retained.  \n- Use `onRestart()` or `onStart()` to **refresh UI or data** if needed."
    },
    {
      "id": 9,
      "section": "Activity Lifecycle",
      "question": "Lifecycle when navigating from Activity A → Activity B",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "**Activity A**\n- `onPause()` → loses focus\n- `onStop()` → no longer visible\n\n**Activity B**\n- `onCreate()` → created\n- `onStart()` → visible\n- `onResume()` → interactive\n\n**Flow**\nA: `onPause → onStop`  \nB: `onCreate → onStart → onResume`\n\n**Note**\n- Activity A stays in memory\n- Pressing Back destroys B and resumes A"
    },
    {
      "id": 10,
      "section": "Activity Lifecycle",
      "question": "Lifecycle when pressing back from Activity B → Activity A",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "lifecycle"
      ],
      "markdown": "When the user presses the **Back button** on **Activity B**, it is **finished**, and the system returns to **Activity A**. The lifecycle methods of both Activities are called as follows:\n\n\n**Activity B**\n- `onPause()` → loses focus  \n- `onStop()` → not visible  \n- `onDestroy()` → finished  \n\n**Activity A**\n- `onRestart()` → coming back  \n- `onStart()` → visible  \n- `onResume()` → interactive  \n\n**Flow**\nB: `onPause → onStop → onDestroy`  \nA: `onRestart → onStart → onResume`"
    },
    {
      "id": 11,
      "section": "Activity State",
      "question": "How to preserve activity state during screen rotation?",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "state",
        "rotation"
      ],
      "markdown": "\nWhen an Activity is rotated, it is **destroyed and recreated**. To preserve state:\n\n\n#### Common Ways\n- **onSaveInstanceState():** Save small UI data (text, selections)\n- **ViewModel:** Keeps UI data across rotations\n\n#### Key Points\n- `onSaveInstanceState()` → temporary UI state  \n- `ViewModel` → long-lived UI data  \n- Avoid manual config handling unless necessary"
    },
    {
      "id": 12,
      "section": "Activity State",
      "question": "What is savedInstanceState Bundle?",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "state"
      ],
      "markdown": "`savedInstanceState` is a **Bundle** used to **save and restore UI state** when an Activity is recreated (e.g., screen rotation).\n\n#### How It’s Used\n- Save data in `onSaveInstanceState()`\n- Restore it in `onCreate()` or `onRestoreInstanceState()`\n\n#### Key Points\n- `null` on first launch\n- Stores **small UI data only**\n- Helps restore state after rotation or system kill"
    },
    {
      "id": 13,
      "section": "Activity State",
      "question": "Difference between Intent and Bundle",
      "difficulty": "Medium",
      "tags": [
        "intent",
        "bundle",
        "data-passing"
      ],
      "markdown": "**Intent**\n- Used to **start Activities/Services** or send broadcasts\n- Can carry data and navigation info\n\n**Bundle**\n- A **key-value data container**\n- Used to pass data via Intent or save state\n\n**In Short**\n- **Intent** = navigation + data\n- **Bundle** = data only"
    },
    {
      "id": 14,
      "section": "Activity Launch Modes",
      "question": "What are launchModes?",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "launchMode",
        "backstack"
      ],
      "markdown": "**Launch modes** define **how a new Activity is launched** and how it behaves in the **Activity back stack**. They control whether a new instance is created or an existing instance is reused.\n#### Types of Launch Modes\n\n1. **standard** (Default)  \n   - Every time the Activity is started, a **new instance** is created and pushed to the stack.  \n   - Example: Multiple instances of the same Activity can exist.\n\n2. **singleTop**  \n   - If the Activity is **already at the top** of the stack, no new instance is created.  \n   - `onNewIntent()` is called instead.  \n   - Example: Clicking a notification that opens the current top Activity.\n\n3. **singleTask**  \n   - Only **one instance** exists in the entire system.  \n   - If an instance exists anywhere in the stack, it is **brought to the front**, and `onNewIntent()` is called.  \n   - Example: Main dashboard Activity.\n\n4. **singleInstance**  \n   - Similar to `singleTask` but the Activity **lives in its own separate task**.  \n   - No other Activity can be part of the same task.  \n   - Example: Launching a special Activity for multi-window scenarios.\n\n---\n\n#### How to Declare Launch Mode\nIn `AndroidManifest.xml`:\n```xml\n<activity android:name=\".MainActivity\"\n          android:launchMode=\"singleTop\" />\n````\n\n---\n\n#### Key Points\n\n* Launch modes **control Activity instance creation** and **stack behavior**.\n* Helps prevent **duplicate Activities** and manage navigation efficiently."
    },
    {
      "id": 15,
      "section": "Activity Launch Modes",
      "question": "Explain standard launchMode",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "launchMode"
      ],
      "markdown": "**standard** is the **default launch mode** for all Activities in Android.  \n\n---\n\n#### How It Works\n- Every time the Activity is started, a **new instance** is **created and pushed onto the back stack**.  \n- Multiple instances of the same Activity can exist simultaneously in the back stack.  \n- Does **not reuse any existing instance**.\n\n---\n\n#### Example\n```kotlin\n// Start MainActivity multiple times\nval intent = Intent(this, MainActivity::class.java)\nstartActivity(intent)\nstartActivity(intent)\n````\n\n* Result: Two separate instances of `MainActivity` are now in the back stack.\n\n---\n\n#### Key Points\n\n* Allows **multiple instances** of the same Activity.\n* Each instance is independent.\n* Useful when each Activity should maintain its **own state**."
    },
    {
      "id": 16,
      "section": "Activity Launch Modes",
      "question": "Explain singleTop launchMode",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "launchMode"
      ],
      "markdown": "**singleTop** is a launch mode that **reuses the Activity** if it is **already at the top of the back stack**, instead of creating a new instance.\n\n---\n\n#### How It Works\n- If the Activity is **not at the top**, a new instance is created (like standard mode).  \n- If the Activity **is at the top**, no new instance is created; **`onNewIntent()`** is called with the new Intent.  \n- Prevents multiple copies of the same Activity when repeatedly launching it from the top.\n\n---\n\n#### Example\n```kotlin\n// Activity A is at the top of the stack\nval intent = Intent(this, ActivityA::class.java)\nstartActivity(intent) // onNewIntent() is called instead of creating a new instance\n````\n\n---\n\n#### Key Points\n\n* Avoids **duplicate instances** at the top of the stack.\n* Saves **memory and resources**.\n* Useful for **notification clicks** or launching an Activity multiple times from the same screen.\n"
    },
    {
      "id": 17,
      "section": "Activity Launch Modes",
      "question": "Explain singleTask launchMode",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "launchMode"
      ],
      "markdown": "**singleTask** is a launch mode that ensures **only one instance of an Activity exists** in the system, and it is **reused if it already exists** anywhere in the back stack.\n\n---\n\n#### How It Works\n- If the Activity **already exists** in the back stack:\n  - The system brings that instance to the **foreground**.\n  - **All Activities above it** in the stack are **destroyed**.\n  - `onNewIntent()` is called with the new Intent.\n- If the Activity **does not exist**, a new instance is created.\n\n---\n\n#### Example\n```kotlin\n// MainActivity is launched with singleTask\nval intent = Intent(this, MainActivity::class.java)\nstartActivity(intent)\n````\n\n* If MainActivity exists anywhere in the stack, it is **reused**, and other Activities above it are removed.\n\n---\n\n#### Key Points\n\n* Ensures **only one instance** of the Activity exists system-wide.\n* Useful for **main dashboard or launcher Activities**.\n* Helps manage navigation and prevent duplicate screens."
    },
    {
      "id": 18,
      "section": "Activity Launch Modes",
      "question": "Explain singleInstance launchMode",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "launchMode"
      ],
      "markdown": "**singleInstance** is a special launch mode that ensures **only one instance of an Activity exists**, and it **resides in its own separate task**. No other Activity can be launched in the same task.\n\n---\n\n#### How It Works\n- The Activity runs in a **separate task**, isolated from other Activities.  \n- If the Activity already exists:\n  - It is **reused**, and `onNewIntent()` is called.  \n  - No other Activities can be part of its task.  \n- Useful for **Activities that must always be standalone**, like a special media player or system-level screen.\n\n---\n\n#### Example\n```xml\n<activity\n    android:name=\".SpecialActivity\"\n    android:launchMode=\"singleInstance\" />\n````\n\n* Launching SpecialActivity multiple times **reuses the same instance** in its separate task.\n\n---\n\n#### Key Points\n\n* Guarantees **one instance in a separate task**.\n* Prevents **other Activities** from being launched in the same task.\n* Ideal for **system-level or always-on-top Activities**."
    },
    {
      "id": 19,
      "section": "Tasks & Back Stack",
      "question": "What are tasks and back stack?",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "task",
        "backstack"
      ],
      "markdown": "In Android, **tasks** and the **back stack** are concepts that define how Activities are organized and navigated.\n\n---\n\n#### 1. Task\n- A **task** is a collection of Activities that users interact with **to accomplish a specific goal**.  \n- Activities in a task are **organized in a stack-like structure**.  \n- Each app usually has its **own task**, but tasks can span multiple apps with certain launch modes.  \n- Example: Opening an email app, reading an email, then composing a new one—all belong to the same task.\n\n---\n\n#### 2. Back Stack\n- The **back stack** is a **Last-In-First-Out (LIFO) stack** that manages the order of Activities within a task.  \n- The **top of the stack** is the **current Activity** in the foreground.  \n- Pressing the **Back button** pops the top Activity off the stack and resumes the previous one.\n\n---\n\n#### Example\n1. User opens **Activity A** → pushed onto stack  \n2. Navigates to **Activity B** → pushed onto stack  \n3. Presses Back → **Activity B** popped, **Activity A** resumes  \n\n```\nStack after opening B: [A, B]  (B on top)\nPress Back: [A]  (B removed)\n```\n\n\n#### Key Points\n- **Task** = logical group of related Activities.  \n- **Back stack** = manages Activity order in a task.  \n- **Back button** navigates through the back stack, not tasks."
    },
    {
      "id": 20,
      "section": "Tasks & Back Stack",
      "question": "What is taskAffinity?",
      "difficulty": "Medium",
      "tags": [
        "activity",
        "taskAffinity",
        "backstack"
      ],
      "markdown": "**`taskAffinity`** is an attribute of an Activity that defines **which task the Activity prefers to belong to**. It allows Activities from the same or different apps to be associated with a particular task.\n\n---\n\n#### How It Works\n- By default, all Activities of an app share the **same taskAffinity** (usually the app package name).  \n- You can set a **custom taskAffinity** in `AndroidManifest.xml` to control task behavior.  \n- When launching an Activity, the system tries to place it in a task with the **same taskAffinity**.\n\n---\n\n#### Example\n```xml\n<activity\n    android:name=\".SpecialActivity\"\n    android:taskAffinity=\"com.example.specialtask\" />\n````\n\n* `SpecialActivity` will prefer to run in a task named `com.example.specialtask`.\n* Useful for creating **separate tasks for specific Activities** (e.g., for multi-window apps or notifications).\n\n---\n\n#### Key Points\n\n* Controls **task association** for Activities.\n* Helps **manage multiple tasks** within the same app.\n* Does **not force** the system to create a new task; it’s a **preference**."
    },
    {
      "id": 21,
      "section": "Android Basics",
      "question": "What is installLocation tag?",
      "difficulty": "Easy",
      "tags": [
        "manifest",
        "installation"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "The **`installLocation`** tag in `AndroidManifest.xml` specifies **where the app should be installed** on the device. It helps control whether the app installs on **internal storage** or **external storage (SD card)**.\n\n---\n\n#### Possible Values\n\n1. **internalOnly** (Default)  \n   - App can only be installed on **internal storage**.  \n   - Ensures the app is always available and not removable by the user.\n\n2. **preferExternal**  \n   - App **prefers external storage** (SD card), but can fall back to internal storage if needed.  \n   - Useful for large apps to save internal memory.\n\n3. **auto**  \n   - The system decides the **best location** based on available space and device configuration.\n\n---\n\n#### Example\n```xml\n<manifest xmlns:android=\"http://schemas.android.com/apk/res/android\"\n    package=\"com.example.app\">\n    \n    <application\n        android:installLocation=\"preferExternal\"\n        android:label=\"@string/app_name\">\n    </application>\n</manifest>\n````\n\n---\n\n#### Key Points\n\n* Helps manage **storage usage** for large apps.\n* Some features may **not work on SD card** (e.g., widgets, services).\n* Default is **internalOnly** if not specified."
    },
    {
      "id": 22,
      "section": "Activity & Fragment",
      "question": "Relationship between Activity and Fragment lifecycle",
      "difficulty": "Medium",
      "tags": [
        "lifecycle",
        "fragment",
        "activity"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "- Fragments exist **inside an Activity**, so their lifecycle is **closely tied** to the host Activity.  \n- Fragment lifecycle events occur **alongside the Activity**, but Fragments have **extra callbacks** like `onAttach()`, `onCreateView()`, and `onDetach()` for managing UI.\n\n**Lifecycle Mapping (Simplified):**\n- Activity `onCreate()` → Fragment `onAttach()` → `onCreateView()`  \n- Activity `onStart()` → Fragment `onStart()`  \n- Activity `onResume()` → Fragment `onResume()`  \n- Activity `onPause()` → Fragment `onPause()`  \n- Activity `onStop()` → Fragment `onStop()`  \n- Activity `onDestroy()` → Fragment `onDestroyView()` → `onDestroy()` → `onDetach()`\n\n**Key Points:**  \n- Fragment depends on Activity but can manage its own UI.  \n- Proper lifecycle handling prevents **memory leaks** and ensures **smooth UI updates**.\n"
    },
    {
      "id": 23,
      "section": "Activity & Fragment",
      "question": "How do we save and restore an activity's state during screen rotation?",
      "difficulty": "Medium",
      "tags": [
        "state",
        "rotation",
        "bundle"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "When an Activity rotates, it is **destroyed and recreated**. To preserve state:\n\n---\n\n#### 1. `onSaveInstanceState()`\n```kotlin\noverride fun onSaveInstanceState(outState: Bundle) {\n    super.onSaveInstanceState(outState)\n    outState.putString(\"username\", editText.text.toString())\n}\n\noverride fun onCreate(savedInstanceState: Bundle?) {\n    super.onCreate(savedInstanceState)\n    editText.setText(savedInstanceState?.getString(\"username\"))\n}\n````\n\n---\n\n#### 2. ViewModel\n\n* Survives rotation without recreation.\n\n```kotlin\nval viewModel = ViewModelProvider(this).get(MyViewModel::class.java)\neditText.setText(viewModel.username)\nviewModel.username = editText.text.toString()\n```"
    },
    {
      "id": 24,
      "section": "Activity & Fragment",
      "question": "What is a Bundle?",
      "difficulty": "Easy",
      "tags": [
        "bundle",
        "data passing"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "In Android, a **Bundle** is a **key-value data container** used to pass information between components like Activities, Fragments, or Services.\n\n---\n\n#### Key Points\n- Stores data as **primitive types, Strings, Parcelable, or Serializable objects**.  \n- Often used with:\n  - **Intents** to pass data between Activities.\n  - **Fragments** via `setArguments()` or `getArguments()`.\n  - **onSaveInstanceState()`** to save Activity state.\n\n---\n\n#### Example with Intent\n```kotlin\nval bundle = Bundle()\nbundle.putString(\"username\", \"Aasim\")\n\nval intent = Intent(this, SecondActivity::class.java)\nintent.putExtras(bundle)\nstartActivity(intent)\n````\n\n#### Example in Fragment\n\n```kotlin\nval fragment = MyFragment()\nval bundle = Bundle()\nbundle.putInt(\"userId\", 101)\nfragment.arguments = bundle\n```"
    },
    {
      "id": 25,
      "section": "Activity & Fragment",
      "question": "When Activity A starts Activity B, explain the lifecycle order",
      "difficulty": "Medium",
      "tags": [
        "lifecycle",
        "activity"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "When **Activity A** starts **Activity B**, both Activities go through specific lifecycle callbacks as the system manages focus and visibility.\n\n---\n\n#### Activity A (Current Activity)\n1. **onPause()** – Activity A **loses focus** because Activity B is coming to the foreground.  \n2. **onStop()** – Called if Activity B **fully covers Activity A**. Activity A is now **in the background**.\n\n---\n\n#### Activity B (New Activity)\n1. **onCreate()** – Activity B is **created** and UI is initialized.  \n2. **onStart()** – Activity B becomes **visible**.  \n3. **onResume()** – Activity B **gains focus** and user can interact with it.\n\n\n\n#### Lifecycle Flow (Simplified)\n\n```\nActivity A: onPause → onStop\nActivity B: onCreate → onStart → onResume\n```\n\n#### Key Points\n- Activity A is **paused or stopped** but not destroyed.  \n- Activity B starts fresh and becomes the **foreground Activity**.  \n- Pressing **Back** from Activity B will **resume Activity A** using `onRestart() → onStart() → onResume()`.\n"
    },
    {
      "id": 26,
      "section": "Activity & Fragment",
      "question": "How do you declare the launch mode in your application?",
      "difficulty": "Medium",
      "tags": [
        "launchMode",
        "manifest",
        "intent"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "1. Open `AndroidManifest.xml`.  \n2. Inside the `<activity>` tag, add `android:launchMode` with one of the following values:  \n   - `standard` (default)  \n   - `singleTop`  \n   - `singleTask`  \n   - `singleInstance`\n\n---\n\n#### Example\n```xml\n<activity\n    android:name=\".MainActivity\"\n    android:launchMode=\"singleTop\" />\n````\n\n* This ensures that if `MainActivity` is already at the **top of the stack**, no new instance is created; `onNewIntent()` is called instead.\n\n---\n\n#### Key Points\n\n* Launch mode controls **Activity instance creation** and **back stack behavior**.\n* Declaring it in the manifest applies **system-wide** for that Activity.\n* Useful for preventing **duplicate screens** and managing **navigation flow**.\n"
    },
    {
      "id": 27,
      "section": "Activity & Fragment",
      "question": "How to know configChange happens in onDestroy?",
      "difficulty": "Medium",
      "tags": [
        "lifecycle",
        "configuration change"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "In Android, an Activity may be **destroyed either due to user action or a configuration change** (like screen rotation). To differentiate in `onDestroy()`, use `isChangingConfigurations()`.\n\n---\n\n#### How It Works\n- `isChangingConfigurations()` returns **true** if the Activity is being destroyed due to a **configuration change**.  \n- Returns **false** if destroyed for other reasons (e.g., user finishing the Activity or system reclaiming memory).\n\n---\n\n#### Example\n```kotlin\noverride fun onDestroy() {\n    super.onDestroy()\n    if (isChangingConfigurations) {\n        Log.d(\"ActivityLifecycle\", \"Destroyed due to configuration change\")\n    } else {\n        Log.d(\"ActivityLifecycle\", \"Destroyed permanently\")\n    }\n}\n````\n\n---\n\n#### Key Points\n\n* Helps decide whether to **save resources** or **release them permanently**.\n* Often used with **ViewModel** to retain data across configuration changes.\n* Works reliably with screen rotation, locale changes, or theme changes.\n"
    },
    {
      "id": 28,
      "section": "Fragment Basics",
      "question": "What is Fragment?",
      "difficulty": "Easy",
      "tags": [
        "fragment",
        "ui",
        "modular"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "A **Fragment** is a **modular portion of an Activity** that has its own **lifecycle, UI, and behavior**. Fragments allow developers to create **reusable and flexible UI components** that can be combined in different ways within an Activity.\n\n---\n\n#### Key Features\n- Represents a **part of a screen**, not a full screen.  \n- Can be **added, removed, or replaced dynamically** using `FragmentManager`.  \n- Has its **own lifecycle**, which is closely tied to the host Activity.  \n- Supports **UI layouts**, user interactions, and logic independent of the Activity.\n\n---\n\n#### Example\n```kotlin\nclass MyFragment : Fragment() {\n    override fun onCreateView(\n        inflater: LayoutInflater,\n        container: ViewGroup?,\n        savedInstanceState: Bundle?\n    ): View? {\n        return inflater.inflate(R.layout.fragment_my, container, false)\n    }\n}\n````\n\n* Add to Activity:\n\n```kotlin\nsupportFragmentManager.beginTransaction()\n    .replace(R.id.container, MyFragment())\n    .commit()\n```\n\n---\n\n#### Key Points\n\n* Fragments are **reusable UI components**.\n* Allow **flexible layouts** for phones, tablets, and multi-pane screens.\n* Lifecycle depends on the **host Activity** but has **independent callbacks**.\n\n---"
    },
    {
      "id": 29,
      "section": "Fragment Lifecycle",
      "question": "Fragment Lifecycle Methods",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "lifecycle"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "A **Fragment** has its **own lifecycle** that is closely tied to the host Activity. Understanding these methods helps manage UI and resources efficiently.\n\n---\n\n#### Key Lifecycle Methods\n\n1. **onAttach(Context)**  \n   - Called when the Fragment is **attached to its host Activity**.  \n   - Use for **context-related initializations**.\n\n2. **onCreate(Bundle?)**  \n   - Called to **initialize Fragment** (non-UI tasks).  \n   - Use for **data setup**.\n\n3. **onCreateView(LayoutInflater, ViewGroup?, Bundle?)**  \n   - Inflate the Fragment **UI layout**.  \n\n4. **onViewCreated(View, Bundle?)**  \n   - Called after the **view hierarchy is created**.  \n   - Use for **binding views and setting listeners**.\n\n5. **onStart()**  \n   - Fragment becomes **visible**.  \n\n6. **onResume()**  \n   - Fragment **gains focus** and is interactive.\n\n7. **onPause()**  \n   - Fragment **loses focus** but is still visible.  \n   - Use to **pause UI updates or animations**.\n\n8. **onStop()**  \n   - Fragment is **no longer visible**.  \n   - Release resources not needed when hidden.\n\n9. **onDestroyView()**  \n   - Fragment’s **view hierarchy is destroyed**.  \n   - Clean up **binding references**.\n\n10. **onDestroy()**  \n    - Called to **cleanup Fragment instance**.  \n\n11. **onDetach()**  \n    - Fragment is **detached from Activity**.  \n    - Final cleanup of references to Activity."
    },
    {
      "id": 30,
      "section": "Fragment Basics",
      "question": "Why is it recommended to use only the default constructor in Fragment?",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "constructor",
        "best practice"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "In Android, it is **recommended to use only the default (no-argument) constructor** for Fragments. This ensures the system can **recreate the Fragment properly** during configuration changes or process recreation.\n\n---\n\n#### Reasons\n\n1. **System Recreation**\n   - Android may **destroy and recreate Fragments** (e.g., on rotation or low memory).  \n   - The system uses the **default constructor** to re-instantiate the Fragment.  \n   - Custom constructors with arguments **will not be called**, causing crashes or lost data.\n\n2. **Safe Data Passing**\n   - Data should be passed using a **Bundle via `setArguments()`** instead of constructor parameters.  \n   - `setArguments()` is preserved across **configuration changes**.\n\n---\n\n#### Recommended Approach\n```kotlin\nclass MyFragment : Fragment() {\n    companion object {\n        fun newInstance(userId: Int): MyFragment {\n            val fragment = MyFragment()\n            val args = Bundle()\n            args.putInt(\"userId\", userId)\n            fragment.arguments = args\n            return fragment\n        }\n    }\n}\n````\n\n* Access data in Fragment:\n\n```kotlin\nval userId = arguments?.getInt(\"userId\")\n```\n\n---\n\n#### Key Points\n\n* Always use the **default constructor**.\n* Use `setArguments()` / `Bundle` to pass data.\n* Ensures **reliable Fragment recreation** by the system."
    },
    {
      "id": 31,
      "section": "Fragment Lifecycle",
      "question": "Fragment lifecycle when launched",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "lifecycle"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "When a **Fragment is added to an Activity**, it goes through a series of **lifecycle callbacks** as it becomes visible and interactive.\n\n---\n\n#### Lifecycle Sequence\n\n1. **onAttach(Context)**  \n   - Fragment is **attached to its host Activity**.  \n   - Can access the Activity context.\n\n2. **onCreate(Bundle?)**  \n   - Fragment **initializes non-UI components** and data.  \n\n3. **onCreateView(LayoutInflater, ViewGroup?, Bundle?)**  \n   - Fragment **inflates its UI layout**.  \n\n4. **onViewCreated(View, Bundle?)**  \n   - UI is created; **views can be initialized and listeners set**.\n\n5. **onStart()**  \n   - Fragment becomes **visible** to the user.\n\n6. **onResume()**  \n   - Fragment is now **active and interactive**.\n\n---\n\n#### Simplified Flow Diagram\n\nonAttach → onCreate → onCreateView → onViewCreated → onStart → onResume\n\n#### Key Points\n- Lifecycle is **closely tied to the host Activity**.  \n- Proper handling ensures **UI is ready** and resources are efficiently managed.  \n- After `onResume()`, the Fragment can **interact with the user**."
    },
    {
      "id": 32,
      "section": "Fragment Lifecycle",
      "question": "Fragment lifecycle when back button is pressed",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "lifecycle",
        "backstack"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "When the **Back button** is pressed and a Fragment is removed or replaced, it goes through the **destruction phase** of its lifecycle.\n\n---\n\n#### Lifecycle Sequence\n\n1. **onPause()**  \n   - Fragment **loses focus** and stops interacting with the user.  \n\n2. **onStop()**  \n   - Fragment is **no longer visible**.  \n\n3. **onDestroyView()**  \n   - Fragment’s **view hierarchy is destroyed**.  \n   - Release UI-related resources here.\n\n4. **onDestroy()**  \n   - Fragment instance is **destroyed**, cleaning up non-UI resources.\n\n5. **onDetach()**  \n   - Fragment is **detached from its host Activity**.  \n   - Final cleanup and references to Activity are cleared.\n\n---\n\n#### Simplified Flow Diagram\n\nonPause → onStop → onDestroyView → onDestroy → onDetach\n\n#### Key Points\n- Back press triggers **removal of the Fragment’s UI and instance**.  \n- Proper handling prevents **memory leaks**.  \n- Any data that needs to persist should be saved in **ViewModel or savedInstanceState**.\n"
    }
  ]
}
