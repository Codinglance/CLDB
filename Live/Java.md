{
"category": "Java",
"format": "Markdown inside JSON",
"questions":[
{
"id": 1,
"section": "Java Basics",
"question": "What are the main features of Java?",
"difficulty": "Easy",
"tags": ["java", "oop", "features"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Main Features of Java\n\n- **Object-Oriented**: Encapsulation, Inheritance, Polymorphism, Abstraction\n- **Platform Independent**: Write Once, Run Anywhere (JVM)\n- **Robust & Secure**: Exception handling, strong memory management\n- **Multithreaded**: Built-in thread support\n- **Automatic Memory Management**: Garbage Collection\n- **Rich APIs**: Collections, I/O, Networking"
},
{
"id": 2,
"section": "Java Basics",
"question": "Difference between JDK, JRE, and JVM",
"difficulty": "Easy",
"tags": ["jdk", "jre", "jvm"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### JDK vs JRE vs JVM\n\n- **JVM**: Executes Java bytecode\n- **JRE**: JVM + Libraries (to run Java programs)\n- **JDK**: JRE + Compiler + Development tools"
},
{
"id": 3,
"section": "Java Basics",
"question": "Difference between == and equals()",
"difficulty": "Easy",
"tags": ["equals", "reference", "string"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### == vs equals()\n\n```java\nString a = \"Hello\";\nString b = new String(\"Hello\");\n\nSystem.out.println(a == b);      // false\nSystem.out.println(a.equals(b)); // true\n```\n\n- `==` → reference comparison\n- `equals()` → value comparison"
},
{
"id": 4,
"section": "OOP",
"question": "Difference between abstract class and interface",
"difficulty": "Medium",
"tags": ["abstract", "interface", "oop"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Abstract Class vs Interface\n\n- Abstract class can have constructors and variables\n- Interface supports multiple inheritance\n- Interface variables are `public static final` by default"
},
{
"id": 5,
"section": "Java Basics",
"question": "What are Java access modifiers?",
"difficulty": "Easy",
"tags": ["access-modifiers", "encapsulation"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Java Access Modifiers\n\n- `private` → class level\n- `default` → package level\n- `protected` → package + subclass\n- `public` → everywhere"
},
{
"id": 6,
"section": "Memory Management",
"question": "Explain Java memory model (Heap & Stack)",
"difficulty": "Medium",
"tags": ["heap", "stack", "memory"],
"askedIn": ["Google"],
"expectedReadTime": "1 min",
"markdown": "### Java Memory Model\n\n- **Heap**: Stores objects, managed by GC\n- **Stack**: Stores method calls & local variables\n- **Method Area**: Static data & class metadata"
},
{
"id": 7,
"section": "Collections",
"question": "Difference between ArrayList and LinkedList",
"difficulty": "Medium",
"tags": ["arraylist", "linkedlist", "collections"],
"askedIn": ["Amazon"],
"expectedReadTime": "1 min",
"markdown": "### ArrayList vs LinkedList\n\n- ArrayList → Fast access, slow insertion\n- LinkedList → Slow access, fast insertion\n- LinkedList uses extra memory for pointers"
},
{
"id": 8,
"section": "Multithreading",
"question": "What is a Java thread and how to create one?",
"difficulty": "Medium",
"tags": ["thread", "multithreading"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Creating Threads\n\n```java\nclass MyThread extends Thread {\n    public void run() {\n        System.out.println(\"Running\");\n    }\n}\n```\n\nOr using `Runnable` interface."
},
{
"id": 9,
"section": "Exception Handling",
"question": "Difference between throw and throws",
"difficulty": "Easy",
"tags": ["exception", "throw", "throws"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### throw vs throws\n\n- `throw` → explicitly throw exception\n- `throws` → declare exception in method signature"
},
{
"id": 10,
"section": "Java Keywords",
"question": "Difference between final, finally, and finalize()",
"difficulty": "Easy",
"tags": ["final", "finally", "finalize"],
"askedIn": ["Google"],
"expectedReadTime": "45 sec",
"markdown": "### final vs finally vs finalize()\n\n- `final` → constant / no override\n- `finally` → always executes\n- `finalize()` → called before GC"
}
]
}
