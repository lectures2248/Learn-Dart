
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
| **2011** | Dart was introduced by Lars Bak and Kasper Lund at Google |
| **2013** | Dart 1.0 officially released |
| **2018** | Dart 2.0 released — major improvements, strong typing added |
| **2019** | Flutter adopted Dart as its official language |
| **2021** | Dart 2.12 released — Null Safety introduced |
| **2023** | Dart 3.0 released — 100% sound null safety, records and patterns added |
| **Present** | Dart is one of the fastest-growing languages due to Flutter's popularity |

**Founders:** Lars Bak (worked on V8 JavaScript engine at Google) and Kasper Lund.

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

**Explanation line by line:**

| Code | Meaning |
|------|---------|
| `void` | This function does not return any value |
| `main()` | The name of the starting function — Dart always looks for this |
| `{ }` | Curly braces define the body — code inside runs when program starts |
| `print()` | Built-in function that displays output on screen |
| `"Hello, World!"` | A String value (text enclosed in double or single quotes) |
| `;` | Semicolon ends every statement in Dart |

---

### How to Run a Dart File

**In Terminal / Command Prompt:**
```
dart run filename.dart
```

**In VS Code:**
Press `F5` or right-click the file → "Run Dart File"

---

## 1.7 Identifiers in Dart

### What is an Identifier?

An **identifier** is a name you give to a variable, function, class, or any other element in your program.

```dart
int studentAge = 20;     // "studentAge" is the identifier
String firstName = "Ali"; // "firstName" is the identifier
void greetUser() { }      // "greetUser" is the identifier
```

---

### Rules for Identifiers

| Rule | Valid Example | Invalid Example |
|------|--------------|-----------------|
| Must start with a letter or underscore `_` | `name`, `_value` | `1name`, `@value` |
| Can contain letters, digits, and underscores | `student1`, `my_var` | `student-1`, `my var` |
| Cannot be a Dart keyword | `myClass` | `class`, `void` |
| Case-sensitive | `age` and `Age` are different | — |
| No spaces allowed | `firstName` | `first name` |

---

### Naming Conventions in Dart

| Type | Convention | Example |
|------|------------|---------|
| Variables & functions | camelCase | `studentName`, `calculateTotal()` |
| Classes | PascalCase | `StudentInfo`, `MyHomePage` |
| Constants | camelCase with `const` | `const maxLimit = 100` |
| Private members | starts with `_` | `_privateVar` |

---

## 1.8 Keywords in Dart

**Keywords** are reserved words that Dart uses for its own purposes.
You **cannot** use these as identifiers (variable names, function names, etc.)

### Complete List of Dart Keywords

| | | | |
|-|-|-|-|
| `abstract` | `as` | `assert` | `async` |
| `await` | `break` | `case` | `catch` |
| `class` | `const` | `continue` | `covariant` |
| `default` | `deferred` | `do` | `dynamic` |
| `else` | `enum` | `export` | `extends` |
| `external` | `factory` | `false` | `final` |
| `finally` | `for` | `Function` | `get` |
| `hide` | `if` | `implements` | `import` |
| `in` | `interface` | `is` | `late` |
| `library` | `mixin` | `new` | `null` |
| `on` | `operator` | `part` | `required` |
| `rethrow` | `return` | `set` | `show` |
| `static` | `super` | `switch` | `sync` |
| `this` | `throw` | `true` | `try` |
| `typedef` | `var` | `void` | `while` |
| `with` | `yield` | | |

### Most Commonly Used Keywords (for beginners)

| Keyword | Purpose |
|---------|---------|
| `var` | Declare a variable |
| `void` | Function that returns nothing |
| `int` | Integer data type |
| `String` | Text data type |
| `bool` | True/false data type |
| `if` | Conditional statement |
| `else` | Alternative for if |
| `for` | Loop |
| `while` | Loop |
| `return` | Return a value from a function |
| `class` | Define a class |
| `true` / `false` | Boolean values |
| `null` | No value |
| `final` | Value cannot change |
| `const` | Compile-time constant |

---
#       TOPIC 2: VARIABLES AND DATA TYPES        
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

---

