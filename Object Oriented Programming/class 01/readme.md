# Class 1: Introduction to OOP (Object-Oriented Programming)

## What is OOP?

> "OOP (Object-Oriented Programming) is a way of writing code that is based on the idea of objects."

An **object** represents a real-world thing — like a car, a person, or a mobile phone.

Every object has:

- **Properties** (also called *fields* or *attributes*) → things it **has**
- **Behaviors** (also called *methods*/*functions*) → things it **can do**

---

## Why OOP? (The Problem with Traditional Code)

Before OOP, in **procedural programming**, code was written as one big list of instructions.

**Problems with that approach:**

- Difficult to manage large codebases
- Repeated code everywhere
- Hard to find and fix bugs
- No clear structure for representing real-world objects

**OOP solves this by:**

- Grouping related data and actions together
- Making code reusable using classes
- Organizing code into smaller, understandable parts
- Making apps easier to build and maintain

---

## The Basic Building Blocks of OOP

1. **Class**
2. **Object**

### What is a Class?

A **class** is like a blueprint, template, or design for creating objects.

It defines:

- What an object **will have** (properties)
- What an object **can do** (methods)

A class by itself does not represent anything real — it's just a design.

**Real-Life Analogy #1 — House Blueprint:**
Think of a class as a house blueprint (a 2D or 3D design). It shows where the walls, doors, and windows will be. But you can't *live* in a blueprint — you must build an actual house from it. That's where the **object** comes in.

**Real-Life Analogy #2 — Car Model:**
Imagine Toyota wants to design a new GLI model. First, they create a **blueprint** — an idea of how it will look and what features it will have. At this stage, the car doesn't exist in the real world yet; it's just a design (the **class**).
Once the design is finalized, Toyota can manufacture as many actual cars from that blueprint as they want — each one is an **object**.

### What is an Object?

An **object** is a real thing created from a class.

- It has actual values.
- You can create many objects from one class.

**Real-Life Analogy:**
Some housing societies use the same design, same color, and same style for many houses. The idea is that we create **one map (class)**, and using that map we build **multiple houses (objects)**.

### Summary

| Concept | Meaning |
|---|---|
| **Class** | Blueprint |
| **Object** | Actual thing built from the blueprint |

**Important:** A class is only a blueprint or template — it does **not** occupy any space in memory by itself. However, when you create an object from that class, it becomes a real **instance** and *does* use memory to store its data and behavior.

---

## Example: Student Management System

Suppose we're writing a program for a school.

### Without OOP

You'd need separate variables for every student:

```dart
String student1Name = "Ali";
int student1Age = 18;

String student2Name = "Sara";
int student2Age = 20;
// and so on...
```

If you wanted to print student details, you'd need to write separate print statements/functions for each student. This doesn't scale.

### With OOP

You create a `Student` class **once**, and then create as many student objects as you need.

```dart
class Student {
  String name;
  int age;

  void displayInfo() {
    print("Name: $name, Age: $age");
  }
}
```

Now you can do this:

```dart
void main() {
  Student student1 = Student();
  student1.name = "Ali";
  student1.age = 18;

  Student student2 = Student();
  student2.name = "Sara";
  student2.age = 20;

  student1.displayInfo();
  student2.displayInfo();
}
```

---

## Pillars of OOP (Core Principles)

| Pillar | Meaning |
|---|---|
| **Encapsulation** | Binding data and methods together (hiding internal details) |
| **Inheritance** | Reusing code using parent-child relationships |
| **Polymorphism** | Performing the same action in different ways |
| **Abstraction** | Hiding complex logic and showing only the essentials |
---

*End of Class 1*
