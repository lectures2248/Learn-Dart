# Project: Student Marksheet System

---
## Step 1: Create Variables

First create variables for Student Name, Student ID, and 5 subject marks.

```dart
String studentName;
String studentId;

int english;
int maths;
int science;
int computer;
int urdu;
```

---

## Step 2: Import Package

We need user input, so import `dart:io`.

```dart
import 'dart:io';
```

---

## Step 3: Take Student Name

```dart
print("Enter Student Name:");
String studentName = stdin.readLineSync()!;
```

**Example Input:**
```
Ali Ahmed
```

---

## Step 4: Take Student ID

```dart
print("Enter Student ID:");
String studentId = stdin.readLineSync()!;
```

**Example Input:**
```
STD101
```

---

## Step 5: Take English Marks

```dart
print("Enter English Marks:");
int english = int.parse(stdin.readLineSync()!);
```

---

## Step 6: Take Maths Marks

```dart
print("Enter Maths Marks:");
int maths = int.parse(stdin.readLineSync()!);
```

---

## Step 7: Take Science Marks

```dart
print("Enter Science Marks:");
int science = int.parse(stdin.readLineSync()!);
```

---

## Step 8: Take Computer Marks

```dart
print("Enter Computer Marks:");
int computer = int.parse(stdin.readLineSync()!);
```

---

## Step 9: Take Urdu Marks

```dart
print("Enter Urdu Marks:");
int urdu = int.parse(stdin.readLineSync()!);
```

---

## Step 10: Calculate Obtained Marks

**Formula:** Obtained Marks = Sum of all subject marks

```dart
int obtainedMarks =
    english +
    maths +
    science +
    computer +
    urdu;
```

**Example:**
```
80 + 90 + 75 + 85 + 70 = 400
```

---

## Step 11: Calculate Total Marks

Each subject = 100 marks, Total subjects = 5

```dart
int totalMarks = 500;
```

---

## Step 12: Calculate Percentage

**Formula:** Percentage = (Obtained Marks / Total Marks) × 100

```dart
double percentage = (obtainedMarks / totalMarks) * 100;
```

**Example:**
```
(400 / 500) * 100 = 80%
```

---

## Step 13: Calculate Grade

**Grade Rules:**

| Percentage | Grade |
|------------|-------|
| 90+        | A+    |
| 80+        | A     |
| 70+        | B     |
| 60+        | C     |
| 50+        | D     |
| Below 50   | Fail  |

```dart
String grade;

if (percentage >= 90) {
  grade = "A+";
} else if (percentage >= 80) {
  grade = "A";
} else if (percentage >= 70) {
  grade = "B";
} else if (percentage >= 60) {
  grade = "C";
} else if (percentage >= 50) {
  grade = "D";
} else {
  grade = "Fail";
}
```

---

## Step 14: Display Marksheet

```dart
print("===== MARKSHEET =====");

print("Student Name: $studentName");
print("Student ID: $studentId");

print("Obtained Marks: $obtainedMarks");
print("Total Marks: $totalMarks");

print("Percentage: $percentage");
print("Grade: $grade");
```

---

## Final Complete Program

```dart
import 'dart:io';

void main() {

  print("Enter Student Name:");
  String studentName = stdin.readLineSync()!;

  print("Enter Student ID:");
  String studentId = stdin.readLineSync()!;

  print("Enter English Marks:");
  int english = int.parse(stdin.readLineSync()!);

  print("Enter Maths Marks:");
  int maths = int.parse(stdin.readLineSync()!);

  print("Enter Science Marks:");
  int science = int.parse(stdin.readLineSync()!);

  print("Enter Computer Marks:");
  int computer = int.parse(stdin.readLineSync()!);

  print("Enter Urdu Marks:");
  int urdu = int.parse(stdin.readLineSync()!);

  int obtainedMarks =
      english +
      maths +
      science +
      computer +
      urdu;

  int totalMarks = 500;

  double percentage = (obtainedMarks / totalMarks) * 100;

  String grade;

  if (percentage >= 90) {
    grade = "A+";
  } else if (percentage >= 80) {
    grade = "A";
  } else if (percentage >= 70) {
    grade = "B";
  } else if (percentage >= 60) {
    grade = "C";
  } else if (percentage >= 50) {
    grade = "D";
  } else {
    grade = "Fail";
  }

  print("\n===== STUDENT MARKSHEET =====");

  print("Student Name: $studentName");
  print("Student ID: $studentId");

  print("Obtained Marks: $obtainedMarks");
  print("Total Marks: $totalMarks");

  print("Percentage: ${percentage.toStringAsFixed(2)}%");
  print("Grade: $grade");
}
```

---

## Sample Output

```
Enter Student Name:
Ali

Enter Student ID:
STD101

Enter English Marks:
80

Enter Maths Marks:
90

Enter Science Marks:
75

Enter Computer Marks:
85

Enter Urdu Marks:
70

===== STUDENT MARKSHEET =====

Student Name: Ali
Student ID: STD101

Obtained Marks: 400
Total Marks: 500

Percentage: 80.00%
Grade: A
```

---
