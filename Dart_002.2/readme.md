# Dart — Operators & If-Else Statements

---

## What We Will Learn?

1. What are Operators?
2. Types of Operators in Dart
3. Comparison Operators
4. If Statement
5. If-Else Statement
6. Else-If Statement

---

## 1. What are Operators?

Operators are special symbols that perform operations on values and variables.

**Example:**

```dart
int a = 10;
int b = 5;

print(a + b);
```

**Output:**
```
15
```

Here, `+` is an operator.

---

## 2. Types of Operators in Dart

1. Arithmetic Operators
2. Comparison Operators
3. Logical Operators
4. Assignment Operators

> We will focus on **Arithmetic** and **Comparison** Operators.

---

### Arithmetic Operators

Used for mathematical calculations.

| Operator | Meaning        |
|----------|----------------|
| `+`      | Addition       |
| `-`      | Subtraction    |
| `*`      | Multiplication |
| `/`      | Division       |
| `%`      | Modulus        |

**Example:**

```dart
void main() {
  int a = 10;
  int b = 3;

  print(a + b);
  print(a - b);
  print(a * b);
  print(a / b);
  print(a % b);
}
```

**Output:**
```
13
7
30
3.3333333333333335
1
```

---

## 3. Comparison Operators

Comparison operators compare two values.

They always return: **`true`** or **`false`**

| Operator | Meaning                |
|----------|------------------------|
| `==`     | Equal to               |
| `!=`     | Not Equal to           |
| `>`      | Greater Than           |
| `<`      | Less Than              |
| `>=`     | Greater Than or Equal  |
| `<=`     | Less Than or Equal     |

**Example:**

```dart
void main() {
  print(10 > 5);
  print(10 < 5);
  print(10 == 10);
  print(10 != 5);
}
```

**Output:**
```
true
false
true
true
```

---

## 4. If Statement

The `if` statement executes code **only when a condition is true**.

**Syntax:**

```dart
if (condition) {
  // code
}
```

**Example:**

```dart
void main() {
  int age = 20;

  if (age >= 18) {
    print("You can vote");
  }
}
```

**Output:**
```
You can vote
```

---

## 5. If-Else Statement

`if-else` is used when we have **two possible outcomes**.

**Syntax:**

```dart
if (condition) {
  // code
} else {
  // code
}
```

**Example:**

```dart
void main() {
  int age = 15;

  if (age >= 18) {
    print("You can vote");
  } else {
    print("You cannot vote");
  }
}
```

**Output:**
```
You cannot vote
```

---

### Comparison Operators with If-Else

**Example 1:**

```dart
void main() {
  int num = 10;

  if (num == 10) {
    print("Number is 10");
  } else {
    print("Number is not 10");
  }
}
```

**Output:**
```
Number is 10
```

---

**Example 2:**

```dart
void main() {
  int marks = 40;

  if (marks >= 50) {
    print("Pass");
  } else {
    print("Fail");
  }
}
```

**Output:**
```
Fail
```

---

## 6. Else-If Statement

`else-if` is used when we have **multiple conditions**.

**Syntax:**

```dart
if (condition1) {
  // code
} else if (condition2) {
  // code
} else {
  // code
}
```

**Example:**

```dart
void main() {
  int marks = 75;

  if (marks >= 80) {
    print("Grade A");
  } else if (marks >= 60) {
    print("Grade B");
  } else {
    print("Grade C");
  }
}
```

**Output:**
```
Grade B
```

---

## Class Activity

Create a program that:

1. Stores a number.
2. Checks whether the number is **positive** or **negative**.
3. Displays the result using `if-else`.

**Expected Output:**
```
Number is Positive
```