### Non-Primitive Data Types
Non-primitive types store **collections or complex data**.
They are built from primitive types.

| Type | Description | Example |
|------|-------------|---------|
| `List` | Ordered collection of values | `[1, 2, 3]` |
| `Map` | Key-value pairs | `{"name": "Ali", "age": 20}` |
| `Set` | Unordered unique values | `{1, 2, 3}` |
| `Object` | Base type of everything in Dart | Any class instance |

```dart
void main() {
  List<String> fruits = ["Apple", "Mango", "Banana"];  // List
  Map<String, int> scores = {"Ali": 90, "Sara": 85};   // Map
  Set<int> uniqueNums = {1, 2, 3, 2, 1};               // Set (duplicates removed)

  print(fruits);
  print(scores);
  print(uniqueNums);  // prints {1, 2, 3} — duplicates removed automatically
}
```

---

### Key Difference

| Primitive | Non-Primitive |
|-----------|---------------|
| Stores a single value | Stores multiple values |
| Fixed size in memory | Dynamic size |
| `int`, `double`, `bool`, `String` | `List`, `Map`, `Set`, `Object` |
| Simpler to use | More powerful |

---

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

  // Used in conditions
  if (isLoggedIn) {
    print("Welcome back!");
  } else {
    print("Please login first.");
  }

  // Comparison results are bool
  int age = 20;
  bool isAdult = age >= 18;    // true
  print(isAdult);

  // Logical operators with bool
  print(isLoggedIn && isAdmin);   // false (both must be true)
  print(isLoggedIn || isAdmin);   // true  (at least one must be true)
  print(!isLoggedIn);             // false (flips the value)
}
```

---

### dynamic — Any Type

A variable declared as `dynamic` can hold any type of value and can change type.
Use it carefully — it removes type safety.

```dart
void main() {
  dynamic value = "Hello";
  print(value);        // Hello
  print(value.runtimeType);  // String

  value = 42;
  print(value);        // 42
  print(value.runtimeType);  // int

  value = true;
  print(value);        // true
  print(value.runtimeType);  // bool

  value = 3.14;
  print(value);        // 3.14
  print(value.runtimeType);  // double
}
```

> Use `dynamic` when you don't know the type in advance — like when reading data from an API.
> Avoid overusing it — it disables type checking and can cause runtime errors.

---

### var — Type Inference

`var` lets Dart detect the type automatically from the assigned value.
Once assigned, the type is locked — you cannot change it later.

```dart
void main() {
  var name = "Ali";       // Dart detects: String
  var age = 25;           // Dart detects: int
  var price = 99.99;      // Dart detects: double
  var isActive = true;    // Dart detects: bool

  print(name.runtimeType);   // String
  print(age.runtimeType);    // int

  // name = 100;  // ERROR — cannot assign int to a String var
}
```

---

### final — Value Set Once

A `final` variable can only be assigned **one time**.
After it is set, it cannot be changed.
The value is determined at **runtime** (when the program runs).

```dart
void main() {
  final String country = "Pakistan";
  final int birthYear = 2002;

  print(country);
  print(birthYear);

  // country = "India";  // ERROR — cannot change a final variable
}
```

---

### const — Compile-Time Constant

`const` is like `final` but stricter.
The value must be known at **compile time** (before the program runs).
Used for values that are truly fixed forever.

```dart
void main() {
  const double pi = 3.14159;
  const int maxStudents = 30;
  const String appName = "My Flutter App";

  print(pi);
  print(maxStudents);
  print(appName);

  // pi = 3.0;  // ERROR — cannot reassign a const
}
```

---

### final vs const — The Key Difference

```dart
void main() {
  // const — value must be known before program runs
  const int taxRate = 17;              // Known at compile time ✓

  // final — value can be determined when program runs
  final DateTime now = DateTime.now(); // Set when program runs ✓

  // const DateTime now2 = DateTime.now(); // ERROR — DateTime.now() not known at compile time
}
```

| | `final` | `const` |
|-|---------|---------|
| Can change after set? | No | No |
| Value determined | At runtime | At compile time |
| Use for | One-time assigned values | True constants |

---

### null and Null Safety

`null` means a variable has **no value**.
Dart's null safety prevents you from accidentally using a null variable.

```dart
void main() {
  String name = "Ali";
  // name = null;   // ERROR — String cannot be null

  String? city;     // The ? makes it nullable
  print(city);      // null

  city = "Karachi";
  print(city);      // Karachi

  // Null check before using
  if (city != null) {
    print(city.toUpperCase());
  }

  // Null coalescing operator ?? — use default if null
  String? nickname;
  print(nickname ?? "No nickname");   // No nickname
}
```

---

#      TOPIC 3: CONTROL FLOW STATEMENTS          
---

## 3.1 What are Operators?

An **operator** is a symbol that performs an operation on values or variables.
The values on which the operator acts are called **operands**.

```dart
int result = 10 + 5;
//           10   +   5
//         operand  operator  operand
```

---

### Types of Operators in Dart

---

#### A. Arithmetic Operators

Used to perform mathematical calculations.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `+` | Addition | `10 + 3` | `13` |
| `-` | Subtraction | `10 - 3` | `7` |
| `*` | Multiplication | `10 * 3` | `30` |
| `/` | Division | `10 / 3` | `3.3333` (double) |
| `~/` | Integer Division | `10 ~/ 3` | `3` (no decimal) |
| `%` | Modulus (remainder) | `10 % 3` | `1` |

```dart
void main() {
  int a = 15;
  int b = 4;

  print(a + b);    // 19
  print(a - b);    // 11
  print(a * b);    // 60
  print(a / b);    // 3.75
  print(a ~/ b);   // 3
  print(a % b);    // 3
}
```

---

#### B. Relational / Comparison Operators

Compare two values. Always return `true` or `false`.

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `==` | Equal to | `5 == 5` | `true` |
| `!=` | Not equal to | `5 != 3` | `true` |
| `>` | Greater than | `8 > 5` | `true` |
| `<` | Less than | `3 < 7` | `true` |
| `>=` | Greater than or equal | `5 >= 5` | `true` |
| `<=` | Less than or equal | `4 <= 6` | `true` |

```dart
void main() {
  int x = 10;
  int y = 20;

  print(x == y);   // false
  print(x != y);   // true
  print(x > y);    // false
  print(x < y);    // true
  print(x >= 10);  // true
  print(y <= 20);  // true
}
```

---

#### C. Logical Operators

Combine multiple conditions together.

| Operator | Name | Meaning |
|----------|------|---------|
| `&&` | AND | True only if BOTH sides are true |
| `\|\|` | OR | True if AT LEAST ONE side is true |
| `!` | NOT | Flips true to false, false to true |

```dart
void main() {
  bool a = true;
  bool b = false;

  print(a && b);   // false — both must be true
  print(a || b);   // true  — at least one is true
  print(!a);       // false — flips true to false
  print(!b);       // true  — flips false to true

  int age = 22;
  bool hasID = true;
  bool canVote = age >= 18 && hasID;   // Both conditions must be met
  print(canVote);   // true
}
```

---

#### D. Assignment Operators

Assign or update values in variables.

| Operator | Example | Equivalent |
|----------|---------|------------|
| `=` | `x = 5` | Assign 5 to x |
| `+=` | `x += 3` | `x = x + 3` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 3` | `x = x * 3` |
| `/=` | `x /= 3` | `x = x / 3` |
| `%=` | `x %= 3` | `x = x % 3` |

