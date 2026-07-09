# Dart Programming Lecture: Synchronous and Asynchronous Programming

---

## 1. Synchronous Programming

**Definition:**
> Synchronous programming in Dart is the traditional way of executing code, where each task is performed one after the other in a sequential and blocking manner.

In synchronous code, the program waits for each operation to complete before moving on to the next one.

**Real-Life Example:**
Waiting in a queue at a single checkout counter, where each customer is served one after the other.

**Programming Example:**

```dart
import 'dart:io';

void main() {
  print("Enter your birth place :");
  String? birthplace = stdin.readLineSync();
  print("Your birthplace is ${birthplace}");
}
```

---

## 2. Asynchronous Programming

**Definition:**
> Asynchronous programming in Dart allows you to perform tasks concurrently, without blocking the main thread.

In asynchronous code, the program doesn't wait for each operation to complete before moving on to the next one. Instead, it allows other tasks to continue while waiting for asynchronous operations to finish.

**Real-Life Example:**
Multiple customers shopping in a supermarket with multiple checkout counters open simultaneously, allowing them to proceed independently without waiting for others.

**Programming Example:**

```dart
void main() {
  print('Start of program');

  doTask1();
  doTask2();
  doTask3();
}

void doTask1() {
  print('Task 1');
}

void doTask2() {
  Future.delayed(Duration(seconds: 2), () {
    print('Task 2 (Delayed)');
  });
}

void doTask3() {
  print('Task 3');
}
```

---

## 3. What is a Future?

> Future in Dart can be referred to as a real-life promise — you keep the promise, or you break it.

In Dart, a `Future` may give you some valid response (the promise is kept), or you may get an error (the promise is broken).

---

## 4. What is Async / Await, and What is Their Use?

When we call Future functions, we naturally want to perform some actions on the data that will be received from those Future functions. This could involve calling another Future function, and then another after that — soon the code becomes unmanageable and messy.

For this purpose, we use `async` and `await`. By using these, we tell Dart to wait and not move further until the response is received from the Future function.

**Technically, we make an asynchronous function behave like a synchronous function.**

**Programming Example:**

```dart
void main() async {
  print('Start of program');

  doTask1();
  await doTask2();
  doTask3();

  print('End of program');
}

void doTask1() {
  print('Task 1');
}

Future<void> doTask2() async {
  await Future.delayed(Duration(seconds: 2));
  print('Task 2 (Delayed)');
}

void doTask3() {
  print('Task 3');
}
```

---

*End of Lecture*
