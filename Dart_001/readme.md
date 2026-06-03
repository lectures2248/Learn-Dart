
  # TOPIC 1: INTRODUCTION TO DART        

---

## 1.1 What is Dart?

Dart is a **general-purpose, object-oriented programming language** developed by **Google**.
It is designed to build fast applications for mobile, web, desktop, and server.

Dart is the **official language of Flutter** — Google's UI framework for building cross-platform apps.
Without Dart, you cannot write Flutter applications.

> Think of Dart as the engine. Flutter is the car. You must understand the engine first.

---

## 1.2 History of Dart

| Year | Event |
|------|-------|
| **2011** | Dart was introduced by Lars Bak and Kasper at Google |
| **2013** | Dart 1.0 officially released |
| **2018** | Dart 2.0 released — major improvements, strong typing added |
| **2019** | Flutter adopted Dart as its official language |
| **2021** | Dart 2.12 released — Null Safety introduced |
| **2023** | Dart 3.0 released — 100% sound null safety, records and patterns added |
| **Present** | Dart is one of the fastest-growing languages due to Flutter's popularity |

**Founders:** Lars Bak (worked on V8 JavaScript engine at Google) and Kasper.

**Why Google made Dart:**
JavaScript had performance and scalability problems for large applications.
Google needed a language that was fast, structured, and easy to learn.
Dart was their answer.

---

## 1.3 Features of Dart

### 1. Object-Oriented
Everything in Dart is an object — even numbers and functions.
Dart supports classes, objects, inheritance, and interfaces.

### 2. Strongly Typed
Every variable has a type. This catches errors before the program runs.
```dart
int age = 20;       // Only integers allowed
String name = "Ali"; // Only text allowed
```

### 3. Null Safety
Dart prevents the most common programming crash — using a variable that has no value (null).
```dart
String name = "Ali";   // Cannot be null
String? city;          // This one CAN be null (? makes it nullable)
```

### 4. AOT and JIT Compilation
- **JIT (Just-In-Time):** Used during development. Gives hot reload in Flutter.
- **AOT (Ahead-Of-Time):** Used for final app release. Makes the app fast.

### 5. Cross-Platform
One Dart codebase can run on:
- Android
- iOS
- Web
- Windows / macOS / Linux

### 6. Garbage Collection
Dart automatically manages memory. You don't manually free memory like in C/C++.

### 7. Asynchronous Programming
Dart supports `async` and `await` — important for loading data from the internet without freezing the app.

### 8. Open Source
Dart is completely free and open source. The source code is available on GitHub.

---

## 1.4 Advantages of Dart

| Advantage | Explanation |
|-----------|-------------|
| **Easy to Learn** | Syntax is similar to Java, C#, and JavaScript — familiar to most developers |
| **Fast Performance** | AOT compilation produces native machine code — very fast execution |
| **Single Language** | One language for mobile, web, and desktop |
| **Hot Reload** | Changes appear instantly during development — no need to restart the app |
| **Strong Community** | Large and growing community, backed by Google |
| **Rich Standard Library** | Built-in tools for collections, math, dates, HTTP, and more |
| **Flutter Integration** | First-class support for Flutter — the most popular cross-platform framework |
| **Null Safety** | Eliminates an entire class of runtime errors |

---

## 1.5 Installation of Dart SDK

### What is SDK?
SDK stands for **Software Development Kit**.
It is a set of tools that allows you to write, run, and compile Dart programs.

---

### Method 1: Install Dart SDK Directly (Windows)

**Step 1:** Go to the official Dart website:
```
https://dart.dev/get-dart
```

**Step 2:** Download the Windows installer (.exe file)

**Step 3:** Run the installer — it installs Dart and adds it to your system PATH automatically

**Step 4:** Open Command Prompt and verify:
```
dart --version
```
You should see something like:
```
Dart SDK version: 3.x.x
```

---

### Method 2: Install via Flutter (Recommended)

If you install Flutter, Dart is included automatically.
```
https://flutter.dev/docs/get-started/install
```
After Flutter is installed:
```
flutter --version
dart --version
```
Both will work.