```dart
void main() {
  int x = 10;

  x += 5;  print(x);   // 15
  x -= 3;  print(x);   // 12
  x *= 2;  print(x);   // 24
  x ~/= 4; print(x);   // 6
  x %= 4;  print(x);   // 2
}
```

---

#### E. Increment and Decrement Operators

| Operator | Name | Effect |
|----------|------|--------|
| `++x` | Pre-increment | Increment first, then use |
| `x++` | Post-increment | Use first, then increment |
| `--x` | Pre-decrement | Decrement first, then use |
| `x--` | Post-decrement | Use first, then decrement |

```dart
void main() {
  int a = 5;
  print(++a);  // 6  — incremented first, then printed
  print(a++);  // 6  — printed first, then incremented
  print(a);    // 7  — now it's 7

  int b = 10;
  print(--b);  // 9  — decremented first
  print(b--);  // 9  — printed first, then decremented
  print(b);    // 8
}
```

---

## 3.2 Control Flow Statements

**Control flow** determines the order in which statements in a program are executed.

Without control flow, every program would run from top to bottom in a straight line.
Control flow lets us:
- Make **decisions** (if/else)
- **Repeat** actions (loops)
- **Jump** to different parts (break, continue, return)

There are **three main categories:**
1. Decision-Making Statements
2. Looping Statements
3. Jump Statements

