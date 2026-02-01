{
"category": "DSA",
"format": "Markdown inside JSON",
"questions": [
{
"id": 1,
"section": "Arrays",
"question": "Reverse an Array",
"difficulty": "Easy",
"tags": ["array", "reverse"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Reverse an Array\n\n**Problem:** Reverse the elements of an array.\n\n```java\nint[] arr = {1, 2, 3, 4, 5};\nfor (int i = arr.length - 1; i >= 0; i--) {\n    System.out.print(arr[i] + \" \");\n}\n```\n\n**Output:**\n```\n5 4 3 2 1\n```"
},
{
"id": 2,
"section": "Arrays",
"question": "Find Maximum and Minimum in an Array",
"difficulty": "Easy",
"tags": ["array", "min", "max"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Find Max and Min\n\n```java\nint max = arr[0], min = arr[0];\nfor (int num : arr) {\n    if (num > max) max = num;\n    if (num < min) min = num;\n}\n```\n\n**Output:**\n```\nMax: 9\nMin: 1\n```"
},
{
"id": 3,
"section": "Linked List",
"question": "Reverse a Singly Linked List",
"difficulty": "Medium",
"tags": ["linkedlist", "reverse"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Reverse Linked List\n\n```java\nNode prev = null, curr = head;\nwhile (curr != null) {\n    Node next = curr.next;\n    curr.next = prev;\n    prev = curr;\n    curr = next;\n}\nreturn prev;\n```\n\n**Output:**\n```\n3 2 1\n```"
},
{
"id": 4,
"section": "Strings",
"question": "Check if a String is Palindrome",
"difficulty": "Easy",
"tags": ["string", "palindrome"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Palindrome String\n\n```java\nString reversed = new StringBuilder(str).reverse().toString();\nif (str.equals(reversed)) {\n    System.out.println(\"Palindrome\");\n}\n```\n\n**Output:**\n```\nlevel is a palindrome\n```"
},
{
"id": 5,
"section": "Recursion",
"question": "Find Factorial using Recursion",
"difficulty": "Easy",
"tags": ["recursion", "math"],
"askedIn": ["Google"],
"expectedReadTime": "45 sec",
"markdown": "### Factorial using Recursion\n\n```java\nif (n == 0 || n == 1) return 1;\nreturn n * factorial(n - 1);\n```\n\n**Output:**\n```\nFactorial of 5 is 120\n```"
},
{
"id": 6,
"section": "Recursion / Iteration",
"question": "Fibonacci Series using Iteration",
"difficulty": "Easy",
"tags": ["fibonacci", "loop"],
"askedIn": ["Amazon"],
"expectedReadTime": "45 sec",
"markdown": "### Fibonacci Series\n\n```java\nint a = 0, b = 1;\nfor (int i = 2; i < n; i++) {\n    int c = a + b;\n    a = b;\n    b = c;\n}\n```\n\n**Output:**\n```\n0 1 1 2 3 5 8 13 21 34\n```"
},
{
"id": 7,
"section": "Stack",
"question": "Implement Stack using Array",
"difficulty": "Medium",
"tags": ["stack", "array"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Stack using Array\n\n```java\nvoid push(int x) {\n    if (top == capacity - 1) return;\n    arr[++top] = x;\n}\n\nint pop() {\n    if (top == -1) return -1;\n    return arr[top--];\n}\n```"
},
{
"id": 8,
"section": "Queue",
"question": "Implement Queue using Array",
"difficulty": "Medium",
"tags": ["queue", "array"],
"askedIn": ["Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Queue using Array\n\n```java\nvoid enqueue(int x) {\n    if (rear == capacity) return;\n    arr[rear++] = x;\n}\n\nint dequeue() {\n    if (front == rear) return -1;\n    return arr[front++];\n}\n```"
},
{
"id": 9,
"section": "Searching",
"question": "Binary Search in a Sorted Array",
"difficulty": "Medium",
"tags": ["binary-search", "array"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Binary Search\n\n```java\nwhile (left <= right) {\n    int mid = left + (right - left) / 2;\n    if (arr[mid] == target) return mid;\n    else if (arr[mid] < target) left = mid + 1;\n    else right = mid - 1;\n}\nreturn -1;\n```\n\n**Output:**\n```\nIndex: 2\n```"
},
{
"id": 10,
"section": "Linked List",
"question": "Detect Cycle in a Linked List (Floyd’s Algorithm)",
"difficulty": "Medium",
"tags": ["linkedlist", "cycle"],
"askedIn": ["Google", "Amazon"],
"expectedReadTime": "1 min",
"markdown": "### Cycle Detection (Floyd’s Algorithm)\n\n```java\nNode slow = head, fast = head;\nwhile (fast != null && fast.next != null) {\n    slow = slow.next;\n    fast = fast.next.next;\n    if (slow == fast) return true;\n}\nreturn false;\n```\n\n**Output:**\n```\ntrue\n```"
}
]
}