---

### Setting Up VS Code for Dart

1. Install **Visual Studio Code** from `https://code.visualstudio.com`
2. Open VS Code → Go to Extensions (Ctrl + Shift + X)
3. Search for **"Dart"** → Install the Dart extension by Dart Code
4. Search for **"Flutter"** → Install the Flutter extension (optional but recommended)
5. Create a new file with `.dart` extension and start coding

---

## 1.6 Creating a Simple Dart Application

### Your First Dart Program

```dart
void main() {
  print("Hello, World!");
}
```

**Output:**
```
Hello, World!
```


#  VARIABLES AND DATA TYPES        
---

## 2.1 What is a Variable?

A **variable** is a named storage location in memory that holds a value.

Think of it like a box:
- The box has a **label** (variable name)
- The box holds a **value** (the data)
- The box has a **type** (what kind of data it can hold)

```dart
int age = 21;
// int   → type (what kind of data)
// age   → name (the label)
// 21    → value (the data stored)
```

---

## 2.2 Primitive vs Non-Primitive Data Types

### Primitive Data Types
Primitive types store **single, simple values** directly in memory.
They are the building blocks of data.

| Type | Description | Example |
|------|-------------|---------|
| `int` | Whole numbers | `10`, `-5`, `0` |
| `double` | Decimal numbers | `3.14`, `-2.5` |
| `bool` | True or false only | `true`, `false` |
| `String` | Text / characters | `"Hello"`, `'Ali'` |

```dart
void main() {
  int marks = 85;          // whole number
  double temperature = 37.5; // decimal number
  bool isPassed = true;    // true or false
  String name = "Sara";    // text

  print(marks);
  print(temperature);
  print(isPassed);
  print(name);
}
```

## 2.3 Understanding All Variable Types in Detail

---

### int — Integer

Stores whole numbers (no decimal point).
Range: Very large — Dart integers have no fixed limit on size.

```dart
void main() {
  int age = 22;
  int temperature = -5;    // Negative numbers allowed
  int population = 220000000;

  print(age);
  print(temperature);
  print(population);

  // Arithmetic with int
  int a = 10;
  int b = 3;
  print(a + b);   // 13
  print(a - b);   // 7
  print(a * b);   // 30
  print(a ~/ b);  // 3  (integer division — no decimal)
  print(a % b);   // 1  (remainder)
}
```

---

### double — Decimal Number

Stores numbers with decimal points.
Use when you need precision — prices, measurements, percentages.

```dart
void main() {
  double price = 299.99;
  double pi = 3.14159;
  double weight = 70.5;
  double temperature = -2.3;

  print(price);
  print(pi);

  // Arithmetic with double
  double total = price * 3;
  print(total);   // 899.97

  // int can be stored in double
  double x = 5;    // Valid — stored as 5.0
  print(x);        // 5.0
}
```

---

### String — Text

Stores any sequence of characters — letters, numbers, symbols, spaces.
Always enclosed in single `'` or double `"` quotes.

```dart
void main() {
  String firstName = "Ahmed";
  String lastName = 'Khan';
  String city = "Karachi";

  // Joining strings (Concatenation)
  String fullName = firstName + " " + lastName;
  print(fullName);    // Ahmed Khan

  // String Interpolation (better way)
  print("My name is $firstName $lastName");
  print("I live in $city");

  // Multi-line string (triple quotes)
  String address = """
  House 12,
  Street 5,
  Karachi
  """;
  print(address);

  // Useful String properties
  print(firstName.length);         // 5 — number of characters
  print(firstName.toUpperCase());  // AHMED
  print(firstName.toLowerCase());  // ahmed
  print(firstName.contains("med")); // true
}
```

---

### bool — Boolean

Stores only two values: `true` or `false`.
Used in conditions, flags, and decision making.

```dart
void main() {
  bool isLoggedIn = true;
  bool isAdmin = false;
  bool hasInternet = true;

  print(isLoggedIn);    // true
  print(isAdmin);       // false
}
```