---

## 3.3 Decision-Making Statements

Decision-making statements let the program choose which block of code to run based on a condition.

---

### A. if Statement

Runs a block of code **only when the condition is true**.

**Syntax:**
```dart
if (condition) {
  // runs if condition is true
}
```

**Example:**
```dart
void main() {
  int marks = 75;

  if (marks >= 50) {
    print("You passed!");
  }
}
```

---

### B. if-else Statement

Runs one block when condition is true, another when false.

**Syntax:**
```dart
if (condition) {
  // runs when true
} else {
  // runs when false
}
```

**Example:**
```dart
void main() {
  int age = 16;

  if (age >= 18) {
    print("You can vote.");
  } else {
    print("You are too young to vote.");
  }
}
```

---

### C. if-else if-else (Ladder)

Checks multiple conditions one by one. Stops at the first true one.

**Syntax:**
```dart
if (condition1) {
  // runs if condition1 true
} else if (condition2) {
  // runs if condition2 true
} else if (condition3) {
  // runs if condition3 true
} else {
  // runs if all above are false
}
```

**Example:**
```dart
void main() {
  int marks = 72;

  if (marks >= 80) {
    print("Grade: A");
  } else if (marks >= 70) {
    print("Grade: B");
  } else if (marks >= 60) {
    print("Grade: C");
  } else if (marks >= 50) {
    print("Grade: D");
  } else {
    print("Grade: F — Fail");
  }
}
```
**Output:** `Grade: B`

---

### D. Nested if-else

An `if` inside another `if`. Used when one condition depends on another.

```dart
void main() {
  int age = 20;
  bool hasLicense = true;

  if (age >= 18) {
    if (hasLicense) {
      print("You can drive.");
    } else {
      print("You are old enough but need a license.");
    }
  } else {
    print("You are too young to drive.");
  }
}
```

---

### E. switch Statement

Compares one variable to multiple fixed values.
Cleaner than many if-else if blocks.

**Syntax:**
```dart
switch (variable) {
  case value1:
    // code
    break;
  case value2:
    // code
    break;
  default:
    // runs if no case matches
}
```

**Example:**
```dart
void main() {
  int day = 3;

  switch (day) {
    case 1:
      print("Monday");
      break;
    case 2:
      print("Tuesday");
      break;
    case 3:
      print("Wednesday");
      break;
    case 4:
      print("Thursday");
      break;
    case 5:
      print("Friday");
      break;
    case 6:
      print("Saturday");
      break;
    case 7:
      print("Sunday");
      break;
    default:
      print("Invalid day number");
  }
}
```
**Output:** `Wednesday`

---

### F. Ternary Operator

Short form of a simple if-else. Used when assigning a value based on a condition.

**Syntax:**
```dart
variable = condition ? valueIfTrue : valueIfFalse;
```

**Example:**
```dart
void main() {
  int age = 20;
  String result = age >= 18 ? "Adult" : "Minor";
  print(result);   // Adult

  int marks = 45;
  String status = marks >= 50 ? "Pass" : "Fail";
  print(status);   // Fail
}
```

---

##  EXAMPLES — Decision-Making Statements

---

**Example 1: Check Positive, Negative, or Zero**
```dart
void main() {
  int number = -7;

  if (number > 0) {
    print("$number is Positive");
  } else if (number < 0) {
    print("$number is Negative");
  } else {
    print("The number is Zero");
  }
}
```
**Output:** `-7 is Negative`

---

