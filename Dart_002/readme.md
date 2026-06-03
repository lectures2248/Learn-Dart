# Dart — User Input & Type Conversion

---

## What We Will Learn?

1. User Input
2. Type Conversion

---

## 1. User Input in Dart

To take input from the user, we use:

```
stdin.readLineSync()
```

Before using it, **import `dart:io` package**.

### Example

```dart
import 'dart:io';

void main() {
  print("Enter your name:");
  String? name = stdin.readLineSync();
  print("Welcome, $name");
}
```

**Output:**
```
Enter your name:
Ali
Welcome, Ali
```

**Explanation:**
- `stdin.readLineSync()` takes input from the keyboard.
- User input is stored in a variable.
- Input is always received as a **String**.

---

### Example: Age Input

```dart
import 'dart:io';

void main() {
  print("Enter your age:");
  String? age = stdin.readLineSync();
  print("Your age is $age");
}
```

**Output:**
```
Enter your age:
20
Your age is 20
```

---

## 2. Type Conversion

Sometimes user input is received as a **String**.  
To perform calculations, we convert it into another data type.  
This process is called **Type Conversion**.

---

### String → Int

```dart
import 'dart:io';

void main() {
  print("Enter a number:");
  String? num = stdin.readLineSync();
  int number = int.parse(num!);
  print(number + 10);
}
```

**Output:**
```
Enter a number:
5
15
```

**Explanation:**
- User enters `"5"` → it is a String.
- `int.parse()` converts it to an integer.
- Now Dart can perform calculations.

---

### String → Double

```dart
import 'dart:io';

void main() {
  print("Enter your height:");
  String? height = stdin.readLineSync();
  double h = double.parse(height!);
  print(h);
}
```

**Output:**
```
Enter your height:
5.8
5.8
```

---

### Int → String

```dart
void main() {
  int age = 20;
  String ageText = age.toString();
  print(ageText);
}
```

**Output:**
```
20
```

---

## Practical Example

Create a program that **adds two numbers entered by the user**.

```dart
import 'dart:io';

void main() {
  print("Enter first number:");
  int num1 = int.parse(stdin.readLineSync()!);

  print("Enter second number:");
  int num2 = int.parse(stdin.readLineSync()!);

  int sum = num1 + num2;
  print("Sum = $sum");
}
```

**Output:**
```
Enter first number:
10
Enter second number:
20
Sum = 30
```

---
