# Class 2: Classes, Objects & Constructors — Practical

## Quick Recap

- A **class** has two main things:
  - **Properties** (also called fields/attributes) → the things the object *has*, they hold data or values.
  - **Methods** (also called functions) → the things the object *can do*, they hold actions/behavior.

Now let's put this into practice with real Dart code.

---

## Practical Examples of Class & Object

### Example 1: Car

```dart
class Car {
  String brand = "";
  int speed = 0;

  void showInfo() {
    print("Brand: $brand, Speed: $speed km/h");
  }
}

void main() {
  Car car1 = Car();
  car1.brand = "Toyota";
  car1.speed = 180;
  car1.showInfo();
}
```

---

### Example 2: Person

```dart
class Person {
  String name = "";
  int age = 0;

  void introduce() {
    print("Hi, I'm $name and I'm $age years old.");
  }
}

void main() {
  Person p = Person();
  p.name = "Ali";
  p.age = 25;
  p.introduce();
}
```

---

### Example 3: BankAccount

```dart
class BankAccount {
  String accountHolder = "";
  double balance = 0;

  void deposit(double amount) {
    balance += amount;
    print("Deposited \$${amount}. New Balance: \$${balance}");
  }
}

void main() {
  BankAccount account = BankAccount();
  account.accountHolder = "Sara";
  account.deposit(1000);
}
```

---

## What is a Constructor?

A **constructor** is a special method that is called automatically when you create an object.

It helps you set the **initial values** of the properties — instead of assigning them one by one after creating the object (like we did above with `car1.brand = "Toyota"`).

### Constructor Example (Positional Parameters)

```dart
class Student {
  String name;
  int age;

  // Constructor
  Student(this.name, this.age);

  void show() => print("Name: $name, Age: $age");
}

void main() {
  Student s = Student("Ali", 20);
  s.show();
}
```

### Constructor Example (Named Parameters)

```dart
class Student {
  String name;
  int age;

  // Constructor with only named parameters
  Student({required this.name, required this.age});

  void show() => print("Name: $name, Age: $age");
}

void main() {
  Student s = Student(name: "Sara", age: 25);
  s.show();
}
```
---

*End of Class 2*