**Example 2: Voting Eligibility**
```dart
void main() {
  int age = 17;

  if (age >= 18) {
    print("You are eligible to vote.");
  } else {
    int remaining = 18 - age;
    print("You cannot vote yet. Wait $remaining more year(s).");
  }
}
```
**Output:** `You cannot vote yet. Wait 1 more year(s).`

---

**Example 3: Largest of Three Numbers**
```dart
void main() {
  int a = 45, b = 78, c = 62;

  if (a >= b && a >= c) {
    print("Largest is: $a");
  } else if (b >= a && b >= c) {
    print("Largest is: $b");
  } else {
    print("Largest is: $c");
  }
}
```
**Output:** `Largest is: 78`

---

**Example 4: Grade System using switch**
```dart
void main() {
  String grade = "B";

  switch (grade) {
    case "A":
      print("Excellent — 80% and above");
      break;
    case "B":
      print("Very Good — 70 to 79%");
      break;
    case "C":
      print("Good — 60 to 69%");
      break;
    case "D":
      print("Pass — 50 to 59%");
      break;
    case "F":
      print("Fail — Below 50%");
      break;
    default:
      print("Invalid Grade");
  }
}
```
**Output:** `Very Good — 70 to 79%`

---

**Example 5: Even or Odd**
```dart
void main() {
  int number = 14;
  String result = number % 2 == 0 ? "Even" : "Odd";
  print("$number is $result");
}
```
**Output:** `14 is Even`

---

**Example 6: Traffic Light System**
```dart
void main() {
  String light = "Red";

  switch (light) {
    case "Red":
      print("STOP — Do not cross");
      break;
    case "Yellow":
      print("SLOW DOWN — Prepare to stop");
      break;
    case "Green":
      print("GO — You may proceed");
      break;
    default:
      print("Unknown signal");
  }
}
```
**Output:** `STOP — Do not cross`

---

**Example 7: BMI Category**
```dart
void main() {
  double bmi = 27.5;

  if (bmi < 18.5) {
    print("Underweight");
  } else if (bmi < 25.0) {
    print("Normal weight");
  } else if (bmi < 30.0) {
    print("Overweight");
  } else {
    print("Obese");
  }
}
```
**Output:** `Overweight`

---

**Example 8: Login Check**
```dart
void main() {
  String username = "admin";
  String password = "1234";

  if (username == "admin" && password == "1234") {
    print("Login successful! Welcome.");
  } else if (username != "admin") {
    print("Username not found.");
  } else {
    print("Incorrect password.");
  }
}
```
**Output:** `Login successful! Welcome.`

---

**Example 9: Electricity Bill Slab**
```dart
void main() {
  int units = 350;
  double bill;

  if (units <= 100) {
    bill = units * 5.0;
  } else if (units <= 200) {
    bill = 100 * 5.0 + (units - 100) * 8.0;
  } else if (units <= 300) {
    bill = 100 * 5.0 + 100 * 8.0 + (units - 200) * 12.0;
  } else {
    bill = 100 * 5.0 + 100 * 8.0 + 100 * 12.0 + (units - 300) * 18.0;
  }

  print("Units used: $units");
  print("Total Bill: Rs. $bill");
}
```
**Output:**
```
Units used: 350
Total Bill: Rs. 3800.0
```

---

**Example 10: Day Type (Weekday or Weekend)**
```dart
void main() {
  String day = "Saturday";

  switch (day) {
    case "Saturday":
    case "Sunday":
      print("$day is a Weekend — Enjoy your day off!");
      break;
    case "Monday":
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
    case "Friday":
      print("$day is a Weekday — Time to work!");
      break;
    default:
      print("Invalid day entered.");
  }
}
```
**Output:** `Saturday is a Weekend — Enjoy your day off!`

---

## 3.4 Looping Statements

A **loop** repeats a block of code multiple times.
Instead of writing the same code 100 times, you write it once and tell the loop how many times to run it.

---

### A. for Loop

Use when you know **exactly how many times** to repeat.

**Syntax:**
```dart
for (initialization; condition; increment/decrement) {
  // code to repeat
}
```

**How it works:**
1. `initialization` — runs once at the start (e.g., `int i = 1`)
2. `condition` — checked before every iteration (e.g., `i <= 5`)
3. Code runs if condition is true
4. `increment` — runs after each iteration (e.g., `i++`)
5. Repeat from step 2

