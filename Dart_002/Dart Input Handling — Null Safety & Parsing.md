# Dart Input Handling — Null Safety & Parsing
---

## Problem Kya Thi

Humne yeh code likha tha:

```dart
int num_one = int.parse(stdin.readLineSync() ?? "0");
```

Dekhne mein theek lagta hai na? Lekin crash ho gaya. Batata hoon kyun.

---

## `stdin.readLineSync()` kya karta hai?

Jo bhi user terminal mein type kare, woh read karta hai.

Return type hai `String?` — woh question mark matlab yeh null bhi de sakta hai.

```dart
String? input = stdin.readLineSync();
```

---

## `??` Operator

Isko null-coalescing operator kehte hain. Simple rule:

> agar left side null ho — right side use karo

```dart
String input = stdin.readLineSync() ?? "0";

// readLineSync null de  →  "0" milega
// readLineSync "5" de   →  "5" milega
```

---

## Toh Phir Crash Kyun Hua?

Kyunke jab user bina kuch type kiye Enter dabata hai, `readLineSync()` null nahi deta.

Woh deta hai **empty string** — yani `""`

Aur `?? "0"` sirf null pe trigger hota hai. Empty string null nahi hoti.

Toh ultimately yeh ho gaya:

```dart
int.parse("")   // crash — empty string koi number thodi hai
```

Yahi asli masla tha.

---

## `parse` vs `tryParse` — Farq Kya Hai

Bas yeh yaad rakhna:

| | `parse` | `tryParse` |
|---|---|---|
| Sahi input (jaise "5") | 5 return karta hai | 5 return karta hai |
| Galat input (jaise "") | **crash** | null return karta hai |

`tryParse` safe option hai. Jab bhi user se input lo, yahi use karo.

---

## Sahi Wala Code

```dart
import 'dart:io';

void main() {
  stdout.write("Enter number one: ");
  String input1 = stdin.readLineSync() ?? "0";
  int num_one = int.tryParse(input1) ?? 0;

  stdout.write("Enter number two: ");
  String input2 = stdin.readLineSync() ?? "0";
  int num_two = int.tryParse(input2) ?? 0;

  print(num_one + num_two);
}
```

Double `??` dhyan se dekho — pehla wala `readLineSync` ka null handle karta hai, doosra wala `tryParse` ka null handle karta hai agar input galat tha.

---
