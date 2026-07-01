# Abstraction in Dart 

## What is Abstraction?

**Abstraction** means: **hide the complicated stuff, show only the important stuff.**

That's it. That's the whole idea.

You just show the user **what** something does, not **how** it does it.

---

## Real-Life Example

### TV Remote

When you press the power button on a TV remote:

- You just press **one button**
- TV turns ON

You don't see:
- The circuit inside
- The signal sent to the TV
- How the TV processes that signal

All that complex stuff is **hidden**. You only see the **button** (the essential part). That's abstraction.

### Another Example — Bike

To ride a bike, you just:
- Pedal
- Use the brake
- Turn the handle

You don't need to know how the chain, gears, and brake pads work internally. It's **hidden** from you.

---

## Why Do We Use Abstraction?

- Keeps things **simple** for the user
- Hides messy/complex code
- If we change internal logic later, the user won't even notice — because they never saw it in the first place

---

## How Do We Do Abstraction in Dart?

We use:

1. **Abstract class**
2. **Abstract method**

---

## Abstract Class

An abstract class is a class that:

- We **cannot** create an object of directly
- Is only meant to be **extended** by other classes

We write `abstract` before `class`.

```dart
abstract class Shape {
  void draw(); // no body — this is abstract method
}
```

 If you try this:

```dart
Shape s = Shape(); //  ERROR
```

Dart will not allow it, because `Shape` is abstract.

---

## Abstract Method

An abstract method is a method with **no body**.

```dart
void draw(); // just this, no { }
```

Rule: **abstract method must be inside abstract class.**

Any class that extends this abstract class **must** give the actual code (body) for that method.

---

## Full Simple Example

```dart
abstract class Shape {
  void draw(); // abstract method, no body
}

class Circle extends Shape {
  @override
  void draw() {
    print("Drawing a Circle");
  }
}

class Square extends Shape {
  @override
  void draw() {
    print("Drawing a Square");
  }
}

void main() {
  Circle c = Circle();
  Square s = Square();

  c.draw(); // Drawing a Circle
  s.draw(); // Drawing a Square
}
```

**What's happening:**

- `Shape` says: "Every shape must have a `draw()` method" — but doesn't say how.
- `Circle` and `Square` each write their **own version** of `draw()`.
- This way, every shape is forced to have a `draw()`, but each one can draw differently.

---

## Abstract Class Can Also Have Normal Methods

Abstract class is not *only* abstract methods. It can have normal methods too (with body).

```dart
abstract class Animal {
  void eat() {
    print("Animal is eating"); // normal method, has body
  }

  void makeSound(); // abstract method, no body
}

class Dog extends Animal {
  @override
  void makeSound() {
    print("Dog says Woof!");
  }
}

void main() {
  Dog d = Dog();
  d.eat();       // inherited, ready-made
  d.makeSound(); // Dog says Woof!
}
```

So:
- `eat()` → already written, every animal uses same code
- `makeSound()` → every animal must write their own, because dog barks, cat meows, cow moos — all different

---

*End of Lecture*