```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    print("Iteration: $i");
  }
}
```
**Output:**
```
Iteration: 1
Iteration: 2
Iteration: 3
Iteration: 4
Iteration: 5
```

---

### B. while Loop

Use when you **don't know** exactly how many times to repeat.
Checks the condition **before** running the code.

**Syntax:**
```dart
while (condition) {
  // code to repeat
  // must update variable to avoid infinite loop
}
```

```dart
void main() {
  int count = 1;

  while (count <= 5) {
    print("Count: $count");
    count++;   // IMPORTANT: without this, infinite loop
  }
}
```
**Output:**
```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

---

### C. do-while Loop

Runs the code **first**, then checks the condition.
Guarantees the loop body runs **at least once**.

**Syntax:**
```dart
do {
  // code runs first
} while (condition);  // then checks
```

```dart
void main() {
  int num = 10;

  do {
    print("Value: $num");
    num++;
  } while (num < 5);   // condition is false from start, but runs once
}
```
**Output:** `Value: 10`

---

### D. for-in Loop

Simplified loop for iterating through a **collection** (List, Set, etc.)

```dart
void main() {
  List<String> fruits = ["Apple", "Mango", "Banana", "Grapes"];

  for (String fruit in fruits) {
    print(fruit);
  }
}
```
**Output:**
```
Apple
Mango
Banana
Grapes
```

---

### Comparison of Loops

| Loop | Use When |
|------|----------|
| `for` | You know exact number of repetitions |
| `while` | You don't know how many times, check first |
| `do-while` | Must run at least once, check after |
| `for-in` | Looping through a List or collection |

---

##  10 EXAMPLES — Looping Statements

---

**Example 1: Print Numbers 1 to 10**
```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    print(i);
  }
}
```

---

**Example 2: Multiplication Table**
```dart
void main() {
  int num = 7;
  for (int i = 1; i <= 10; i++) {
    print("$num x $i = ${num * i}");
  }
}
```
**Output:**
```
7 x 1 = 7
7 x 2 = 14
...
7 x 10 = 70
```

---

**Example 3: Sum of Numbers 1 to 100**
```dart
void main() {
  int sum = 0;

  for (int i = 1; i <= 100; i++) {
    sum += i;   // sum = sum + i
  }

  print("Sum of 1 to 100 = $sum");
}
```
**Output:** `Sum of 1 to 100 = 5050`

---

**Example 4: Print Even Numbers from 1 to 20**
```dart
void main() {
  for (int i = 1; i <= 20; i++) {
    if (i % 2 == 0) {
      print(i);
    }
  }
}
```
**Output:** `2 4 6 8 10 12 14 16 18 20`

---

**Example 5: Countdown Timer using while**
```dart
void main() {
  int seconds = 10;

  while (seconds >= 0) {
    if (seconds == 0) {
      print("LAUNCH!");
    } else {
      print("$seconds...");
    }
    seconds--;
  }
}
```
**Output:**
```
10...
9...
...
1...
LAUNCH!
```

---

**Example 6: Factorial of a Number**
```dart
void main() {
  int number = 5;
  int factorial = 1;

  for (int i = 1; i <= number; i++) {
    factorial *= i;   // factorial = factorial * i
  }

  print("Factorial of $number = $factorial");
}
```
**Output:** `Factorial of 5 = 120`
> 5! = 5 × 4 × 3 × 2 × 1 = 120

---

**Example 7: Print Student Names from a List**
```dart
void main() {
  List<String> students = ["Ali", "Sara", "Ahmed", "Usman", "Hira"];

  print("Class Roll Call:");
  for (int i = 0; i < students.length; i++) {
    print("${i + 1}. ${students[i]}");
  }
}
```
**Output:**
```
Class Roll Call:
1. Ali
2. Sara
3. Ahmed
4. Usman
5. Hira
```

---

**Example 8: Reverse a Number using while**
```dart
void main() {
  int number = 12345;
  int reversed = 0;

  while (number > 0) {
    int digit = number % 10;    // Get last digit
    reversed = reversed * 10 + digit;
    number ~/= 10;              // Remove last digit
  }

  print("Reversed: $reversed");
}
```
**Output:** `Reversed: 54321`

---

**Example 9: do-while — Keep Asking Until Valid Input (Simulated)**
```dart
void main() {
  List<int> guesses = [0, -5, 150, 75];  // simulated inputs
  int index = 0;
  int input;

  do {
    input = guesses[index];
    print("Input entered: $input");
    index++;
  } while (input <= 0 || input > 100);

  print("Valid input accepted: $input");
}
```
**Output:**
```
Input entered: 0
Input entered: -5
Input entered: 150
Input entered: 75
Valid input accepted: 75
```

---

**Example 10: Star Pattern using Nested for Loop**
```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    String row = "";
    for (int j = 1; j <= i; j++) {
      row += "* ";
    }
    print(row);
  }
}
```
**Output:**
```
*
* *
* * *
* * * *
* * * * *
```

---

## 3.5 Jump Statements

**Jump statements** change the normal flow of a loop or function.
They allow you to exit early, skip an iteration, or leave a function.

---

### A. break Statement

**Immediately exits** the loop or switch block.
No more iterations run after `break`.

**Syntax:**
```dart
for (...) {
  if (condition) break;  // exits the loop
}
```

**Example:**
```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    if (i == 6) {
      print("Found 6! Stopping the loop.");
      break;   // exits immediately
    }
    print(i);
  }
  print("Loop ended.");
}
```
**Output:**
```
1
2
3
4
5
Found 6! Stopping the loop.
Loop ended.
```

---

### B. continue Statement

**Skips the current iteration** and jumps to the next one.
The loop does NOT exit — it continues from the next iteration.

**Syntax:**
```dart
for (...) {
  if (condition) continue;  // skip this iteration
  // rest of the code
}
```

**Example:**
```dart
void main() {
  for (int i = 1; i <= 8; i++) {
    if (i % 2 != 0) continue;  // skip odd numbers
    print(i);
  }
}
```
**Output:**
```
2
4
6
8
```

---

### C. return Statement

Exits a **function** immediately and optionally returns a value.
Can also be used to stop a loop inside a function.

```dart
int findFirst(List<int> numbers, int target) {
  for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] == target) {
      return i;   // exit function immediately with this value
    }
  }
  return -1;   // not found
}

