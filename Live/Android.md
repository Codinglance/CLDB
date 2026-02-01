{
"category": "Android",
"format": "Markdown inside JSON",
"questions": [
{
"id": 1,
"section": "Android Basics",
"question": "What is Android?",
"difficulty": "Easy",
"tags": ["android", "os", "basics"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "Android is an **open-source mobile operating system** developed by Google, primarily used for smartphones, tablets, TVs, and wearables."
},
{
"id": 2,
"section": "Android Components",
"question": "What are the main components of Android?",
"difficulty": "Easy",
"tags": ["activity", "service", "broadcast", "content-provider"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "**Four main components:**\n\n- **Activity** – UI screen\n- **Service** – Background task\n- **Broadcast Receiver** – Listens to system events\n- **Content Provider** – Manages shared app data"
},
{
"id": 3,
"section": "Activity Lifecycle",
"question": "Explain Activity lifecycle",
"difficulty": "Easy",
"tags": ["activity", "lifecycle"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "| Method | Description |\n|-------|------------|\n| onCreate() | Initialize UI |\n| onStart() | Visible |\n| onResume() | User interaction |\n| onPause() | Partially visible |\n| onStop() | Not visible |\n| onDestroy() | Cleanup |\n| onRestart() | Restart activity |"
},
{
"id": 4,
"section": "Fragments",
"question": "What is a Fragment?",
"difficulty": "Easy",
"tags": ["fragment", "ui"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "A **Fragment** is a reusable portion of UI inside an Activity.\n\n**Advantages:**\n- Modular UI\n- Reusable\n- Tablet support"
},
{
"id": 5,
"section": "Fragments",
"question": "Difference between Activity and Fragment",
"difficulty": "Easy",
"tags": ["activity", "fragment", "comparison"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "| Activity | Fragment |\n|---------|----------|\n| Independent | Dependent on Activity |\n| Own lifecycle | Child lifecycle |\n| Entry point | UI component |"
},
{
"id": 6,
"section": "Intents",
"question": "What is an Intent?",
"difficulty": "Easy",
"tags": ["intent", "navigation"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "Intent is a **messaging object** used to communicate between components.\n\n**Types:**\n- Explicit Intent\n- Implicit Intent"
},
{
"id": 7,
"section": "Intents",
"question": "Explicit vs Implicit Intent",
"difficulty": "Easy",
"tags": ["intent", "explicit", "implicit"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "| Explicit | Implicit |\n|---------|----------|\n| Target known | Target unknown |\n| Internal navigation | External apps |\n| Faster | Flexible |"
},
{
"id": 8,
"section": "App Configuration",
"question": "What is AndroidManifest.xml?",
"difficulty": "Easy",
"tags": ["manifest", "configuration"],
"askedIn": ["Google"],
"expectedReadTime": "30 sec",
"markdown": "AndroidManifest.xml defines **app configuration** like components, permissions, package name, and SDK versions."
},
{
"id": 9,
"section": "Core Concepts",
"question": "What is Context?",
"difficulty": "Easy",
"tags": ["context", "application"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "Context provides access to **resources, system services, and app environment**.\n\n**Types:**\n- Application Context\n- Activity Context"
},
{
"id": 10,
"section": "Performance",
"question": "What is ANR?",
"difficulty": "Medium",
"tags": ["anr", "performance"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "**ANR (Application Not Responding)** occurs when the UI thread is blocked for too long.\n\n**Causes:**\n- Network on main thread\n- Heavy computation"
},
{
"id": 11,
"section": "UI Basics",
"question": "Difference between dp, sp, px",
"difficulty": "Easy",
"tags": ["dp", "sp", "px"],
"askedIn": ["Amazon"],
"expectedReadTime": "30 sec",
"markdown": "| Unit | Usage |\n|----|------|\n| dp | Layout |\n| sp | Text |\n| px | Avoid |"
},
{
"id": 12,
"section": "UI Basics",
"question": "What is View and ViewGroup?",
"difficulty": "Easy",
"tags": ["view", "viewgroup"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "| View | ViewGroup |\n|------|-----------|\n| UI element | Container |\n| No children | Has children |"
},
{
"id": 13,
"section": "RecyclerView",
"question": "What is RecyclerView?",
"difficulty": "Easy",
"tags": ["recyclerview", "list"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "RecyclerView is an advanced list component that efficiently displays large data sets using the **ViewHolder pattern**."
},
{
"id": 14,
"section": "RecyclerView",
"question": "RecyclerView vs ListView",
"difficulty": "Medium",
"tags": ["recyclerview", "listview"],
"askedIn": ["Google"],
"expectedReadTime": "45 sec",
"markdown": "| RecyclerView | ListView |\n|--------------|----------|\n| Better performance | Slower |\n| Flexible layouts | Limited |"
},
{
"id": 15,
"section": "ViewBinding",
"question": "What is ViewBinding?",
"difficulty": "Easy",
"tags": ["viewbinding"],
"askedIn": ["Amazon"],
"expectedReadTime": "30 sec",
"markdown": "ViewBinding provides **type-safe access** to views without using findViewById."
},
{
"id": 16,
"section": "ViewBinding",
"question": "ViewBinding vs DataBinding",
"difficulty": "Medium",
"tags": ["viewbinding", "databinding"],
"askedIn": ["Google"],
"expectedReadTime": "45 sec",
"markdown": "| ViewBinding | DataBinding |\n|-------------|-------------|\n| Simple | Complex |\n| No XML logic | Supports XML logic |"
},
{
"id": 17,
"section": "Layouts",
"question": "What is ConstraintLayout?",
"difficulty": "Easy",
"tags": ["constraintlayout", "ui"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "30 sec",
"markdown": "ConstraintLayout allows building **complex layouts with a flat hierarchy**, improving performance."
},
{
"id": 18,
"section": "UI Visibility",
"question": "VISIBLE vs INVISIBLE vs GONE",
"difficulty": "Easy",
"tags": ["visibility", "ui"],
"askedIn": ["Amazon"],
"expectedReadTime": "30 sec",
"markdown": "| State | Visible | Space |\n|------|---------|-------|\n| VISIBLE | Yes | Yes |\n| INVISIBLE | No | Yes |\n| GONE | No | No |"
},
{
"id": 19,
"section": "Services",
"question": "What is a Service?",
"difficulty": "Easy",
"tags": ["service", "background"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "Service runs **background tasks** without UI.\n\n**Types:**\n- Foreground\n- Background\n- Bound"
},
{
"id": 20,
"section": "Broadcast Receiver",
"question": "What is BroadcastReceiver?",
"difficulty": "Easy",
"tags": ["broadcastreceiver"],
"askedIn": ["Google"],
"expectedReadTime": "30 sec",
"markdown": "BroadcastReceiver listens to **system-wide events** like battery low and network changes."
},
{
"id": 21,
"section": "Content Provider",
"question": "What is ContentProvider?",
"difficulty": "Easy",
"tags": ["contentprovider", "data"],
"askedIn": ["Google"],
"expectedReadTime": "30 sec",
"markdown": "ContentProvider manages and shares app data between applications securely."
},
{
"id": 22,
"section": "Performance",
"question": "What is Overdraw?",
"difficulty": "Medium",
"tags": ["overdraw", "performance"],
"askedIn": ["Google"],
"expectedReadTime": "30 sec",
"markdown": "Overdraw happens when a pixel is drawn multiple times, causing performance issues."
},
{
"id": 23,
"section": "Layouts",
"question": "What is LayoutInflater?",
"difficulty": "Easy",
"tags": ["layoutinflater"],
"askedIn": ["Amazon"],
"expectedReadTime": "30 sec",
"markdown": "LayoutInflater converts XML layouts into View objects at runtime."
},
{
"id": 24,
"section": "UI Support",
"question": "How Android handles screen sizes?",
"difficulty": "Easy",
"tags": ["screens", "density"],
"askedIn": ["Google"],
"expectedReadTime": "45 sec",
"markdown": "Android supports multiple screens using **dp, sp, qualifiers, and density buckets**."
},
{
"id": 25,
"section": "Application",
"question": "What is Application class?",
"difficulty": "Easy",
"tags": ["application", "lifecycle"],
"askedIn": ["Google"],
"expectedReadTime": "30 sec",
"markdown": "Application class is the **base class** that maintains global app state."
}
]
}
