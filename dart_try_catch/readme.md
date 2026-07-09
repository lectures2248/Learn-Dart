# Dart Programming Lecture: Try-Catch Exception Handling

---

## 1. What is Try-Catch?

Try-catch is used to handle runtime errors so that your program does not crash.

**Simple idea:**
> "Try to run this code. If something goes wrong, catch the error."

---

## 2. Basic Syntax

```dart
try {
  // risky code
} catch (e) {
  // handle error
}
```

**Example — Without try-catch:**

```dart
import 'dart:io';

void main() {
  stdout.write("Enter your age: ");
  
  int age = int.parse(stdin.readLineSync()!);

  print("Your age is: $age");
}
```

**Example — With try-catch:**

```dart
import 'dart:io';

void main() {
  stdout.write("Enter your age: ");

  try {
    int age = int.parse(stdin.readLineSync()!);
    print("Your age is: $age");
  } catch (e) {
    print("Invalid input! Please enter a number.");
  }
}
```

---

## 3. Why Not Just Let It Crash?

If your app crashes:
- User experience becomes bad
- App looks unprofessional
- Data may be lost

**So we HANDLE errors instead of ignoring them.**

---

## 4. Catching the Actual Error Message

```dart
void main() {
  try {
    int num = int.parse("abc");
  } catch (e) {
    print("Error is: $e");
  }
}
```

---

## 5. Using Stack Trace (Advanced)

```dart
try {
  // code
} catch (e, s) {
  print(e);
  print(s);
}
```

**Explanation:**
- `e` = error
- `s` = stack trace (where the error happened)

Mostly used in debugging.

---

## 6. Multiple Error Handling

```dart
void main() {
  try {
    List<int> list = [1, 2, 3];
    print(list[5]);
  } on RangeError {
    print("Index issue");
  } catch (e) {
    print("Other error: $e");
  }
}
```

**Explanation:**
- `RangeError` is handled separately
- Other errors go to the general `catch` block

---

## 7. Finally Block

The `finally` block always runs — no matter what happens.

```dart
void main() {
  try {
    int result = 10 ~/ 0;
  } catch (e) {
    print("Error occurred");
  } finally {
    print("Program finished");
  }
}
```

**Use cases:**
- Closing a file
- Closing a database connection
- Cleanup work

---

## 8. Custom Exception

```dart
class InvalidPasswordException implements Exception {
  String message;
  InvalidPasswordException(this.message);

  @override
  String toString() {
    return message;
  }
}

void login(String password) {
  if (password.length < 6) {
    throw InvalidPasswordException("Password too short");
  }
  print("Login successful");
}
```

---

## 9. Applied Example: ATM Withdrawal

```dart
void withdraw(int balance, int amount) {
  if (amount > balance) {
    throw Exception("Insufficient balance");
  }
  print("Withdraw successful");
}

void main() {
  try {
    withdraw(5000, 7000);
  } catch (e) {
    print("Transaction failed: $e");
  } finally {
    print("Thank you for using ATM");
  }
}
```

---

*End of Lecture*