void main() {
  List<int> nums = [5, 3, 8, 1, 9, 2];
  int index = findFirst(nums, 8);
  print("Found at index: $index");   // Found at index: 2
}
```

---

### break vs continue vs return

| Statement | What it does | Scope |
|-----------|-------------|-------|
| `break` | Exits the loop completely | Loop / switch |
| `continue` | Skips current iteration, continues loop | Loop only |
| `return` | Exits the entire function | Function |

---

## EXAMPLES — Jump Statements

---

**Example 1: break — Stop at First Negative Number**
```dart
void main() {
  List<int> numbers = [5, 10, 3, 8, -2, 7, 4];

  for (int num in numbers) {
    if (num < 0) {
      print("Negative number found: $num — stopping.");
      break;
    }
    print(num);
  }
}
```
**Output:**
```
5
10
3
8
Negative number found: -2 — stopping.
```

---

**Example 2: continue — Skip Multiples of 3**
```dart
void main() {
  print("Numbers from 1 to 15, skipping multiples of 3:");

  for (int i = 1; i <= 15; i++) {
    if (i % 3 == 0) continue;
    print(i);
  }
}
```
**Output:** `1 2 4 5 7 8 10 11 13 14`

---

**Example 3: break — Search in a List**
```dart
void main() {
  List<String> students = ["Ali", "Sara", "Ahmed", "Usman", "Hira"];
  String searchFor = "Ahmed";
  bool found = false;

  for (int i = 0; i < students.length; i++) {
    if (students[i] == searchFor) {
      print("$searchFor found at position ${i + 1}");
      found = true;
      break;
    }
  }

  if (!found) print("$searchFor not found.");
}
```
**Output:** `Ahmed found at position 3`

---

**Example 4: continue — Skip Failed Students**
```dart
void main() {
  Map<String, int> results = {
    "Ali": 78,
    "Sara": 42,
    "Ahmed": 88,
    "Usman": 35,
    "Hira": 65
  };

  print("Passed Students:");
  results.forEach((name, marks) {
    if (marks < 50) return;  // return acts as continue in forEach
    print("  $name — $marks marks");
  });
}
```
**Output:**
```
Passed Students:
  Ali — 78 marks
  Ahmed — 88 marks
  Hira — 65 marks
