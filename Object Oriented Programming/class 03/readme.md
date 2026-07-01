# Class 3: Inheritance in Dart

## What is Inheritance?

**Inheritance** means one class (the **child**/**subclass**) can inherit properties and methods from another class (the **parent**/**superclass**).

- Dart uses the `extends` keyword.
- The child class can use the parent's properties and methods, **and** add its own new ones.

### Basic Syntax

```dart
class Animal {
  void makeSound() {
    print("Animal makes sound");
  }
}

class Dog extends Animal {
  void bark() {
    print("Dog barks");
  }
}

void main() {
  Dog dog = Dog();
  dog.makeSound(); // Inherited from Animal
  dog.bark();      // Dog's own method
}
```

Here, the `Dog` class is using the `makeSound()` method from its parent class `Animal`, even though `makeSound()` is not defined inside `Dog` itself.

---

## The 4 Types of Inheritance in Dart

### 1. Single Inheritance

One child class inherits from **one** parent class.

```dart
class Vehicle {
  void move() => print("Moving...");
}

class Car extends Vehicle {
  void speed() => print("Speed is 100km/h");
}
```

Another example of the same concept:

```dart
class Animal {
  void eat() => print("Animal is eating");
}

class Dog extends Animal {
  void bark() => print("Dog is barking");
}

void main() {
  Dog d = Dog();
  d.eat();  // from Animal
  d.bark(); // own
}
```

---

### 2. Multilevel Inheritance

A class inherits from a class, which itself already inherited from another class.

```
Grandparent  --->  Parent  --->  Child
```

```dart
class LivingThing {
  void breathe() => print("Breathing...");
}

class Animal extends LivingThing {
  void walk() => print("Walking...");
}

class Dog extends Animal {
  void bark() => print("Barking...");
}

void main() {
  Dog d = Dog();
  d.breathe(); // from LivingThing
  d.walk();    // from Animal
  d.bark();    // own
}
```

---

### 3. Hierarchical Inheritance

**Multiple** classes inherit from the **same** base class.

```dart
class Shape {
  void draw() => print("Drawing shape...");
}

class Circle extends Shape {
  void radius() => print("Radius is 5");
}

class Square extends Shape {
  void side() => print("Side is 4");
}

void main() {
  Circle c = Circle();
  Square s = Square();

  c.draw();
  c.radius();

  s.draw();
  s.side();
}
```

---

### 4. Hybrid / Multiple Inheritance

Dart **does not** support multiple inheritance using `extends` (a class cannot extend more than one class directly).

However, Dart provides the `with` keyword to **mix in** behavior from multiple sources — this is done using **mixins**.

> We'll cover this in detail later using **interfaces** and **mixins**.
---

*End of Class 3*
