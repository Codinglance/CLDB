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
      "markdown": "Android is an **open-source operating system** developed by **Google**, built on top of the **Linux kernel**. It is mainly designed for **mobile devices**, but is also used across a wide range of smart devices.  ### Where Android Is Used Android powers multiple types of devices, including: - **Smartphones and tablets** - **Smart TVs** (Android TV) - **Smartwatches** (Wear OS) - **Cars** (Android Auto) - **IoT and embedded devices** such as kiosks, POS systems, and smart displays  ### Programming Languages Supported Android supports application development using multiple programming languages: - **Kotlin** – Officially recommended by Google, modern, concise, and safe - **Java** – Original Android language with a large existing codebase - **C++** – Used via the Android NDK for performance-critical tasks like games and media processing"
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
      "markdown": "In Android, **Context** is an abstract class that provides access to **application-specific resources and system services**. It acts as a **bridge between your app and the Android system**, allowing components to interact with resources like layouts, strings, databases, preferences, and system-level services.\n\nSimply put, **Context tells Android \"where your app is\" and \"what it is allowed to do.\"**\n\n---\n\n### How is Context Used?\nContext is commonly used to:\n- Access application **resources** (strings, colors, dimensions)\n- Inflate **layouts** and create views\n- Start **activities** and **services**\n- Access **system services** (LocationManager, NotificationManager, etc.)\n- Show **UI elements** like Toasts, Dialogs, and Snackbars\n- Access **SharedPreferences**, files, and databases\n\n**Example usage:**\n```kotlin\nToast.makeText(context, \"HelloAndroid\", Toast.LENGTH_SHORT).show()\n\nval intent = Intent(context, SecondActivity::class.java)\ncontext.startActivity(intent)\n```\n\n---\n\n### Types of Context in Android\nAndroid mainly provides **three types of Context**, each with a specific use case.\n\n---\n\n### 1. Application Context\nObtained using `getApplicationContext()` and tied to the **entire lifecycle of the application**.\n\n**Use when:**\n- You need a context that outlives an Activity\n- Working with singletons, managers, or background operations\n- Accessing resources without UI dependency\n\n**Example:**\n```kotlin\nval appContext = applicationContext\n```\n\n⚠️ **Avoid** using it for UI elements like dialogs.\n\n---\n\n### 2. Activity Context\nProvided by an **Activity**, tied to the **Activity lifecycle**, and destroyed when the Activity is destroyed.\n\n**Use when:**\n- Creating UI components\n- Showing dialogs, bottom sheets, or popups\n- Inflating layouts related to the screen\n\n**Example:**\n```kotlin\nval activityContext = this\n```\n\n---\n\n### 3. Service Context\nProvided by a **Service**. Used for background operations and not suitable for UI-related tasks.\n\n**Use when:**\n- Running background tasks\n- Accessing system services inside a Service\n\n**Example:**\n```kotlin\nclass MyService : Service() {\n    override fun onCreate() {\n        val serviceContext = this\n    }\n}\n```"
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
      "markdown": "Android application components are the **core building blocks** of an Android app. Each component serves a specific purpose and has its own lifecycle, which is managed by the Android operating system.  There are **four main Android application components**.  ---  ### 1. Activity  An **Activity** represents a **single screen with a user interface**. It is the most visible component of an Android application and is responsible for interacting with the user.  **Key responsibilities:** - Display UI elements such as buttons, text, and images - Handle user input and interactions - Manage screen lifecycle events like create, pause, resume, and destroy   Every Activity follows a defined lifecycle, allowing Android to manage resources efficiently as the user navigates through the app.  ---  ### 2. Service  A **Service** is used to perform **long-running operations in the background** without providing a user interface. Services allow tasks to continue even when the user switches apps.  **Key responsibilities:** - Run background tasks such as music playback or data syncing - Perform operations independently of UI components   Services are essential for tasks that should not be interrupted by user navigation.  ---  ### 3. Broadcast Receiver  A **Broadcast Receiver** responds to **system-wide or application-level broadcast messages**. These messages inform apps about important system events.  **Key responsibilities:** - Listen for events sent by the system or other apps - Execute short tasks when an event occurs   Broadcast Receivers do not have a user interface and are typically used to trigger actions based on external events.  ---  ### 4. Content Provider  A **Content Provider** manages and shares **application data** with other apps in a secure way. It acts as an interface between an app’s data and external applications.  **Key responsibilities:** - Control access to app data - Perform CRUD operations (Create, Read, Update, Delete) - Ensure data security and consistency   Content Providers are especially useful when multiple apps need to access the same data."
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
      "markdown": "**AndroidManifest.xml** is a **required configuration file** in every Android application. It tells the **Android system** essential information about the app before it can be installed or run. Without this file, an Android app cannot function.\n\n---\n\n### Purpose of AndroidManifest.xml\nThe Android system uses this file to:\n- Identify the **application package**\n- Know which **components** the app contains\n- Understand required **permissions**\n- Decide the app’s **entry point**\n- Apply app-level settings\n\n---\n\n### What It Contains\n\n#### 1. Application Information\nDefines basic app settings such as:\n- App name and icon\n- Theme and configuration\n\n```xml\n<application\n    android:label=\"@string/app_name\"\n    android:icon=\"@mipmap/ic_launcher\" />\n```\n\n---\n\n#### 2. Application Components\nAll core components must be declared here:\n- Activities\n- Services\n- Broadcast Receivers\n- Content Providers\n\n```xml\n<activity android:name=\".MainActivity\" />\n```\n\n---\n\n#### 3. App Entry Point\nThe launcher Activity is defined using an intent filter.\n\n```xml\n<intent-filter>\n    <action android:name=\"android.intent.action.MAIN\" />\n    <category android:name=\"android.intent.category.LAUNCHER\" />\n</intent-filter>\n```\n\n---\n\n#### 4. Permissions\nPermissions required by the app are declared here.\n\n```xml\n<uses-permission android:name=\"android.permission.INTERNET\" />\n```\n\n---\n\n#### 5. SDK Version Support\nDefines the minimum and target Android versions.\n\n```xml\n<uses-sdk\n    android:minSdkVersion=\"21\"\n    android:targetSdkVersion=\"34\" />\n```"
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
      "markdown": "### Application Class\n\nThe `Application` class represents the **global state of the app**.\nIt is created before any Activity or Service.\n\n**Use Cases:**\n- Initialize libraries (Firebase, DI, Analytics)\n- Store global data\n\n**Example:**\n```kotlin\nclass MyApp : Application() {\n    override fun onCreate() {\n        super.onCreate()\n    }\n}\n```"
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
      "markdown": "### ADB (Android Debug Bridge)\n\nADB is a command-line tool used to communicate with Android devices.\n\n**Uses:**\n- Install/uninstall apps\n- Debug apps\n- Execute shell commands\n\n**Example:**\n```bash\nadb install app.apk\n```"
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
      "markdown": "### AAPT\n\nAAPT is a build tool that compiles and packages Android app resources.\n\n**Responsibilities:**\n- Compile XML resources\n- Generate R.java / R.class\n- Package APK or AAB"
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
      "markdown": "### DEX File\n\nDEX (Dalvik Executable) file contains compiled bytecode of Android apps.\nJava/Kotlin code is converted into DEX format for execution by Android Runtime (ART)."
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
      "markdown": "### Multidex\n\nMultidex allows an app to contain multiple DEX files when method count exceeds 65,536.\n\n**Why needed?**\n- Large apps exceed the single DEX limit.\n\n**Example:**\n```gradle\nmultiDexEnabled true\n```"
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
      "markdown": "### Android Processes\n\nA process is an instance of a running application.\nAndroid assigns priority to processes based on their importance.\n\n**Process Priority Order:**\n1. Foreground process\n2. Visible process\n3. Service process\n4. Background process\n5. Empty process"
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
      "markdown": "### Multiple Processes\n\nYes ✅\n\n**How?**\nSpecify `android:process` in `AndroidManifest.xml`.\n\n```xml\n<activity\n    android:name=\".MainActivity\"\n    android:process=\":remote\" />\n```\n\n**Use Cases:**\n- Isolate heavy tasks\n- Improve stability\n- IPC (Inter-Process Communication)"
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
      "markdown": "### Memory Management\n\nAndroid uses automatic memory management through **Garbage Collection (GC)**.\n\n**Features:**\n- Heap memory allocation\n- Garbage Collector\n- Low Memory Killer (LMK)\n- Process termination when memory is low\n\n**Best Practices:**\n- Avoid memory leaks\n- Use ViewBinding instead of findViewById\n- Release resources in lifecycle methods"
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
      "markdown": "### StrictMode\n\nStrictMode is a developer tool used to detect bad practices in Android apps.\n\n**Detects:**\n- Disk I/O on main thread\n- Network calls on main thread\n- Memory leaks\n\n**Example:**\n```kotlin\nStrictMode.setThreadPolicy(\n    StrictMode.ThreadPolicy.Builder().detectAll().penaltyLog().build()\n)\n```"
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
      "markdown": "### Lint\n\nLint is a static code analysis tool that checks Android code for bugs, performance issues, and best practices.\n\n**Detects:**\n- Unused resources\n- Performance issues\n- Security vulnerabilities"
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
      "markdown": "### Support Library / AndroidX\n\nProvides backward-compatible features for older Android versions.\n\n**Why introduced?**\n- New APIs not available in old Android versions\n- Consistent behavior across devices\n\n**Example:**\n```gradle\nimplementation \"androidx.appcompat:appcompat:1.6.1\"\n```"
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
      "markdown": "### Doze Mode\n\nIntroduced in Android 6.0 to save battery when the device is idle.\n\n**Effects:**\n- Restricts background CPU and network usage\n- Delays jobs and alarms\n\n### App Standby\n\nRestricts background activities of unused apps.\n\n**Effects:**\n- Limits background execution\n- Saves battery"
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
      "markdown": "### File, Class, Activity\n\n**File:**\n- Physical resource in the project (XML, Kotlin, images)\n- Example: `MainActivity.kt`, `activity_main.xml`\n\n**Class:**\n- Blueprint for objects in Java/Kotlin\n```kotlin\nclass User(val name: String)\n```\n\n**Activity:**\n- UI component representing a screen\n```kotlin\nclass MainActivity : AppCompatActivity()\n```"
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
      "markdown": "### Dynamic Configuration\n\nChange app parameters without updating the app using **Remote Configuration techniques**.\n\n**Common Methods:**\n1. Firebase Remote Config\n2. Server API configuration\n3. Feature flags\n4. Remote JSON config\n\n**Example (Firebase Remote Config):**\n- Change UI text, features, or behavior remotely\n\n**Benefits:**\n- Dynamic updates\n- A/B testing\n- Feature toggling"
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
      "markdown": "An **Activity** is a core Android component representing a single screen with a user interface.\n\n### Lifecycle Methods\n```kotlin\nonCreate()\nonStart()\nonResume()\nonPause()\nonStop()\nonDestroy()\nonRestart()\n```\n\n### Lifecycle Flow\n```\nonCreate → onStart → onResume\n                ↓\n            onPause → onStop → onDestroy\n```"
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
      "markdown": "| onCreate() | onStart() |\n| ---------- | --------- |\n| Called once when Activity is created | Called every time Activity becomes visible |\n| Used for initialization | Used to prepare UI |\n| Set content view | Register listeners |"
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
      "markdown": "⚠️ Normally `onDestroy()` is **not called alone**.\nIt may happen if:\n* System kills the process\n* finish() is called before Activity is fully resumed\n* App crashes\n\n✅ Note: Android does not guarantee `onDestroy()` execution."
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
      "markdown": "```\nonCreate → onStart → onResume\n```"
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
      "markdown": "```\nonPause → onStop → onDestroy\n```"
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
      "markdown": "A new instance is created:\n```\nonCreate → onStart → onResume\n```"
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
      "markdown": "```\nonPause → onStop\n```\n(Activity is kept in back stack, not destroyed)"
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
      "markdown": "```\nonRestart → onStart → onResume\n```"
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
      "markdown": "```\nActivity A: onPause()\nActivity B: onCreate → onStart → onResume\nActivity A: onStop()\n```"
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
      "markdown": "```\nActivity B: onPause → onStop → onDestroy\nActivity A: onRestart → onStart → onResume\n```"
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
      "markdown": "Use:\n* `onSaveInstanceState()`\n* ViewModel\n* SavedStateHandle\n\n### Example\n```kotlin\noverride fun onSaveInstanceState(outState: Bundle) {\n    outState.putString(\"name\", \"Aasim\")\n    super.onSaveInstanceState(outState)\n}\n```"
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
      "markdown": "`savedInstanceState` is a Bundle that stores UI state before Activity destruction.\n\n### Example\n```kotlin\noverride fun onCreate(savedInstanceState: Bundle?) {\n    super.onCreate(savedInstanceState)\n    val name = savedInstanceState?.getString(\"name\")\n}\n```"
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
      "markdown": "| Intent | Bundle |\n| ------ | ------ |\n| Used to start components | Used to pass data |\n| Can carry Bundle | Cannot start components |\n| Messaging object | Key-value container |"
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
      "markdown": "Launch modes define how Activities are created and managed in the back stack.\n\n### Types\n* standard (default)\n* singleTop\n* singleTask\n* singleInstance"
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
      "markdown": "* Default mode\n* Always creates a new instance\n\n### Back stack example\n```\nA → B → C → B (new instance)\n```"
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
      "markdown": "* Reuses Activity if already on top of stack\n\n### Example\n```\nA → B → C → B (reuse if B is on top)\n```"
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
      "markdown": "* Only one instance exists in a task\n* Clears above Activities\n\n### Example\n```\nA → B → C → D → B\nResult: A → B\n```"
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
      "markdown": "* Activity runs in a separate task\n* No other Activity in the same task"
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
      "markdown": "### Task\nA task is a collection of Activities that users interact with.\n\n### Back Stack\nA stack of Activities in LIFO order."
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
      "markdown": "taskAffinity defines which task an Activity prefers to belong to.\n\n### Example\n```xml\n<activity\n    android:name=\".MainActivity\"\n    android:taskAffinity=\"com.example.newtask\" />\n```"
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
      "markdown": "Specifies where the app can be installed.\n\n### Values\n- auto\n- internalOnly\n- preferExternal\n\n```xml\n<manifest android:installLocation=\"auto\">\n```"
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
      "markdown": "Fragments have their own lifecycle but depend on Activity.\n\n### Example mapping\n\n| Activity    | Fragment                      |\n| ----------- | ----------------------------- |\n| onCreate()  | onAttach() → onCreate()       |\n| onStart()   | onStart()                     |\n| onResume()  | onResume()                    |\n| onPause()   | onPause()                     |\n| onStop()    | onStop()                      |\n| onDestroy() | onDestroyView() → onDestroy() |"
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
      "markdown": "### Steps\n1. Save state in `onSaveInstanceState()`\n2. Restore state in `onCreate()` or `onRestoreInstanceState()`"
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
      "markdown": "A Bundle is a key-value pair data structure used to pass data between Android components.\n\n### Example\n```kotlin\nval bundle = Bundle()\nbundle.putInt(\"age\", 25)\n```"
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
      "markdown": "```\nActivity A: onPause()\nActivity B: onCreate → onStart → onResume\nActivity A: onStop()\n```"
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
      "markdown": "### In AndroidManifest.xml\n```xml\n<activity\n    android:name=\".MainActivity\"\n    android:launchMode=\"singleTask\" />\n```\n\n### In Intent\n```kotlin\nintent.addFlags(Intent.FLAG_ACTIVITY_SINGLE_TOP)\n```"
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
      "markdown": "Use `isChangingConfigurations`.\n\n### Example\n```kotlin\noverride fun onDestroy() {\n    super.onDestroy()\n    if (isChangingConfigurations) {\n        Log.d(\"ConfigChange\", \"Activity destroyed due to configuration change\")\n    }\n}\n```"
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
      "markdown": "A **Fragment** is a reusable portion of UI that represents a part of an Activity’s interface and behavior.\n\n### Key Points\n- Fragment cannot exist without an Activity.\n- It has its own lifecycle.\n- Used for modular and reusable UI.\n- Supports multi-pane layouts (tablet, foldables).\n\n### Example\n```kotlin\nclass HomeFragment : Fragment(R.layout.fragment_home)\n```"
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
      "markdown": "Fragments have a lifecycle similar to Activities but with additional callbacks.\n\n```kotlin\nonAttach()        // Fragment attached to Activity\nonCreate()        // Fragment created\nonCreateView()    // UI created\nonViewCreated()   // View ready\nonStart()         // Fragment visible\nonResume()        // Fragment active\nonPause()         // Fragment partially visible\nonStop()          // Fragment hidden\nonDestroyView()   // View destroyed\nonDestroy()       // Fragment destroyed\nonDetach()        // Fragment detached from Activity\n```"
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
      "markdown": "Fragments must have a **public empty constructor** because Android may recreate them during configuration changes or process death.\n\n### ❌ Wrong Approach\n```kotlin\nclass MyFragment(val name: String) : Fragment()\n```\n\n### ✅ Correct Approach\nUse `newInstance()` with Bundle.\n```kotlin\nclass MyFragment : Fragment() {\n    companion object {\n        fun newInstance(name: String): MyFragment {\n            val fragment = MyFragment()\n            val bundle = Bundle()\n            bundle.putString(\"name\", name)\n            fragment.arguments = bundle\n            return fragment\n        }\n    }\n}\n```"
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
      "markdown": "```\nonAttach → onCreate → onCreateView → onViewCreated → onStart → onResume\n```"
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
      "markdown": "If Fragment is in back stack:\n```\nonPause → onStop → onDestroyView\n```\n\nIf Fragment is removed completely:\n```\nonPause → onStop → onDestroyView → onDestroy → onDetach\n```"
    }
  ]
}