```

---

**Example 5: break in while Loop — Guess the Number**
```dart
void main() {
  int secret = 7;
  List<int> attempts = [2, 9, 4, 7, 1];  // simulated guesses

  for (int guess in attempts) {
    print("Guess: $guess");
    if (guess == secret) {
      print("Correct! You found the number.");
      break;
    } else {
      print("Wrong, try again.");
    }
  }
}
```

---

**Example 6: continue — Print Only Alphabets (skip digits)**
```dart
void main() {
  List<String> chars = ["a", "1", "b", "3", "c", "7", "d", "e"];

  print("Alphabets only:");
  for (String ch in chars) {
    if (int.tryParse(ch) != null) continue;  // skip if it's a number
    print(ch);
  }
}
```
**Output:** `a b c d e`

---

**Example 7: return — Validate Input**
```dart
bool isValidAge(int age) {
  if (age < 0) {
    print("Error: Age cannot be negative.");
    return false;
  }
  if (age > 120) {
    print("Error: Age seems unrealistic.");
    return false;
  }
  return true;
}

void main() {
  print(isValidAge(25));    // true
  print(isValidAge(-5));    // false
  print(isValidAge(150));   // false
}
```

---

**Example 8: break — ATM Withdrawal Attempt Limit**
```dart
void main() {
  int maxAttempts = 3;
  List<String> pins = ["1111", "2222", "1234"];  // 3rd one is correct
  String correctPin = "1234";

  for (int attempt = 1; attempt <= maxAttempts; attempt++) {
    String entered = pins[attempt - 1];
    print("Attempt $attempt: Entered $entered");

    if (entered == correctPin) {
      print("PIN correct. Access granted.");
      break;
    } else {
      if (attempt == maxAttempts) {
        print("Too many wrong attempts. Card blocked.");
      } else {
        print("Wrong PIN. Try again.");
      }
    }
  }
}
```
**Output:**
```
Attempt 1: Entered 1111
Wrong PIN. Try again.
Attempt 2: Entered 2222
Wrong PIN. Try again.
Attempt 3: Entered 1234
PIN correct. Access granted.
```

---

**Example 9: continue — Show Only Items in Stock**
```dart
void main() {
  Map<String, int> inventory = {
    "Pen": 50,
    "Notebook": 0,
    "Eraser": 30,
    "Ruler": 0,
    "Marker": 15,
  };

  print("Items In Stock:");
  inventory.forEach((item, qty) {
    if (qty == 0) return;  // skip out-of-stock items
    print("  $item — $qty units");
  });
}
```
**Output:**
```
Items In Stock:
  Pen — 50 units
  Eraser — 30 units
  Marker — 15 units
```

---

**Example 10: break + continue Combined**
```dart
void main() {
  print("Processing numbers 1 to 20:");
  print("Skip multiples of 4. Stop when total exceeds 30.\n");

  int total = 0;

  for (int i = 1; i <= 20; i++) {
    if (i % 4 == 0) {
      print("  Skipping $i");
      continue;
    }

    total += i;
    print("  Added $i — Running total: $total");

    if (total > 30) {
      print("\nTotal exceeded 30. Stopping.");
      break;
    }
  }

  print("Final total: $total");
}
```
**Output:**
```
Processing numbers 1 to 20:
Skip multiples of 4. Stop when total exceeds 30.

  Added 1 — Running total: 1
  Added 2 — Running total: 3
  Added 3 — Running total: 6
  Skipping 4
  Added 5 — Running total: 11
  Added 6 — Running total: 17
  Added 7 — Running total: 24
  Skipping 8
  Added 9 — Running total: 33

Total exceeded 30. Stopping.
Final total: 33
```
