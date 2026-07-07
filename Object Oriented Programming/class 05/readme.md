# Dart OOP Lecture
### extends vs implements • and Mixins

---

## Part 1: extends vs implements

`extends` = you get real code from parent. You can change it if you want.

`implements` = you get no code. Just names of methods. You must write all of them yourself.

| | extends | implements |
|---|---|---|
| Code given? | Yes | No |
| Must write all methods? | No | Yes |
| How many at once? | Only 1 | Many |


### 2. Why implements needs all methods

Abstract class has no code inside. Only method names. So when you `implements` it, Dart gives you nothing. You must write real code for every method. If you miss one, code will not run.

### 3. Code Example — Admin

Three abstract classes below. `Admin` implements all three. So `Admin` must write all methods with real code.

```dart
abstract class Authentication {
  void register(String name, email, password);
  void login(String email, password);
}

abstract class FileManagement {
  String downloadFile();
  void uploadFile();
}

abstract class Report {
  String generateReport();
}

// interface
class Admin implements Authentication, FileManagement, Report {
  @override
  void register(String name, email, password) {
    // validateEmail(email);
    // validatePassword(password);
  }

  @override
  void login(String email, password) {
    print("Signing in with $email and $password");
  }

  @override
  String downloadFile() {
    print("Downloading file...");
    return "file_downloaded.pdf";
  }

  @override
  String generateReport() {
    print("Generating report...");
    return "report_generated.pdf";
  }

  @override
  void uploadFile() {
    print("Uploading file...");
  }
}
```

### 4. What we added

- `downloadFile()` — prints message, returns a String.
- `generateReport()` — prints message, returns a String.
- `uploadFile()` — prints message.

> Every method got real code. That is the rule of `implements`.

---

## Part 2: Mixins

### 1. What is a Mixin?

A mixin gives ready-made methods to any class. You use keyword `with`. No need to write the code again.

### 2. Why use mixin?

In Dart, a class can `extend` only 1 parent. But sometimes you need same helper methods in many different classes. Mixin solves this. You can add many mixins to one class.

### 3. Quick Compare

| | extends | implements | with (mixin) |
|---|---|---|---|
| Code given? | Yes | No | Yes |
| Must write all methods? | No | Yes | No |
| How many at once? | 1 | Many | Many |

### 4. Code Example — Validator Mixin

`Validator` mixin has 2 helper methods. Any class that adds `with Validator` gets these methods free.

```dart
mixin Validator {
  String? validateEmail(String email) {
    if (!email.contains("@") || !email.contains(".com")) {
      print("Invalid email format");
    } else {
      return email;
    }
  }

  String? validatePassword(String password) {
    if (password.length < 6 && password.length > 8) {
      print("should be between 6 to 8 digits");
    } else {
      return password;
    }
  }
}

class User with Validator implements Authentication {
  @override
  void register(String name, email, password) {
    validateEmail(email);
    validatePassword(password);
  }

  @override
  void login(String email, password) {
    print("Signing in with $email and $password");
  }
}
```

> `User` uses `with Validator` (free methods) + `implements Authentication` (must write register/login). Both together — very common.

### 5. Same Idea Again — Staff Class

Same pattern, new class. `Staff` uses `with Validator` for free methods, and `implements Authentication` for its own login/register.

```dart
class Staff with Validator implements Authentication {
  @override
  void register(String name, email, password) {
    validateEmail(email);
    validatePassword(password);
    print("Staff account created for $name");
  }

  @override
  void login(String email, password) {
    validateEmail(email);
    print("Staff signing in with $email");
  }
}

void main() {
  Staff staff = Staff();
  staff.register("Ali", "ali@example.com", "abcdef");
  staff.login("ali@example.com", "abcdef");
}
```
- `with` (mixin) — free ready-made methods, add many at once.
- One class can use `with` + `implements` together.
