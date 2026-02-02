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
    },
    {
      "id": 33,
      "section": "Fragment Lifecycle",
      "question": "Fragment lifecycle when home button is pressed",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "lifecycle",
        "home"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "```\nonPause → onStop\n```\n(Fragment remains in memory)"
    },
    {
      "id": 34,
      "section": "Fragment Lifecycle",
      "question": "Fragment lifecycle when returning from background",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "lifecycle",
        "resume"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "```\nonStart → onResume\n```"
    },
    {
      "id": 35,
      "section": "Fragment vs Activity",
      "question": "Difference between Fragment and Activity",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "activity",
        "comparison"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "| Fragment            | Activity                |\n| ------------------- | ----------------------- |\n| Part of an Activity | Independent component   |\n| Cannot exist alone  | Can exist independently |\n| Lightweight         | Heavy component         |\n| Reusable UI         | Full screen UI          |\n| Child of Activity   | Parent container        |"
    },
    {
      "id": 36,
      "section": "Fragment Usage",
      "question": "When should you use Fragment instead of Activity?",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "activity",
        "architecture"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "Use Fragment when:\n- Building modular UI\n- Supporting multiple screen sizes\n- Implementing single-activity architecture\n- Reusing UI components\n- Using ViewPager / Navigation Component"
    },
    {
      "id": 37,
      "section": "Fragment Transaction",
      "question": "Difference between add and replace Fragment in back stack",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "backstack",
        "transaction"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "### add()\n- Adds Fragment on top of existing Fragment\n- Previous Fragment remains in memory and visible (if not hidden)\n\n### replace()\n- Removes current Fragment and adds new Fragment\n- Previous Fragment is destroyed (view)\n\n| add()                      | replace()                   |\n| -------------------------- | --------------------------- |\n| Multiple fragments coexist | Only one fragment at a time |\n| Faster UI switching        | Cleaner UI                  |\n| More memory usage          | Less memory usage           |"
    },
    {
      "id": 38,
      "section": "Fragment Advanced",
      "question": "What is Retained Fragment / Headless Fragment?",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "retain",
        "headless"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "A **Retained Fragment** is a Fragment that survives configuration changes.\n\n### Characteristics\n- No UI (Headless Fragment)\n- Used to retain data across configuration changes\n\n### Example\n```kotlin\nsetRetainInstance(true)\n```\n⚠️ Deprecated in modern Android → replaced by ViewModel."
    },
    {
      "id": 39,
      "section": "Fragment Transaction",
      "question": "Purpose of addToBackStack() in FragmentTransaction",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "backstack",
        "transaction"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "`addToBackStack()` adds a Fragment transaction to the back stack, allowing users to navigate back.\n\n### Example\n```kotlin\nsupportFragmentManager.beginTransaction()\n    .replace(R.id.container, SecondFragment())\n    .addToBackStack(null)\n    .commit()\n```\n\n### Without addToBackStack()\n- Back button closes Activity."
    },
    {
      "id": 40,
      "section": "Fragment Communication",
      "question": "How to communicate between two Fragments?",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "communication",
        "viewmodel"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "2 min",
      "markdown": "### ✅ Best Approaches\n\n#### 1. Shared ViewModel (Recommended)\n- Both fragments share same ViewModel.\n\n#### 2. Interface Callback\n- Fragment communicates via Activity.\n\n#### 3. Fragment Result API\n- Modern solution.\n\n### Example (Fragment Result API)\n```kotlin\nparentFragmentManager.setFragmentResult(\"key\", bundleOf(\"data\" to \"Hello\"))\n```"
    },
    {
      "id": 41,
      "section": "Fragment Communication",
      "question": "How to share ViewModel between fragments?",
      "difficulty": "Medium",
      "tags": [
        "fragment",
        "viewmodel",
        "shared"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "Use `activityViewModels()`.\n\n### Example\n```kotlin\nclass SharedViewModel : ViewModel() {\n    val data = MutableLiveData<String>()\n}\n```\n\n```kotlin\nval viewModel: SharedViewModel by activityViewModels()\n```"
    },
    {
      "id": 42,
      "section": "Dialog vs DialogFragment",
      "question": "Difference between Dialog and DialogFragment",
      "difficulty": "Medium",
      "tags": [
        "dialog",
        "fragment"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "| Dialog               | DialogFragment                 |\n| -------------------- | ------------------------------ |\n| UI popup component   | Fragment wrapper around Dialog |\n| Not lifecycle-aware  | Lifecycle-aware                |\n| Manual management    | Managed by FragmentManager     |\n| Risk of memory leaks | Safer                          |\n\n### Example DialogFragment\n```kotlin\nclass MyDialogFragment : DialogFragment()\n```"
    },
    {
      "id": 43,
      "section": "Intent & Broadcast",
      "question": "What is Intent?",
      "difficulty": "Easy",
      "tags": [
        "intent",
        "activity"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "✅ **Definition:**\nIntent is a messaging object used to request an action from another component (Activity, Service, BroadcastReceiver).\n\n✅ **Used Class / Tag:**\n`android.content.Intent`\n\n✅ **Example:**\n```kotlin\nval intent = Intent(this, SecondActivity::class.java)\nstartActivity(intent)\n```"
    },
    {
      "id": 44,
      "section": "Intent & Broadcast",
      "question": "What is Explicit Intent?",
      "difficulty": "Easy",
      "tags": [
        "intent",
        "explicit"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "✅ **Definition:**\nIntent where you specify the exact target component (class name).\n\n✅ **Used Class:**\n`Intent(Context, TargetClass::class.java)`\n\n✅ **Example:**\n```kotlin\nval intent = Intent(this, ProfileActivity::class.java)\nstartActivity(intent)\n```"
    },
    {
      "id": 45,
      "section": "Intent & Broadcast",
      "question": "What is Implicit Intent?",
      "difficulty": "Medium",
      "tags": [
        "intent",
        "implicit"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "✅ **Definition:**\nIntent where the target component is not specified, but the action is defined.\n\n✅ **Used Tags / Actions:**\n`Intent.ACTION_VIEW`, `Intent.ACTION_SEND`\n\n✅ **Example:**\n```kotlin\nval intent = Intent(Intent.ACTION_VIEW)\nintent.data = Uri.parse(\"https://google.com\")\nstartActivity(intent)\n```"
    },
    {
      "id": 46,
      "section": "Intent & Broadcast",
      "question": "What is Sticky Intent?",
      "difficulty": "Medium",
      "tags": [
        "intent",
        "broadcast",
        "deprecated"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "✅ **Definition:**\nSticky Intent remains in the system after being broadcast, so future receivers can access it.\n\n⚠️ Deprecated in modern Android.\n\n✅ **Used Method:**\n`sendStickyBroadcast()`\n\n✅ **Example (Not recommended):**\n```kotlin\nval intent = Intent(\"MY_ACTION\")\nsendStickyBroadcast(intent)\n```"
    },
    {
      "id": 47,
      "section": "Intent & Broadcast",
      "question": "What is PendingIntent?",
      "difficulty": "Medium",
      "tags": [
        "intent",
        "pendingintent",
        "notification"
      ],
      "askedIn": [
        "Google",
        "Amazon"
      ],
      "expectedReadTime": "1 min",
      "markdown": "✅ **Definition:**\nA token that allows another app or system to execute your Intent later on your behalf.\n\n✅ **Used Class:**\n`android.app.PendingIntent`\n\n✅ **Example:**\n```kotlin\nval intent = Intent(this, MainActivity::class.java)\nval pendingIntent = PendingIntent.getActivity(\n    this, 0, intent, PendingIntent.FLAG_UPDATE_CURRENT\n)\n```\n📌 Used in: Notifications, Alarms, Widgets."
    },
    {
      "id": 1,
      "section": "Intent & Broadcast",
      "question": "What is IntentFilter?",
      "difficulty": "Medium",
      "tags": [
        "intent",
        "filter",
        "manifest"
      ],
      "markdown": "Declares which Intents a component can respond to.\n\n### Used Tag (Manifest)\n`<intent-filter>`\n\n### Example\n```xml\n<activity android:name=\".MainActivity\">\n    <intent-filter>\n        <action android:name=\"android.intent.action.MAIN\"/>\n        <category android:name=\"android.intent.category.LAUNCHER\"/>\n    </intent-filter>\n</activity>\n```"
    },
    {
      "id": 2,
      "section": "Intent & Broadcast",
      "question": "What is BroadcastReceiver?",
      "difficulty": "Medium",
      "tags": [
        "broadcast",
        "receiver",
        "component"
      ],
      "markdown": "A component that listens for system-wide or app-specific broadcast messages.\n\n### Used Class\n`BroadcastReceiver`\n\n### Example\n```kotlin\nclass MyReceiver : BroadcastReceiver() {\n    override fun onReceive(context: Context, intent: Intent) {\n        Log.d(\"Receiver\", \"Broadcast received\")\n    }\n}\n```\nRegister in Manifest:\n```xml\n<receiver android:name=\".MyReceiver\"/>\n```"
    },
    {
      "id": 3,
      "section": "Intent & Broadcast",
      "question": "What is LocalBroadcastManager?",
      "difficulty": "Medium",
      "tags": [
        "broadcast",
        "local",
        "deprecated"
      ],
      "markdown": "Used to send broadcasts within the same app only (more secure & efficient).\n\n⚠️ Deprecated → Use Flow / LiveData / SharedViewModel instead.\n\n### Used Class\n`LocalBroadcastManager`\n\n### Example\n```kotlin\nLocalBroadcastManager.getInstance(this)\n    .sendBroadcast(Intent(\"MY_LOCAL_ACTION\"))\n```"
    },
    {
      "id": 4,
      "section": "Intent & Broadcast",
      "question": "Types of Broadcasts in Android",
      "difficulty": "Medium",
      "tags": [
        "broadcast",
        "types"
      ],
      "markdown": "### a) Normal Broadcast\n- Delivered to all receivers simultaneously.\n\n### b) Ordered Broadcast\n- Delivered one by one based on priority.\n\n### c) Sticky Broadcast\n- Remains in system memory.\n\n### d) Local Broadcast\n- Inside the same app only."
    },
    {
      "id": 5,
      "section": "Intent & Broadcast",
      "question": "Difference between Normal vs Ordered Broadcast",
      "difficulty": "Medium",
      "tags": [
        "broadcast",
        "comparison"
      ],
      "markdown": "| Feature              | Normal Broadcast | Ordered Broadcast      |\n| -------------------- | ---------------- | ---------------------- |\n| Delivery             | Simultaneous     | Sequential             |\n| Priority             | No               | Yes                    |\n| Can stop propagation | ❌ No             | ✅ Yes                  |\n| Method               | sendBroadcast()  | sendOrderedBroadcast() |\n\n### Example\n```kotlin\nsendBroadcast(Intent(\"ACTION_NORMAL\"))\nsendOrderedBroadcast(Intent(\"ACTION_ORDERED\"), null)\n```"
    },
    {
      "id": 6,
      "section": "Intent & Broadcast",
      "question": "How can two Android apps interact?",
      "difficulty": "Medium",
      "tags": [
        "app interaction",
        "communication"
      ],
      "markdown": "### Methods\n\n#### a) Implicit Intent\n```kotlin\nval intent = Intent(Intent.ACTION_SEND)\nintent.type = \"text/plain\"\nstartActivity(intent)\n```\n\n#### b) Content Provider\n- Share data using URI.\n\n#### c) BroadcastReceiver\n- App-to-app communication.\n\n#### d) Deep Links\n- Open another app using URL."
    },
    {
      "id": 7,
      "section": "Intent & Broadcast",
      "question": "What is Deeplink?",
      "difficulty": "Medium",
      "tags": [
        "deeplink",
        "navigation",
        "url"
      ],
      "markdown": "A URL that opens a specific screen inside an app instead of the browser.\n\n### Used Tags\n`<data>`, `<intent-filter>`\n\n### Example (Manifest)\n```xml\n<activity android:name=\".ProductActivity\">\n    <intent-filter>\n        <action android:name=\"android.intent.action.VIEW\"/>\n        <category android:name=\"android.intent.category.DEFAULT\"/>\n        <category android:name=\"android.intent.category.BROWSABLE\"/>\n        <data\n            android:scheme=\"https\"\n            android:host=\"myapp.com\"\n            android:pathPrefix=\"/product\"/>\n    </intent-filter>\n</activity>\n```\n\nOpen link:\n```\nhttps://myapp.com/product/123\n```"
    },
    {
      "id": 8,
      "section": "Service & Background Processing",
      "question": "What is Service?",
      "difficulty": "Medium",
      "tags": [
        "service",
        "background",
        "component"
      ],
      "markdown": "A Service is an Android component that performs long-running operations in the background without UI.\n\n### Used Class\n`android.app.Service`\n\n### Example\n```kotlin\nclass MyService : Service() {\n    override fun onBind(intent: Intent?): IBinder? = null\n\n    override fun onStartCommand(intent: Intent?, flags: Int, startId: Int): Int {\n        Log.d(\"Service\", \"Service Started\")\n        return START_STICKY\n    }\n}\n```\nStart Service:\n```kotlin\nstartService(Intent(this, MyService::class.java))\n```"
    },
    {
      "id": 9,
      "section": "Service & Background Processing",
      "question": "Types of Services in Android",
      "difficulty": "Medium",
      "tags": [
        "service",
        "types"
      ],
      "markdown": "### a) Foreground Service\n### b) Background Service (Deprecated / Restricted)\n### c) Bound Service"
    },
    {
      "id": 10,
      "section": "Service & Background Processing",
      "question": "What is Foreground Service?",
      "difficulty": "Medium",
      "tags": [
        "service",
        "foreground",
        "notification"
      ],
      "markdown": "A service that runs in the foreground with a visible notification.\n\n### Used Methods\n`startForeground()`\n\n### Example\n```kotlin\nstartForeground(1, notification)\n```\nUse cases: Music player, navigation, fitness tracking, location tracking."
    },
    {
      "id": 11,
      "section": "Service & Background Processing",
      "question": "What is Background Service?",
      "difficulty": "Medium",
      "tags": [
        "service",
        "background",
        "deprecated"
      ],
      "markdown": "A service running in the background without user interaction.\n⚠️ Restricted from Android 8+ (Oreo) due to battery optimization & security."
    },
    {
      "id": 12,
      "section": "Service & Background Processing",
      "question": "What is Bound Service?",
      "difficulty": "Medium",
      "tags": [
        "service",
        "bound"
      ],
      "markdown": "A service that allows components to bind and interact with it.\n\n### Used Method\n`bindService()`\n\n### Example\n```kotlin\nbindService(Intent(this, MyService::class.java), connection, Context.BIND_AUTO_CREATE)\n```"
    },
    {
      "id": 13,
      "section": "Service & Background Processing",
      "question": "Difference between Service and IntentService",
      "difficulty": "Medium",
      "tags": [
        "service",
        "intentservice",
        "comparison"
      ],
      "markdown": "| Feature            | Service            | IntentService     |\n| ------------------ | ------------------ | ----------------- |\n| Thread             | Main thread        | Background thread |\n| Queue              | ❌ No               | ✅ Yes             |\n| Stop automatically | ❌ No               | ✅ Yes             |\n| Use case           | Long-running tasks | Sequential tasks  |"
    },
    {
      "id": 14,
      "section": "Service & Background Processing",
      "question": "Why IntentService is deprecated?",
      "difficulty": "Medium",
      "tags": [
        "intentservice",
        "deprecated"
      ],
      "markdown": "Reasons:\n* Not lifecycle-aware\n* No support for modern background limits\n* Replaced by WorkManager / JobIntentService / Coroutines\n⚠️ Deprecated since Android API 30."
    },
    {
      "id": 15,
      "section": "Service & Background Processing",
      "question": "What is JobIntentService?",
      "difficulty": "Medium",
      "tags": [
        "jobintentservice",
        "service",
        "background"
      ],
      "markdown": "A backward-compatible alternative to IntentService using JobScheduler.\n\n### Used Class\n`androidx.core.app.JobIntentService`\n\n### Example\n```kotlin\nclass MyJobIntentService : JobIntentService() {\n    override fun onHandleWork(intent: Intent) {\n        Log.d(\"JobIntentService\", \"Task executed\")\n    }\n}\n```"
    },
    {
      "id": 16,
      "section": "Service & Background Processing",
      "question": "What is WorkManager?",
      "difficulty": "Medium",
      "tags": [
        "workmanager",
        "background",
        "tasks"
      ],
      "markdown": "A modern Android library for guaranteed background work execution.\n\n### Used Class\n`androidx.work.WorkManager`\n\n### Example\n```kotlin\nval workRequest = OneTimeWorkRequestBuilder<MyWorker>().build()\nWorkManager.getInstance(this).enqueue(workRequest)\n```\nBest for: Guaranteed execution, Deferrable tasks, Background sync."
    },
    {
      "id": 17,
      "section": "Threads & Concurrency",
      "question": "What is a Background Thread?",
      "difficulty": "Medium",
      "tags": [
        "thread",
        "background",
        "concurrency"
      ],
      "markdown": "A background thread is a thread that runs tasks without blocking the main (UI) thread.\n\n### Why needed?\n* Network calls\n* Database operations\n* File I/O\n* Heavy computations\n\n### Examples of background threads\n* Thread\n* ExecutorService\n* Coroutine\n* WorkManager\n* Service\n\n### Example\n```kotlin\nThread {\n    // background work\n}.start()\n```"
    },
    {
      "id": 18,
      "section": "Threads & Concurrency",
      "question": "Why should non-UI work not run on the main thread?",
      "difficulty": "Medium",
      "tags": [
        "main thread",
        "ui",
        "performance"
      ],
      "markdown": "The main thread is responsible for UI rendering and user interactions.\n\n❌ If heavy work runs on main thread:\n* UI freezes\n* App becomes unresponsive\n* ANR occurs\n\n> Network and heavy operations must not run on the main thread."
    },
    {
      "id": 19,
      "section": "Threads & Concurrency",
      "question": "What is ANR? How can it be prevented?",
      "difficulty": "Medium",
      "tags": [
        "anr",
        "main thread",
        "prevention"
      ],
      "markdown": "ANR (Application Not Responding) occurs when the main thread is blocked for too long.\n\n⏱️ Time limits:\n* Activity: 5 seconds\n* BroadcastReceiver: 10 seconds\n\n### Common Causes:\n* Long operations on main thread\n* Infinite loops\n* Deadlocks\n* Heavy UI rendering\n* Network calls on main thread\n\n### Prevention:\n* Use background threads\n* Use coroutines / WorkManager\n* Optimize UI\n* Avoid blocking calls"
    },
    {
      "id": 20,
      "section": "Threads & Concurrency",
      "question": "What is AsyncTask?",
      "difficulty": "Medium",
      "tags": [
        "asynctask",
        "deprecated"
      ],
      "markdown": "AsyncTask was used to perform background tasks and update UI easily.\n\n⚠️ Deprecated since API 30.\n\n### Methods\n* onPreExecute()\n* doInBackground()\n* onPostExecute()\n\n### Example\n```kotlin\nclass MyTask : AsyncTask<Void, Void, String>() {\n    override fun doInBackground(vararg params: Void?): String {\n        return \"Result\"\n    }\n\n    override fun onPostExecute(result: String) {\n        println(result)\n    }\n}\n```"
    },
    {
      "id": 21,
      "section": "Threads & Concurrency",
      "question": "What is Loader?",
      "difficulty": "Medium",
      "tags": [
        "loader",
        "deprecated"
      ],
      "markdown": "Loader was used to load data asynchronously in Activities/Fragments.\n\n⚠️ Deprecated in AndroidX.\n\n### Types\n* CursorLoader\n* AsyncTaskLoader\n\n### Issues\n* Complex API\n* Lifecycle problems\n\n### Replacement\n* ViewModel + LiveData + Coroutines"
    },
    {
      "id": 22,
      "section": "Threads & Concurrency",
      "question": "Explain Looper, Handler, and HandlerThread",
      "difficulty": "Medium",
      "tags": [
        "looper",
        "handler",
        "handlerthread"
      ],
      "markdown": "### Looper\nLooper manages a message queue for a thread. Main thread has a Looper by default.\n\n### Handler\nHandler posts tasks/messages to a thread’s Looper.\n\n```kotlin\nval handler = Handler(Looper.getMainLooper())\nhandler.post {\n    // update UI\n}\n```\n\n### HandlerThread\nA background thread with its own Looper.\n\n```kotlin\nval handlerThread = HandlerThread(\"MyThread\")\nhandlerThread.start()\nval handler = Handler(handlerThread.looper)\n```"
    },
    {
      "id": 23,
      "section": "Threads & Concurrency",
      "question": "Different types of threads in Android",
      "difficulty": "Medium",
      "tags": [
        "threads",
        "types",
        "concurrency"
      ],
      "markdown": "| Type              | Description        |\n| ----------------- | ------------------ |\n| Main Thread       | UI thread          |\n| Worker Thread     | Background tasks   |\n| HandlerThread     | Thread with Looper |\n| Thread Pool       | ExecutorService    |\n| Coroutine Threads | Dispatchers        |\n| Binder Thread     | IPC communication  |\n| Render Thread     | UI rendering       |\n| GC Thread         | Garbage Collection |"
    },
    {
      "id": 24,
      "section": "Threads & Concurrency",
      "question": "Which thread does Dispatchers.Default use?",
      "difficulty": "Medium",
      "tags": [
        "coroutine",
        "dispatcher",
        "background"
      ],
      "markdown": "`Dispatchers.Default` uses a shared pool of background threads optimized for CPU-intensive tasks.\n\nBacked by:\n* ForkJoinPool (JVM)\n* CPU core-based thread pool\n\nUse cases:\n* Heavy computations\n* Sorting\n* JSON parsing"
    },
    {
      "id": 25,
      "section": "Threads & Concurrency",
      "question": "Best way to update UI periodically",
      "difficulty": "Medium",
      "tags": [
        "ui",
        "update",
        "periodic",
        "threads"
      ],
      "markdown": "### a) Coroutine + delay()\n```kotlin\nlifecycleScope.launch {\n    while (true) {\n        delay(1000)\n        updateUI()\n    }\n}\n```\n\n### b) Handler\n```kotlin\nval handler = Handler(Looper.getMainLooper())\nval runnable = object : Runnable {\n    override fun run() {\n        updateUI()\n        handler.postDelayed(this, 1000)\n    }\n}\nhandler.post(runnable)\n```\n\n### c) Flow / LiveData (Best practice)\n```kotlin\nflow.collect {\n    updateUI()\n}\n```"
    },
    {
      "id": 26,
      "section": "Threads & Concurrency",
      "question": "How to detect blocking UI thread?",
      "difficulty": "Medium",
      "tags": [
        "ui",
        "blocking",
        "anr",
        "detection"
      ],
      "markdown": "### a) StrictMode\n```kotlin\nStrictMode.setThreadPolicy(\n    StrictMode.ThreadPolicy.Builder()\n        .detectAll()\n        .penaltyLog()\n        .build()\n)\n```\n\n### b) Android Profiler\n* CPU Profiler\n* Main thread monitoring\n\n### c) ANR Reports\n* Play Console\n* Logcat\n\n### d) Systrace / Perfetto\n* System-level tracing\n\n### e) Choreographer / Frame drops\n* Detect UI jank"
    },
    {
      "id": 27,
      "section": "RecyclerView",
      "question": "What is RecyclerView?",
      "difficulty": "Medium",
      "tags": [
        "recyclerview",
        "listview",
        "component"
      ],
      "markdown": "RecyclerView is an advanced and flexible version of ListView used to display large sets of data efficiently.\n\n### Package\n```text\nandroidx.recyclerview.widget.RecyclerView\n```\n\n### Key Components\n* Adapter\n* ViewHolder\n* LayoutManager\n* ItemAnimator\n* ItemDecoration\n\n### Example\n```kotlin\nrecyclerView.layoutManager = LinearLayoutManager(this)\nrecyclerView.adapter = MyAdapter(list)\n```"
    },
    {
      "id": 28,
      "section": "RecyclerView",
      "question": "Difference between RecyclerView and ListView",
      "difficulty": "Medium",
      "tags": [
        "recyclerview",
        "listview",
        "comparison"
      ],
      "markdown": "| Feature            | RecyclerView | ListView      |\n| ------------------ | ------------ | ------------- |\n| ViewHolder pattern | Mandatory    | Optional      |\n| Layout types       | Multiple     | Only vertical |\n| Performance        | High         | Low           |\n| Animations         | Built-in     | Limited       |\n| Flexibility        | Very high    | Low           |\n| Optimization       | Advanced     | Basic         |\n| Nested scrolling   | Better       | Poor          |\n\n> RecyclerView is more flexible, efficient, and extensible than ListView."
    },
    {
      "id": 29,
      "section": "RecyclerView",
      "question": "What is ViewHolder Pattern?",
      "difficulty": "Medium",
      "tags": [
        "viewholder",
        "pattern",
        "recyclerview"
      ],
      "markdown": "ViewHolder pattern caches item views to avoid repeated `findViewById()` calls.\n\n### Purpose\n* Improve performance\n* Reduce view inflation cost\n* Faster scrolling\n\n### Example\n```kotlin\nclass MyViewHolder(view: View) : RecyclerView.ViewHolder(view) {\n    val title = view.findViewById<TextView>(R.id.title)\n}\n```"
    },
    {
      "id": 30,
      "section": "RecyclerView",
      "question": "How does RecyclerView work internally?",
      "difficulty": "Medium",
      "tags": [
        "recyclerview",
        "internal",
        "view recycling"
      ],
      "markdown": "### Core Concept: View Recycling\nRecyclerView reuses item views instead of creating new ones.\n\n### Steps\n1. LayoutManager requests views.\n2. Adapter binds data to ViewHolder.\n3. Off-screen views are recycled.\n4. Recycled views are reused for new items.\n\n### Internal Components\n* Recycler (view cache pool)\n* Adapter\n* LayoutManager\n* ItemAnimator\n\n### View Cache Levels\n| Cache Type           | Description             |\n| -------------------- | ----------------------- |\n| Attached Scrap       | Currently visible views |\n| Cached Views         | Recently detached views |\n| Recycled View Pool   | Shared recycled views   |\n| View Cache Extension | Custom cache            |"
    },
    {
      "id": 31,
      "section": "RecyclerView",
      "question": "RecyclerView Scrolling Optimization Techniques",
      "difficulty": "Medium",
      "tags": [
        "recyclerview",
        "optimization",
        "performance"
      ],
      "markdown": "1) Use ViewHolder properly – avoid expensive operations in `onBindViewHolder()`\n\n2) Use DiffUtil instead of notifyDataSetChanged()\n```kotlin\nDiffUtil.calculateDiff(callback)\n```\n\n3) Enable stable IDs\n```kotlin\nsetHasStableIds(true)\n```\n\n4) Avoid nested layouts (ConstraintLayout recommended)\n\n5) Use ListAdapter instead of RecyclerView.Adapter\n```kotlin\nclass MyAdapter : ListAdapter<Item, VH>(DiffCallback())\n```\n\n6) Disable unnecessary animations\n```kotlin\nrecyclerView.itemAnimator = null\n```\n\n7) Increase RecyclerView cache size\n```kotlin\nrecyclerView.setItemViewCacheSize(20)\n```\n\n8) Use ViewBinding instead of findViewById()\n\n9) Avoid heavy operations in onBindViewHolder()\n* Network calls\n* Image decoding\n* Complex calculations"
    },
    {
      "id": 32,
      "section": "RecyclerView",
      "question": "How to optimize Nested RecyclerView?",
      "difficulty": "Medium",
      "tags": [
        "nested recyclerview",
        "optimization",
        "performance"
      ],
      "markdown": "Nested RecyclerView = RecyclerView inside RecyclerView (e.g., horizontal list inside vertical list)\n\n### Problems\n* Laggy scrolling\n* High memory usage\n* View inflation overhead\n\n### Optimization Techniques\n1) Share RecycledViewPool\n```kotlin\nval pool = RecyclerView.RecycledViewPool()\nparentRecyclerView.setRecycledViewPool(pool)\nchildRecyclerView.setRecycledViewPool(pool)\n```\n\n2) Use setHasFixedSize(true)\n```kotlin\nrecyclerView.setHasFixedSize(true)\n```\n\n3) Disable nested scrolling\n```kotlin\nchildRecyclerView.isNestedScrollingEnabled = false\n```\n\n4) Use ViewPager2 instead of nested RecyclerView (if possible)\n\n5) Preload items (Prefetch)\n```kotlin\nLinearLayoutManager(context).apply {\n    initialPrefetchItemCount = 4\n}\n```\n\n6) Use Paging 3 library for large data\n7) Avoid deep view hierarchy"
    },
    {
      "id": 33,
      "section": "Views & UI Components",
      "question": "What is View?",
      "difficulty": "Easy",
      "tags": [
        "view",
        "ui",
        "component"
      ],
      "markdown": "View is the basic building block of UI in Android. It represents a single UI component.\n\n### Class\n```kotlin\nandroid.view.View\n```\n\n### Examples of View\n* TextView\n* Button\n* ImageView\n* EditText\n\n### Example\n```xml\n<TextView\n    android:layout_width=\"wrap_content\"\n    android:layout_height=\"wrap_content\"\n    android:text=\"Hello\"/>\n```"
    },
    {
      "id": 34,
      "section": "Views & UI Components",
      "question": "What is ViewGroup?",
      "difficulty": "Easy",
      "tags": [
        "viewgroup",
        "ui",
        "container"
      ],
      "markdown": "ViewGroup is a special type of View that can contain other Views (child views).\n\n### Class\n```kotlin\nandroid.view.ViewGroup\n```\n\n### Examples\n* LinearLayout\n* ConstraintLayout\n* RelativeLayout\n* FrameLayout\n\n### Example\n```xml\n<LinearLayout\n    android:layout_width=\"match_parent\"\n    android:layout_height=\"wrap_content\">\n\n    <TextView\n        android:text=\"Child View\"/>\n</LinearLayout>\n```"
    },
    {
      "id": 35,
      "section": "Views & UI Components",
      "question": "Difference between View.GONE and View.INVISIBLE",
      "difficulty": "Easy",
      "tags": [
        "visibility",
        "view",
        "layout"
      ],
      "markdown": "| Property       | View.GONE           | View.INVISIBLE       |\n| -------------- | ------------------ | -------------------- |\n| Visibility     | Hidden             | Hidden               |\n| Space occupied | ❌ No               | ✅ Yes               |\n| Layout impact  | Removed from layout | Layout space remains |\n\n### Example\n```kotlin\nview.visibility = View.GONE\nview.visibility = View.INVISIBLE\n```"
    },
    {
      "id": 36,
      "section": "Views & UI Components",
      "question": "What is SurfaceView?",
      "difficulty": "Medium",
      "tags": [
        "surfaceview",
        "view",
        "graphics",
        "thread"
      ],
      "markdown": "SurfaceView is a View that provides a dedicated drawing surface for rendering graphics in a separate thread.\n\n### Use Cases\n* Games\n* Video playback\n* Camera preview\n* OpenGL rendering\n\n### Difference from View\n* Runs on separate thread\n* Better performance for heavy rendering"
    },
    {
      "id": 37,
      "section": "Views & UI Components",
      "question": "What is Spannable?",
      "difficulty": "Medium",
      "tags": [
        "text",
        "spannable",
        "ui"
      ],
      "markdown": "Spannable is used to apply multiple styles to parts of a text.\n\n### Class\n```kotlin\nSpannableString\n```\n\n### Example\n```kotlin\nval text = SpannableString(\"Hello Android\")\ntext.setSpan(ForegroundColorSpan(Color.RED), 0, 5, Spanned.SPAN_EXCLUSIVE)\ntextView.text = text\n```\n\n### Use Cases\n* Rich text\n* Highlighting text\n* Clickable links"
    },
    {
      "id": 38,
      "section": "Views & UI Components",
      "question": "What is Overdraw?",
      "difficulty": "Medium",
      "tags": [
        "overdraw",
        "ui",
        "performance"
      ],
      "markdown": "Overdraw happens when the system draws the same pixel multiple times in a single frame.\n\n### Causes\n* Deep layout hierarchy\n* Backgrounds on multiple views\n* Overlapping views\n\n### Impact\n* UI lag\n* Battery drain\n\n### Detection\n* Developer Options → Debug GPU Overdraw\n\n### Solution\n* Remove unnecessary backgrounds\n* Use ConstraintLayout\n* Flatten layouts"
    },
    {
      "id": 39,
      "section": "Views & UI Components",
      "question": "Difference between @id and @+id",
      "difficulty": "Easy",
      "tags": [
        "id",
        "xml",
        "view"
      ],
      "markdown": "| Syntax          | Meaning                  |\n| --------------- | ------------------------ |\n| `@+id/viewName` | Create a new ID          |\n| `@id/viewName`  | Reference an existing ID |\n\n### Example\n```xml\n<TextView\n    android:id=\"@+id/title\"/>\n```\n```xml\n<Button\n    android:layout_toRightOf=\"@id/title\"/>\n```"
    },
    {
      "id": 40,
      "section": "Views & UI Components",
      "question": "What is Widget?",
      "difficulty": "Easy",
      "tags": [
        "widget",
        "ui",
        "component"
      ],
      "markdown": "A Widget is a reusable UI component that allows user interaction.\n\n### Examples\n* Button\n* EditText\n* Switch\n* RecyclerView\n\n📌 Also: App Widgets = Home screen widgets."
    },
    {
      "id": 41,
      "section": "Views & UI Components",
      "question": "How to support different screen sizes?",
      "difficulty": "Medium",
      "tags": [
        "responsive",
        "layout",
        "screen"
      ],
      "markdown": "### Techniques\n\n### a) Responsive Layouts\n* ConstraintLayout\n* FlexboxLayout\n\n### b) Resource qualifiers\n| Folder         | Purpose        |\n| -------------- | -------------- |\n| layout-sw600dp | Tablets        |\n| layout-land    | Landscape      |\n| drawable-hdpi  | Screen density |\n| values-night   | Dark mode      |\n\n### c) Use dp & sp instead of px\n\n### d) Vector Drawables\n\n### e) Jetpack Compose responsive UI"
    },
    {
      "id": 42,
      "section": "Views & UI Components",
      "question": "Difference between raw and assets folder",
      "difficulty": "Medium",
      "tags": [
        "resources",
        "storage",
        "folder"
      ],
      "markdown": "| Feature       | raw            | assets       |\n| ------------- | -------------- | ------------ |\n| Folder path   | res/raw        | assets/      |\n| Resource ID   | Yes            | No           |\n| Access method | R.raw.filename | AssetManager |\n| File types    | Limited        | Any file     |\n| Subfolders    | ❌ No           | ✅ Yes       |\n\n### raw:\n```kotlin\nval inputStream = resources.openRawResource(R.raw.file)\n```\n\n### assets:\n```kotlin\nval inputStream = assets.open(\"file.txt\")\n```"
    },
    {
      "id": 43,
      "section": "Views & UI Components",
      "question": "What is Dark Theme?",
      "difficulty": "Easy",
      "tags": [
        "dark mode",
        "theme",
        "ui"
      ],
      "markdown": "Dark Theme is a UI mode where the app uses dark colors to reduce eye strain and battery consumption.\n\n### Implementation\n\n#### a) Theme XML\n```xml\n<style name=\"Theme.MyApp\" parent=\"Theme.MaterialComponents.DayNight\">\n```\n\n#### b) Resource folder\n```\nvalues-night/colors.xml\n```\n\n#### c) Enable dark mode\n```kotlin\nAppCompatDelegate.setDefaultNightMode(AppCompatDelegate.MODE_NIGHT_YES)\n```"
    },
    {
      "id": 44,
      "section": "Data Storage",
      "question": "Ways to store data in Android",
      "difficulty": "Medium",
      "tags": [
        "storage",
        "data",
        "android"
      ],
      "markdown": "| Storage Type        | Use Case                                |\n| ------------------- | --------------------------------------- |\n| SharedPreferences   | Small key-value data                    |\n| DataStore (Jetpack) | Modern replacement of SharedPreferences |\n| Internal Storage    | Private app files                       |\n| External Storage    | Public/shared files                     |\n| SQLite Database     | Structured relational data              |\n| Room Database       | ORM over SQLite                         |\n| ContentProvider     | Data sharing between apps               |\n| Network Storage     | Cloud / API                             |\n| Cache               | Temporary data                          |"
    },
    {
      "id": 45,
      "section": "Data Storage",
      "question": "What is SharedPreferences?",
      "difficulty": "Easy",
      "tags": [
        "sharedpreferences",
        "key-value",
        "storage"
      ],
      "markdown": "SharedPreferences is a lightweight storage mechanism to store key-value pairs.\n\n### Used for\n* User settings\n* Login state\n* Theme preferences\n* Tokens\n\n### Example\n```kotlin\nval prefs = getSharedPreferences(\"MyPrefs\", Context.MODE_PRIVATE)\nprefs.edit().putString(\"username\", \"Aasim\").apply()\n```\n\nRead data:\n```kotlin\nval name = prefs.getString(\"username\", \"\")\n```"
    },
    {
      "id": 46,
      "section": "Data Storage",
      "question": "Difference between commit() and apply()",
      "difficulty": "Medium",
      "tags": [
        "sharedpreferences",
        "commit",
        "apply",
        "threading"
      ],
      "markdown": "| Feature     | commit()                | apply()           |\n| ----------- | ---------------------- | ----------------- |\n| Thread      | Main thread             | Background thread |\n| Return type | boolean                 | void              |\n| Blocking    | Yes                     | No                |\n| Performance | Slower                  | Faster            |\n| Use case    | Immediate result needed | Preferred         |\n\n### Example\n```kotlin\nprefs.edit().putString(\"key\", \"value\").commit()\nprefs.edit().putString(\"key\", \"value\").apply()\n```\n> apply() is asynchronous and recommended, while commit() is synchronous."
    },
    {
      "id": 47,
      "section": "Data Storage",
      "question": "What is ContentProvider?",
      "difficulty": "Medium",
      "tags": [
        "contentprovider",
        "data sharing",
        "android"
      ],
      "markdown": "ContentProvider is an Android component used to share data between different applications.\n\n### Class\n```kotlin\nandroid.content.ContentProvider\n```\n\n### Examples\n* Contacts Provider\n* Media Provider\n* Calendar Provider\n\n### Use Case\n* Inter-app data sharing\n* Secure data access"
    },
    {
      "id": 48,
      "section": "Data Storage",
      "question": "What is Content URI?",
      "difficulty": "Medium",
      "tags": [
        "contenturi",
        "provider",
        "uri"
      ],
      "markdown": "Content URI is the unique identifier used to access data from a ContentProvider.\n\n### Format\n```text\ncontent://authority/path/id\n```\n\n### Example\n```kotlin\ncontent://com.example.app.provider/users/1\n```"
    },
    {
      "id": 49,
      "section": "Data Storage",
      "question": "CRUD operations in ContentProvider",
      "difficulty": "Medium",
      "tags": [
        "crud",
        "contentprovider",
        "data"
      ],
      "markdown": "CRUD = Create, Read, Update, Delete\n\n### Insert (Create)\n```kotlin\ncontentResolver.insert(uri, values)\n```\n### Query (Read)\n```kotlin\ncontentResolver.query(uri, null, null, null, null)\n```\n### Update\n```kotlin\ncontentResolver.update(uri, values, null, null)\n```\n### Delete\n```kotlin\ncontentResolver.delete(uri, null, null)\n```"
    },
    {
      "id": 50,
      "section": "Data Storage",
      "question": "Can SQLite DB be accessed for debugging?",
      "difficulty": "Medium",
      "tags": [
        "sqlite",
        "debug",
        "database"
      ],
      "markdown": "Yes, SQLite DB can be accessed for debugging.\n\n### Methods\n\n#### a) Android Studio Device File Explorer\nPath: `/data/data/<package_name>/databases/`\n\n#### b) adb shell\n```bash\nadb shell\ncd /data/data/com.example.app/databases/\nsqlite3 mydb.db\n```\n#### c) Stetho / Debug DB / Flipper\n* Facebook Stetho\n* DebugDB\n* Flipper\n\n#### d) Room Database Inspector (Android Studio)"
    },
    {
      "id": 51,
      "section": "Networking / Retrofit",
      "question": "What is Retrofit?",
      "difficulty": "Medium",
      "tags": [
        "retrofit",
        "http",
        "network"
      ],
      "markdown": "Retrofit is a type-safe HTTP client library for Android used to call REST APIs.\n\n### Developed by\nSquare\n\n### Built on\nOkHttp\n\n### Features\n* REST API support\n* JSON parsing (Gson, Moshi)\n* Annotations-based API\n* Coroutine support\n\n### Example\n```kotlin\ninterface ApiService {\n    @GET(\"users\")\n    suspend fun getUsers(): List<User>\n}\n```"
    },
    {
      "id": 52,
      "section": "Networking / Retrofit",
      "question": "How to handle multiple network calls using Retrofit?",
      "difficulty": "Medium",
      "tags": [
        "retrofit",
        "network",
        "coroutines",
        "parallel"
      ],
      "markdown": "### a) Sequential calls (Coroutines)\n```kotlin\nval user = api.getUser()\nval posts = api.getPosts(user.id)\n```\n\n### b) Parallel calls (Coroutines async)\n```kotlin\ncoroutineScope {\n    val user = async { api.getUser() }\n    val posts = async { api.getPosts() }\n}\n```\n\n### c) RxJava\n```kotlin\nObservable.zip(api.getUser(), api.getPosts(), ...)\n```\n\n### d) Callback-based\n```kotlin\nCall.enqueue()\n```"
    },
    {
      "id": 53,
      "section": "Networking / OkHttp",
      "question": "What is OkHttp Interceptor?",
      "difficulty": "Medium",
      "tags": [
        "okhttp",
        "interceptor",
        "network"
      ],
      "markdown": "Interceptor is a mechanism in OkHttp to intercept, modify, or log HTTP requests and responses.\n\n### Use cases\n* Logging\n* Authentication\n* Headers\n* Caching\n* Retry logic\n\n### Example\n```kotlin\nval interceptor = Interceptor { chain ->\n    val request = chain.request().newBuilder()\n        .addHeader(\"Authorization\", \"Bearer token\")\n        .build()\n    chain.proceed(request)\n}\n```"
    },
    {
      "id": 54,
      "section": "Networking / OkHttp",
      "question": "Types of OkHttp Interceptors",
      "difficulty": "Medium",
      "tags": [
        "okhttp",
        "interceptor",
        "network"
      ],
      "markdown": "| Type                    | Description                               |\n| ----------------------- | ----------------------------------------- |\n| Application Interceptor | Intercepts before request reaches network |\n| Network Interceptor     | Intercepts after network response         |\n\n### Examples\n* LoggingInterceptor\n* HeaderInterceptor\n* AuthInterceptor\n* CacheInterceptor"
    },
    {
      "id": 55,
      "section": "Networking / OkHttp",
      "question": "HTTP caching in OkHttp",
      "difficulty": "Medium",
      "tags": [
        "okhttp",
        "cache",
        "network"
      ],
      "markdown": "OkHttp supports HTTP response caching using cache headers.\n\n### Setup Cache\n```kotlin\nval cacheSize = 10 * 1024 * 1024 // 10 MB\nval cache = Cache(File(context.cacheDir, \"http_cache\"), cacheSize)\n\nval client = OkHttpClient.Builder()\n    .cache(cache)\n    .build()\n```\n\n### Cache Control\n```kotlin\nCacheControl.Builder()\n    .maxAge(1, TimeUnit.HOURS)\n    .build()\n```"
    },
    {
      "id": 56,
      "section": "Networking / Libraries",
      "question": "HTTP libraries used and why",
      "difficulty": "Easy",
      "tags": [
        "network",
        "libraries",
        "android"
      ],
      "markdown": "| Library           | Why used                 |\n| ----------------- | ------------------------ |\n| Retrofit          | REST API calls           |\n| OkHttp            | Low-level HTTP client    |\n| Volley            | Fast request handling    |\n| Ktor              | Kotlin-first HTTP client |\n| Fuel              | Lightweight HTTP         |\n| HttpURLConnection | Native Java API          |"
    },
    {
      "id": 57,
      "section": "Networking / REST API",
      "question": "How REST APIs work",
      "difficulty": "Medium",
      "tags": [
        "rest",
        "api",
        "network"
      ],
      "markdown": "REST (Representational State Transfer) is an architectural style for communication between client and server.\n\n### Flow\n1. Client sends HTTP request.\n2. Server processes request.\n3. Server returns response (JSON/XML).\n4. Client consumes data.\n\n### Key Principles\n* Stateless\n* Client-server architecture\n* Resource-based URLs\n* HTTP methods"
    },
    {
      "id": 58,
      "section": "Networking / HTTP Methods",
      "question": "HTTP Methods",
      "difficulty": "Easy",
      "tags": [
        "http",
        "methods",
        "network"
      ],
      "markdown": "| Method | Purpose                 |\n| ------ | ----------------------- |\n| GET    | Fetch data              |\n| POST   | Create data             |\n| PUT    | Update entire resource  |\n| PATCH  | Update partial resource |\n| DELETE | Delete data             |\n\n### Example\n```http\nGET /users\nPOST /users\nPUT /users/1\nPATCH /users/1\nDELETE /users/1\n```"
    },
    {
      "id": 59,
      "section": "Networking / Retrofit",
      "question": "Advantage of Retrofit over Volley",
      "difficulty": "Medium",
      "tags": [
        "retrofit",
        "volley",
        "network"
      ],
      "markdown": "Advantages:\n* Type-safe API\n* Better REST support\n* Annotation-based\n* Coroutine & RxJava support\n* Cleaner architecture\n* Easy testing\n\n> Interview line: Retrofit is better for structured REST APIs."
    },
    {
      "id": 60,
      "section": "Networking / Volley",
      "question": "Advantage of Volley over Retrofit",
      "difficulty": "Medium",
      "tags": [
        "volley",
        "retrofit",
        "network"
      ],
      "markdown": "Advantages:\n* Built-in request queue\n* Automatic scheduling\n* Better for small/simple requests\n* Image loading support\n* Faster for frequent small calls\n\n> Interview line: Volley is better for frequent lightweight requests."
    },
    {
      "id": 61,
      "section": "Networking / Retrofit",
      "question": "Advantage of Retrofit over AsyncTask",
      "difficulty": "Medium",
      "tags": [
        "retrofit",
        "asynctask",
        "network"
      ],
      "markdown": "| Retrofit             | AsyncTask               |\n| -------------------- | ----------------------- |\n| Built for networking | Generic background task |\n| Thread-safe          | Poor thread handling    |\n| Error handling       | Weak                    |\n| Scalable             | Not scalable            |\n| Coroutine support    | ❌                       |\n| Maintained           | Deprecated              |\n\n> Retrofit is designed for networking, while AsyncTask is deprecated and not suitable for API calls."
    },
    {
      "id": 62,
      "section": "Permissions & Security",
      "question": "Different protection levels in permissions",
      "difficulty": "Medium",
      "tags": [
        "permissions",
        "security",
        "android"
      ],
      "markdown": "| Level             | Description                                   |\n| ----------------- | --------------------------------------------- |\n| normal            | Low-risk permissions, granted automatically   |\n| dangerous         | Sensitive permissions, require user approval  |\n| signature         | Granted only if apps share same signature     |\n| signatureOrSystem | Granted to system apps or same-signature apps |\n\n### Examples\n| Permission          | Level            |\n| ------------------- | ---------------- |\n| INTERNET            | normal           |\n| CAMERA              | dangerous        |\n| READ_CONTACTS       | dangerous        |\n| SYSTEM_ALERT_WINDOW | signature/system |"
    },
    {
      "id": 63,
      "section": "Permissions & Security",
      "question": "Types of permissions",
      "difficulty": "Medium",
      "tags": [
        "permissions",
        "security",
        "android"
      ],
      "markdown": "### Based on granting method:\n1. Normal permissions\n2. Dangerous permissions\n3. Signature permissions\n4. Special permissions\n\n### Dangerous permission groups:\n| Group      | Example               |\n| ---------- | --------------------- |\n| Location   | ACCESS_FINE_LOCATION  |\n| Camera     | CAMERA                |\n| Storage    | READ_EXTERNAL_STORAGE |\n| Microphone | RECORD_AUDIO          |\n| Contacts   | READ_CONTACTS         |"
    },
    {
      "id": 64,
      "section": "Permissions & Security",
      "question": "How to handle runtime permissions in Android?",
      "difficulty": "Medium",
      "tags": [
        "permissions",
        "runtime",
        "android"
      ],
      "markdown": "Check dangerous permissions at runtime (API 23+).\n\n### Steps\n1. Check permission\n2. Request permission\n3. Handle result\n\n### Example\n```kotlin\nif (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA)\n    != PackageManager.PERMISSION_GRANTED) {\n\n    ActivityCompat.requestPermissions(\n        this,\n        arrayOf(Manifest.permission.CAMERA),\n        100\n    )\n}\n```\n\nHandle result:\n```kotlin\noverride fun onRequestPermissionsResult(\n    requestCode: Int,\n    permissions: Array<out String>,\n    grantResults: IntArray\n) {\n    if (requestCode == 100 && grantResults.isNotEmpty()\n        && grantResults[0] == PackageManager.PERMISSION_GRANTED) {\n        // Permission granted\n    }\n}\n```"
    },
    {
      "id": 65,
      "section": "Permissions & Security",
      "question": "Android security best practices",
      "difficulty": "Medium",
      "tags": [
        "security",
        "android",
        "best-practices"
      ],
      "markdown": "* Use HTTPS instead of HTTP\n* Avoid hardcoding API keys\n* Use ProGuard / R8 obfuscation\n* Use EncryptedSharedPreferences\n* Validate SSL certificates\n* Restrict exported components\n* Use scoped storage\n* Minimize permissions\n* Secure WebView\n* Detect root / tampering\n* Use SafetyNet / Play Integrity API"
    },
    {
      "id": 66,
      "section": "Permissions & Security",
      "question": "How do you know if the device is rooted?",
      "difficulty": "Medium",
      "tags": [
        "security",
        "root",
        "android"
      ],
      "markdown": "Check for su binary, root apps, writable system paths.\n\n### Example\n```kotlin\nfun isDeviceRooted(): Boolean {\n    val paths = arrayOf(\n        \"/system/bin/su\",\n        \"/system/xbin/su\",\n        \"/sbin/su\",\n        \"/system/app/Superuser.apk\"\n    )\n    return paths.any { File(it).exists() }\n}\n```"
    },
    {
      "id": 67,
      "section": "Permissions & Security",
      "question": "What is Symmetric Encryption?",
      "difficulty": "Medium",
      "tags": [
        "encryption",
        "security",
        "android"
      ],
      "markdown": "Symmetric encryption uses the same key for encryption and decryption.\n\n### Examples\n* AES\n* DES\n* Triple DES\n\n### Diagram\n```\nPlain Text → (Key) → Cipher Text → (Same Key) → Plain Text\n```"
    },
    {
      "id": 68,
      "section": "Permissions & Security",
      "question": "What is Asymmetric Encryption?",
      "difficulty": "Medium",
      "tags": [
        "encryption",
        "security",
        "android"
      ],
      "markdown": "Asymmetric encryption uses two keys:\n* Public Key (encryption)\n* Private Key (decryption)\n\n### Examples\n* RSA\n* ECC\n\n### Diagram\n```\nPlain Text → Public Key → Cipher Text → Private Key → Plain Text\n```"
    },
    {
      "id": 69,
      "section": "Permissions & Security",
      "question": "How do you encrypt data in Java?",
      "difficulty": "Medium",
      "tags": [
        "encryption",
        "aes",
        "security"
      ],
      "markdown": "### Example using AES\n```kotlin\nfun encrypt(data: String, secret: String): String {\n    val key = SecretKeySpec(secret.toByteArray(), \"AES\")\n    val cipher = Cipher.getInstance(\"AES\")\n    cipher.init(Cipher.ENCRYPT_MODE, key)\n    return Base64.encodeToString(cipher.doFinal(data.toByteArray()), Base64.DEFAULT)\n}\n```"
    },
    {
      "id": 70,
      "section": "Permissions & Security",
      "question": "What is SSL Pinning?",
      "difficulty": "Medium",
      "tags": [
        "ssl",
        "security",
        "android"
      ],
      "markdown": "SSL Pinning is a security technique that binds the app to a specific server certificate or public key.\n\n### Purpose\n* Prevent Man-in-the-Middle (MITM) attacks\n* Ensure server authenticity"
    },
    {
      "id": 71,
      "section": "Permissions & Security",
      "question": "How do you implement SSL pinning in Android?",
      "difficulty": "Medium",
      "tags": [
        "ssl",
        "security",
        "android",
        "okhttp"
      ],
      "markdown": "### Method 1: OkHttp Certificate Pinning\n```kotlin\nval certificatePinner = CertificatePinner.Builder()\n    .add(\"example.com\", \"sha256/AAAAAAAAAAAAAAAAAAAA...\")\n    .build()\n\nval client = OkHttpClient.Builder()\n    .certificatePinner(certificatePinner)\n    .build()\n```\n\n### Method 2: Network Security Config (Recommended)\n📁 res/xml/network_security_config.xml\n```xml\n<network-security-config>\n    <domain-config>\n        <domain includeSubdomains=\"true\">example.com</domain>\n        <pin-set expiration=\"2027-01-01\">\n            <pin digest=\"SHA-256\">AAAAAAAAAAAA...</pin>\n        </pin-set>\n    </domain-config>\n</network-security-config>\n```\n📄 AndroidManifest.xml\n```xml\n<application\n    android:networkSecurityConfig=\"@xml/network_security_config\">\n</application>\n```"
    },
    {
      "id": 72,
      "section": "Memory & Performance",
      "question": "What is Memory Leak?",
      "difficulty": "Medium",
      "tags": [
        "memory",
        "leak",
        "performance"
      ],
      "markdown": "A memory leak happens when objects are no longer needed but still referenced, so the Garbage Collector cannot free memory.\n\n### Result\n* Increased memory usage\n* App slowdown\n* OutOfMemoryError (OOM)\n* App crash\n\n### Example\n```kotlin\nobject Singleton {\n    var activity: Activity? = null // ❌ memory leak\n}\n```"
    },
    {
      "id": 73,
      "section": "Memory & Performance",
      "question": "Garbage Collection (GC) in Android",
      "difficulty": "Medium",
      "tags": [
        "gc",
        "memory",
        "performance"
      ],
      "markdown": "Garbage Collection is the process of automatically freeing unused memory.\n\n### How it works\n1. Identifies unreachable objects.\n2. Frees heap memory.\n3. Compacts memory.\n\n### Types of GC in Android (ART)\n* Minor GC\n* Major GC\n* Full GC\n\n### Impact\n* UI jank\n* Frame drops (if GC runs frequently)"
    },
    {
      "id": 74,
      "section": "Memory & Performance",
      "question": "Causes of Memory Leaks",
      "difficulty": "Medium",
      "tags": [
        "memory",
        "leak",
        "performance"
      ],
      "markdown": "Common causes:\n* Static references to Activity/Context\n* Anonymous inner classes\n* Long-running threads\n* Handlers with delayed messages\n* Unclosed resources (Cursor, InputStream)\n* Bitmap memory misuse\n* Listeners not removed\n* Memory leaks in singletons\n\n### Example (Handler leak)\n```kotlin\nclass MyActivity : Activity() {\n    private val handler = Handler() // ❌ leak risk\n}\n```\n\n### Fix\n```kotlin\nprivate val handler = Handler(Looper.getMainLooper())\n```"
    },
    {
      "id": 75,
      "section": "Memory & Performance",
      "question": "What is Bitmap Pool?",
      "difficulty": "Medium",
      "tags": [
        "bitmap",
        "memory",
        "performance"
      ],
      "markdown": "Bitmap Pool is a memory optimization technique where bitmaps are reused instead of allocating new memory.\n\n### Used in libraries\n* Glide\n* Fresco\n* Coil\n* Picasso\n\n### Benefit\n* Reduce GC pressure\n* Faster image loading\n* Lower memory usage"
    },
    {
      "id": 76,
      "section": "Memory & Performance",
      "question": "How to handle large bitmaps efficiently?",
      "difficulty": "Medium",
      "tags": [
        "bitmap",
        "memory",
        "performance"
      ],
      "markdown": "### Techniques\n\n#### a) Downsampling images\n```kotlin\nval options = BitmapFactory.Options().apply {\n    inSampleSize = 4\n}\nBitmapFactory.decodeResource(resources, R.drawable.image, options)\n```\n\n#### b) Use image loading libraries\n* Glide\n* Coil\n* Picasso\n\n#### c) Use RGB_565 instead of ARGB_8888\n```kotlin\noptions.inPreferredConfig = Bitmap.Config.RGB_565\n```\n\n#### d) Avoid loading full-size images into memory\n#### e) Use Bitmap Pool (Glide)"
    },
    {
      "id": 76,
      "section": "Memory & Performance",
      "question": "How to use Android Memory Profiler?",
      "difficulty": "Medium",
      "tags": [
        "memory",
        "profiler",
        "android-studio"
      ],
      "markdown": "✅ **Tool:** Android Studio → Profiler → Memory\n\n### ✅ Steps:\n1. Run app in Android Studio.\n2. Open Profiler.\n3. Select Memory tab.\n4. Monitor:\n   * Heap usage\n   * Object allocation\n   * GC events\n   * Leaks\n\n### ✅ Features:\n* Heap dump\n* Allocation tracking\n* Leak detection"
    },
    {
      "id": 77,
      "section": "Memory & Performance",
      "question": "How to measure method execution time?",
      "difficulty": "Medium",
      "tags": [
        "performance",
        "timing",
        "kotlin"
      ],
      "markdown": "### ✅ a) System.currentTimeMillis()\n```kotlin\nval start = System.currentTimeMillis()\n// method call\nval end = System.currentTimeMillis()\nLog.d(\"Time\", \"Execution time = ${end - start} ms\")\n```\n\n### ✅ b) System.nanoTime() (more accurate)\n```kotlin\nval start = System.nanoTime()\n// method call\nval end = System.nanoTime()\nLog.d(\"Time\", \"Execution time = ${(end - start)/1_000_000} ms\")\n```\n\n### ✅ c) Kotlin measureTimeMillis()\n```kotlin\nval time = measureTimeMillis {\n    myMethod()\n}\n```\n\n### ✅ d) Trace API\n```kotlin\nTrace.beginSection(\"MyMethod\")\n// code\nTrace.endSection()\n```"
    },
    {
      "id": 78,
      "section": "Battery Optimization",
      "question": "How to reduce battery consumption?",
      "difficulty": "Medium",
      "tags": [
        "battery",
        "optimization",
        "android"
      ],
      "markdown": "### ✅ Best Practices:\n\n#### 🔋 a) Optimize network calls\n* Batch requests\n* Use caching\n* Avoid polling\n\n#### 🔋 b) Use WorkManager instead of background services\n\n#### 🔋 c) Optimize location updates\n* Reduce frequency\n* Use balanced accuracy\n\n#### 🔋 d) Avoid wake locks\n\n#### 🔋 e) Optimize animations & UI rendering\n\n#### 🔋 f) Use JobScheduler / WorkManager\n\n#### 🔋 g) Reduce overdraw\n\n#### 🔋 h) Avoid unnecessary background tasks\n\n#### 🔋 i) Use Doze mode & App Standby properly\n\n#### 🔋 j) Optimize alarms (setExact vs setInexact)"
    },
    {
      "id": 79,
      "section": "Gradle & Build System",
      "question": "What is Gradle?",
      "difficulty": "Medium",
      "tags": [
        "gradle",
        "build-system",
        "android"
      ],
      "markdown": "✅ **Definition:**\nGradle is a build automation tool used to compile, test, package, and deploy Android applications.\n\n✅ **Features:**\n* Dependency management\n* Build variants\n* Plugin-based system\n* Incremental builds\n\n✅ **Key Files:**\n* `build.gradle` / `build.gradle.kts`\n* `settings.gradle`\n* `gradle.properties`"
    },
    {
      "id": 80,
      "section": "Gradle & Build System",
      "question": "What do you mean by Gradle Wrapper?",
      "difficulty": "Medium",
      "tags": [
        "gradle",
        "wrapper",
        "android"
      ],
      "markdown": "✅ **Definition:**\nGradle Wrapper ensures that the project uses a specific Gradle version, independent of the system-installed Gradle.\n\n✅ **Files:**\n* `gradlew`\n* `gradlew.bat`\n* `gradle/wrapper/gradle-wrapper.properties`\n\n✅ **Benefit:**\n* Consistent builds across environments"
    },
    {
      "id": 81,
      "section": "Gradle & Build System",
      "question": "Difference between implementation and api",
      "difficulty": "Medium",
      "tags": [
        "gradle",
        "dependencies",
        "android"
      ],
      "markdown": "| Feature           | implementation     | api                          |\n| ----------------- | ------------------ | ---------------------------- |\n| Visibility        | Internal to module | Exposed to dependent modules |\n| Compilation speed | Faster             | Slower                       |\n| Encapsulation     | Better             | Less                         |\n| Use case          | Default choice     | Library APIs                 |\n\n✅ Example:\n```gradle\ndependencies {\n    implementation(\"com.squareup.retrofit2:retrofit:2.9.0\")\n    api(\"com.google.guava:guava:31.0\")\n}\n```"
    },
    {
      "id": 82,
      "section": "Gradle & Build System",
      "question": "Difference between Build Type, Product Flavor, and Build Variant",
      "difficulty": "Medium",
      "tags": [
        "gradle",
        "build-variants",
        "android"
      ],
      "markdown": "### ✅ Build Type\nDefines how the app is built.\n* debug\n* release\n\n### ✅ Product Flavor\nDefines different versions of the app.\n* free / paid\n* dev / prod\n\n### ✅ Build Variant\nCombination of build type + product flavor.\nExample: `freeDebug`, `paidRelease`\n\n### ✅ Comparison Table:\n| Concept        | Purpose          |\n| -------------- | ---------------- |\n| Build Type     | Debug vs Release |\n| Product Flavor | App variants     |\n| Build Variant  | Combination      |"
    },
    {
      "id": 83,
      "section": "Gradle & Build System",
      "question": "What do you know about Version Catalog?",
      "difficulty": "Medium",
      "tags": [
        "gradle",
        "version-catalog",
        "android"
      ],
      "markdown": "✅ **Definition:**\nVersion Catalog is a Gradle feature to centralize dependency versions in one place.\n\n✅ **File:**\n```\ngradle/libs.versions.toml\n```\n\n✅ Example:\n```toml\n[versions]\nretrofit = \"2.9.0\"\n\n[libraries]\nretrofit = { module = \"com.squareup.retrofit2:retrofit\", version.ref = \"retrofit\" }\n```\n\nUse in Gradle:\n```gradle\nimplementation(libs.retrofit)\n```\n✅ Benefits:\n* Centralized dependency management\n* Clean build.gradle\n* Easy upgrades"
    },
    {
      "id": 84,
      "section": "ProGuard & App Size",
      "question": "What is Android ProGuard?",
      "difficulty": "Medium",
      "tags": [
        "proguard",
        "r8",
        "android"
      ],
      "markdown": "✅ **Definition:**\nProGuard is a tool used to:\n* Shrink code\n* Obfuscate code\n* Optimize bytecode\n* Remove unused classes\n\n⚠️ Replaced by R8 (default in modern Android)."
    },
    {
      "id": 85,
      "section": "ProGuard & App Size",
      "question": "Android ProGuard Rules",
      "difficulty": "Medium",
      "tags": [
        "proguard",
        "rules",
        "android"
      ],
      "markdown": "✅ **Definition:**\nRules that define what code should be kept or removed.\n\n✅ Example:\n```proguard\n-keep class com.example.model.** { *; }\n-dontwarn okhttp3.**\n-keepattributes Signature\n```"
    },
    {
      "id": 86,
      "section": "ProGuard & App Size",
      "question": "ProGuard applied at which stage of build?",
      "difficulty": "Medium",
      "tags": [
        "proguard",
        "build",
        "android"
      ],
      "markdown": "✅ **Answer:**\nProGuard/R8 runs during the **release build** stage after compilation and before APK/AAB packaging.\n\n### ✅ Build Flow:\n```\nKotlin/Java → DEX → R8(ProGuard) → APK/AAB → Signing → Packaging\n```"
    },
    {
      "id": 87,
      "section": "App Size Optimization",
      "question": "Ways to reduce application size",
      "difficulty": "Medium",
      "tags": [
        "app-size",
        "optimization",
        "android"
      ],
      "markdown": "### ✅ Techniques:\n* Enable R8 / ProGuard\n* Use Android App Bundle (AAB)\n* Remove unused resources\n* Use vector drawables\n* Enable resource shrinking\n* Split APK by ABI, density, language\n* Optimize images (WebP)\n* Avoid heavy libraries\n* Use dynamic feature modules"
    },
    {
      "id": 88,
      "section": "App Delivery",
      "question": "What do you know about App Bundles?",
      "difficulty": "Medium",
      "tags": [
        "app-bundle",
        "aab",
        "android"
      ],
      "markdown": "✅ **Definition:**\nAndroid App Bundle (AAB) is a publishing format that allows Google Play to generate optimized APKs for devices.\n\n✅ Benefits:\n* Smaller downloads\n* Device-specific APKs\n* Faster installs\n\n✅ Difference:\n| APK            | AAB                     |\n| -------------- | ----------------------- |\n| Single package | Multiple optimized APKs |\n| Larger size    | Smaller size            |\n| Manual splits  | Automatic splits        |"
    },
    {
      "id": 89,
      "section": "App Delivery",
      "question": "What do you know about Play Feature Delivery?",
      "difficulty": "Medium",
      "tags": [
        "play-feature-delivery",
        "dynamic-feature",
        "android"
      ],
      "markdown": "✅ **Definition:**\nPlay Feature Delivery allows delivering app features dynamically using dynamic feature modules.\n\n✅ Types:\n* Install-time delivery\n* On-demand delivery\n* Conditional delivery\n\n✅ Example Use Cases:\n* Games levels\n* Chat module\n* Payment module"
    },
    {
      "id": 90,
      "section": "App Delivery",
      "question": "What is Play App Signing?",
      "difficulty": "Medium",
      "tags": [
        "play-app-signing",
        "android",
        "security"
      ],
      "markdown": "✅ **Definition:**\nPlay App Signing is a Google Play service that manages and protects your app signing key.\n\n✅ Benefits:\n* Secure key storage\n* Key recovery\n* Optimized APK signing\n\n✅ Flow:\n1. Developer uploads AAB.\n2. Google Play signs APK with app signing key.\n3. Users download signed APK."
    },
    {
      "id": 161,
      "section": "App Performance",
      "question": "What is ANR?",
      "difficulty": "Medium",
      "tags": [
        "ANR",
        "android",
        "performance",
        "main-thread"
      ],
      "markdown": "✅ **Definition:**\nANR (Application Not Responding) occurs when the main thread is blocked for too long.\n\n⏱️ **Time limits:**\n* Activity: 5 seconds\n* BroadcastReceiver: 10 seconds\n* Service: 20 seconds\n\n### ✅ Causes:\n* Long-running tasks on main thread\n* Network calls on UI thread\n* Deadlocks / infinite loops\n* Heavy layout rendering\n\n### ✅ Prevention:\n* Use background threads / coroutines\n* Optimize UI rendering\n* Avoid blocking main thread"
    },
    {
      "id": 162,
      "section": "App Performance",
      "question": "What is App Startup Time?",
      "difficulty": "Medium",
      "tags": [
        "startup-time",
        "android",
        "performance"
      ],
      "markdown": "✅ **Definition:**\nApp startup time is the time taken from launching the app to displaying the first screen.\n\n### ✅ Types of Startup:\n| Type       | Description             |\n| ---------- | ----------------------- |\n| Cold Start | App not in memory       |\n| Warm Start | App partially in memory |\n| Hot Start  | App already in memory   |\n\n### ✅ Optimization Techniques:\n* Lazy initialization\n* Avoid heavy work in Application/Activity `onCreate()`\n* Use SplashScreen API properly\n* Enable Baseline Profiles\n* Optimize layout\n* Use ViewBinding instead of DataBinding\n* Defer non-critical initialization"
    },
    {
      "id": 163,
      "section": "App Performance",
      "question": "How can a Memory Leak be created in Android?",
      "difficulty": "Medium",
      "tags": [
        "memory-leak",
        "android",
        "performance"
      ],
      "markdown": "⚠️ **Example (Bad Code):**\n```kotlin\nobject MySingleton {\n    var activity: Activity? = null // ❌ Memory Leak\n}\n```\nAnother example:\n```kotlin\nclass MyActivity : Activity() {\n    private val handler = Handler() // ❌ may cause leak\n}\n```"
    },
    {
      "id": 164,
      "section": "App Performance",
      "question": "How to avoid Memory Leak in Android?",
      "difficulty": "Medium",
      "tags": [
        "memory-leak",
        "android",
        "best-practices"
      ],
      "markdown": "### ✅ Best Practices:\n* Avoid static references to Activity/Context\n* Use WeakReference when needed\n* Clear listeners in onDestroy()\n* Use lifecycle-aware components\n* Use applicationContext instead of activityContext when possible\n* Cancel coroutines/jobs properly\n* Avoid anonymous inner classes"
    },
    {
      "id": 165,
      "section": "App Performance",
      "question": "How to identify Memory Leak in Android?",
      "difficulty": "Medium",
      "tags": [
        "memory-leak",
        "android",
        "tools"
      ],
      "markdown": "### ✅ Tools:\n* Android Studio Memory Profiler\n* LeakCanary\n* MAT (Memory Analyzer Tool)\n* Logcat (GC logs)\n\n### ✅ Example with LeakCanary:\n```gradle\ndebugImplementation \"com.squareup.leakcanary:leakcanary-android:2.12\"\n```"
    },
    {
      "id": 166,
      "section": "App Delivery",
      "question": "How to reduce App Size in Android?",
      "difficulty": "Medium",
      "tags": [
        "app-size",
        "android",
        "optimization"
      ],
      "markdown": "### ✅ Techniques:\n* Enable R8 / ProGuard\n* Use Android App Bundle (AAB)\n* Remove unused resources\n* Enable resource shrinking\n* Use vector drawables\n* Optimize images (WebP)\n* Split APK by ABI, density, language\n* Avoid heavy libraries\n* Use dynamic feature modules"
    },
    {
      "id": 167,
      "section": "UI/UX",
      "question": "What are Downloadable Fonts?",
      "difficulty": "Easy",
      "tags": [
        "fonts",
        "android",
        "ui"
      ],
      "markdown": "✅ **Definition:**\nDownloadable Fonts allow apps to download fonts from Google Play services instead of bundling them.\n\n### ✅ Benefits:\n* Reduce APK size\n* Dynamic font loading\n* Faster updates\n\n### ✅ Example (XML):\n```xml\n<TextView\n    android:fontFamily=\"@font/roboto\" />\n```\nFont request:\n```xml\n<font-family\n    app:fontProviderAuthority=\"com.google.android.gms.fonts\"\n    app:fontProviderPackage=\"com.google.android.gms\"\n    app:fontProviderQuery=\"Roboto\" />\n```"
    },
    {
      "id": 168,
      "section": "UI/UX",
      "question": "What is Splash Screen and SplashScreen API?",
      "difficulty": "Medium",
      "tags": [
        "splash-screen",
        "android",
        "startup"
      ],
      "markdown": "### ✅ Traditional Splash Screen (Old Way)\n* Separate SplashActivity\n* Delay using Handler\n* ❌ Bad practice (slow startup)\n\n### ✅ SplashScreen API (Android 12+)\nOfficial Jetpack API for splash screen.\n\n### ✅ Implementation:\nGradle:\n```gradle\nimplementation \"androidx.core:core-splashscreen:1.0.1\"\n```\nTheme:\n```xml\n<style name=\"Theme.MyApp\" parent=\"Theme.SplashScreen\">\n    <item name=\"windowSplashScreenBackground\">@color/white</item>\n    <item name=\"windowSplashScreenAnimatedIcon\">@drawable/logo</item>\n</style>\n```\nActivity:\n```kotlin\noverride fun onCreate(savedInstanceState: Bundle?) {\n    installSplashScreen()\n    super.onCreate(savedInstanceState)\n}\n```\n### ✅ Benefits:\n* Faster startup\n* System-managed splash screen\n* Consistent UX"
    },
    {
      "id": 169,
      "section": "Notifications",
      "question": "What is Android Notification System?",
      "difficulty": "Medium",
      "tags": [
        "notifications",
        "android",
        "ui"
      ],
      "markdown": "The Android Notification System allows apps to display messages outside the app UI in the notification bar.\n\n### 🔹 Key Components\n1. **NotificationManager** - System service used to show notifications.\n2. **NotificationChannel (Android 8.0+)** - Required for notifications, defines importance, sound, vibration.\n3. **NotificationCompat.Builder** - Builds the notification.\n4. **PendingIntent** - Defines action when user taps the notification.\n\n### 🔹 Flow\n```\nCreate Channel → Build Notification → Notify via NotificationManager\n```\n\n### 🔹 Example\n```kotlin\nval channelId = \"my_channel\"\nval channel = NotificationChannel(channelId, \"My Notifications\", NotificationManager.IMPORTANCE_HIGH)\nval manager = getSystemService(NotificationManager::class.java)\nmanager.createNotificationChannel(channel)\n\nval intent = Intent(this, MainActivity::class.java)\nval pendingIntent = PendingIntent.getActivity(this, 0, intent, 0)\n\nval notification = NotificationCompat.Builder(this, channelId)\n    .setSmallIcon(R.drawable.ic_notification)\n    .setContentTitle(\"Hello\")\n    .setContentText(\"This is a notification\")\n    .setContentIntent(pendingIntent)\n    .setAutoCancel(true)\n    .build()\n\nmanager.notify(1, notification)\n```"
    },
    {
      "id": 170,
      "section": "Notifications",
      "question": "How does Notification communicate with a Service?",
      "difficulty": "Medium",
      "tags": [
        "notifications",
        "service",
        "android"
      ],
      "markdown": "A notification often communicates with a **Service** (especially Foreground Service).\n\n### 🔹 Common Use Cases\n* Music player 🎵\n* Download manager ⬇️\n* Location tracking 📍\n* Background tasks\n\n### ✅ Methods:\n1. **Intent + Service**\n```kotlin\nval intent = Intent(this, MyService::class.java)\nintent.action = \"PLAY\"\nval pendingIntent = PendingIntent.getService(this, 0, intent, 0)\n```\n2. **Foreground Service with Notification**\n```kotlin\nstartForeground(1, notification)\n```\n3. **BroadcastReceiver** - Notification button → Broadcast → Service reacts.\n4. **ViewModel / LiveData / EventBus** - Advanced UI-service sync.\n\n### 🔹 Interview Answer\n> Notification communicates with a Service using PendingIntent, BroadcastReceiver, or Foreground Service. The notification sends actions to the service, and the service updates the notification or app state."
    },
    {
      "id": 171,
      "section": "Notifications",
      "question": "What are App Shortcuts in Android?",
      "difficulty": "Medium",
      "tags": [
        "app-shortcuts",
        "android",
        "ui"
      ],
      "markdown": "App Shortcuts provide quick actions from the app icon (long press).\n\n### 🔹 Types of App Shortcuts\n\n1. **Static Shortcuts** (XML)\n```xml\n<shortcuts xmlns:android=\"http://schemas.android.com/apk/res/android\">\n    <shortcut\n        android:shortcutId=\"compose\"\n        android:shortLabel=\"Compose\"\n        android:icon=\"@drawable/ic_compose\"\n        android:intentAction=\"android.intent.action.VIEW\"\n        android:targetClass=\"com.example.ComposeActivity\" />\n</shortcuts>\n```\n\n2. **Dynamic Shortcuts** (Runtime)\n```kotlin\nval shortcut = ShortcutInfo.Builder(this, \"id1\")\n    .setShortLabel(\"Profile\")\n    .setIntent(Intent(this, ProfileActivity::class.java))\n    .build()\nshortcutManager.dynamicShortcuts = listOf(shortcut)\n```\n\n3. **Pinned Shortcuts** - Added directly to home screen."
    },
    {
      "id": 172,
      "section": "Kotlin JVM Annotations",
      "question": "What is @JvmStatic?",
      "difficulty": "Medium",
      "tags": [
        "kotlin",
        "jvm",
        "annotations"
      ],
      "markdown": "### 🔹 What is `@JvmStatic`?\n`@JvmStatic` tells Kotlin to generate a **static method or field** for Java interoperability.\n\n### 🔹 Why needed?\nFunctions inside `companion object` are not static by default. Java cannot call them like static methods unless we use `@JvmStatic`.\n\n### 🔹 Example\n```kotlin\nclass Utils {\n    companion object {\n        @JvmStatic\n        fun showMessage() {\n            println(\"Hello\")\n        }\n    }\n}\n```\nJava call:\n```java\nUtils.showMessage();\n```\nWithout `@JvmStatic`, Java would call:\n```java\nUtils.Companion.showMessage();\n```\n### 🔹 Interview Answer\n> `@JvmStatic` makes Kotlin functions or properties behave like static members for Java interoperability."
    },
    {
      "id": 173,
      "section": "Kotlin JVM Annotations",
      "question": "What is @JvmField?",
      "difficulty": "Medium",
      "tags": [
        "kotlin",
        "jvm",
        "annotations"
      ],
      "markdown": "### 🔹 What is `@JvmField`?\n`@JvmField` exposes a Kotlin property as a **public field** instead of getter/setter.\n\n### 🔹 Why needed?\nBy default, Kotlin generates getter/setter methods. Java cannot directly access fields without them.\n\n### 🔹 Example\n```kotlin\nclass Constants {\n    companion object {\n        @JvmField\n        val API_URL = \"https://api.example.com\"\n    }\n}\n```\nJava call:\n```java\nString url = Constants.API_URL;\n```\nWithout `@JvmField`, Java would call:\n```java\nConstants.Companion.getAPI_URL();\n```\n### 🔹 Interview Answer\n> `@JvmField` prevents Kotlin from generating getter/setter and exposes the property as a Java field."
    },
    {
      "id": 174,
      "section": "Kotlin JVM Annotations",
      "question": "What is @JvmOverloads?",
      "difficulty": "Medium",
      "tags": [
        "kotlin",
        "jvm",
        "annotations"
      ],
      "markdown": "### 🔹 What is `@JvmOverloads`?\n`@JvmOverloads` generates multiple overloaded methods for Java when Kotlin uses default parameters.\n\n### 🔹 Why needed?\nJava does not support default arguments like Kotlin.\n\n### 🔹 Example\n```kotlin\nclass User {\n    @JvmOverloads\n    fun greet(name: String = \"Guest\", age: Int = 18) {\n        println(\"Hello $name, age $age\")\n    }\n}\n```\nGenerated Java methods:\n```java\ngreet();\ngreet(String name);\ngreet(String name, int age);\n```\n### 🔹 Interview Answer\n> `@JvmOverloads` generates overloaded methods for Java when Kotlin functions have default parameters."
    }
  ]
}
