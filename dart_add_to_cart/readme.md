# Dart Lecture — Add to Cart Program

---

## Step 1 — Import dart:io

```dart
import 'dart:io';
```

**Why?**
We need to take **input from the user** (keyboard).
`dart:io` gives us access to `stdin` which reads what the user types.

---

## Step 2 — Product List

```dart
final products = [
  {'id': 1, 'name': 'Apple iPhone', 'price': 999.99},
  {'id': 2, 'name': 'Samsung Galaxy', 'price': 899.99},
  {'id': 3, 'name': 'Google Pixel', 'price': 799.99},
  {'id': 4, 'name': 'OnePlus Nord', 'price': 499.99},
];
```

**What is this?**
- This is a **List** of products
- Each product is a **Map** (like a dictionary) with 3 keys: `id`, `name`, `price`
- `final` means this list will not be changed

Think of it like a table:

| id | name           | price  |
|----|----------------|--------|
| 1  | Apple iPhone   | 999.99 |
| 2  | Samsung Galaxy | 899.99 |
| 3  | Google Pixel   | 799.99 |
| 4  | OnePlus Nord   | 499.99 |

---

## Step 3 — Cart List

```dart
List<Map<String, dynamic>> cartItems = [];
```

**What is this?**
- `cartItems` is an **empty list** at the start
- It will store the products the user adds
- `Map<String, dynamic>` means each item has a key (String) and value (any type)

Think of it like an **empty shopping trolley** — items will be added later.

---

## Step 4 — show_product() Function

```dart
void show_product() {
  print('=== Products ===');
  for (var product in products) {
    print('ID: ${product['id']}  Name: ${product['name']}  Price: ${product['price']}');
  }
  print('');
}
```

**What is this?**
- It loops through every product in the list
- Prints the ID, Name, and Price of each product
- Simple `for` loop — nothing complicated

**Output will look like:**
```
=== Products ===
ID: 1  Name: Apple iPhone  Price: 999.99
ID: 2  Name: Samsung Galaxy  Price: 899.99
ID: 3  Name: Google Pixel  Price: 799.99
ID: 4  Name: OnePlus Nord  Price: 499.99
```

---

## Step 5 — add_to_cart() Function

This is the **most important function**. Let's go step by step.

```dart
void add_to_cart(int product_id) {

  var found_product = products.firstWhere((product) => product['id'] == product_id);

  int index = cartItems.indexWhere((item) => item['id'] == product_id);

  if (index >= 0) {
    cartItems[index]['quantity'] = cartItems[index]['quantity'] + 1;
    print('Quantity increased for: ${cartItems[index]['name']}');
  } else {
    cartItems.add({
      'id': found_product['id'],
      'name': found_product['name'],
      'price': found_product['price'],
      'quantity': 1,
    });
    print('Added to cart: ${found_product['name']}');
  }
}
```

---

## Very Important — firstWhere

### What is firstWhere?

`firstWhere` searches a list and **returns the first item** that matches your condition.

### Simple Example:

```dart
var numbers = [10, 20, 30, 40];

var result = numbers.firstWhere((n) => n == 30);

print(result); // Output: 30
```

It goes through the list one by one and stops when it finds the match.

### In Our Program:

```dart
var found_product = products.firstWhere((product) => product['id'] == product_id);
```

**Reading it in plain English:**
> "Search in `products` list. Find the first product where `id` matches `product_id`. Save it in `found_product`."

**Example:**
- User types `2`
- `firstWhere` searches the list
- Finds `{'id': 2, 'name': 'Samsung Galaxy', 'price': 899.99}`
- Saves it in `found_product`

### When to use firstWhere?
Use `firstWhere` when you want to **find and get the actual item** from a list.

---

## Very Important — indexWhere

### What is indexWhere?

`indexWhere` searches a list and **returns the position (index number)** of the first item that matches your condition.

- If item is **found** → returns the index number (0, 1, 2, ...)
- If item is **not found** → returns **-1**

### Simple Example:

```dart
var names = ['Ali', 'Sara', 'Usman'];

int index = names.indexWhere((name) => name == 'Sara');

print(index); // Output: 1  (Sara is at position 1)
```

```dart
int index = names.indexWhere((name) => name == 'Zara');

print(index); // Output: -1  (Zara not found)
```

### In Our Program:

```dart
int index = cartItems.indexWhere((item) => item['id'] == product_id);
```

**Reading it in plain English:**
> "Search in `cartItems` list. Find the position of the item where `id` matches `product_id`. Save that position in `index`."

**Example:**
- Cart has iPhone (id: 1) at position 0
- User types `1` again
- `indexWhere` returns `0`
- `index >= 0` is true → quantity increases

- User types `3` (Google Pixel, not in cart yet)
- `indexWhere` returns `-1`
- `index >= 0` is false → goes to `else` → adds new item

### When to use indexWhere?
Use `indexWhere` when you want to **check if an item exists** and also **know its position** so you can update it.

---

## Step 6 — show_cart() Function

```dart
void show_cart() {
  print('');
  print('=== Your Cart ===');
  for (var item in cartItems) {
    print('Name: ${item['name']}  Quantity: ${item['quantity']}  Price: ${item['price']}');
  }
}
```

**What is this?**
- Loops through `cartItems` list
- Prints name, quantity and price of each item

**Output Example:**
```
=== Your Cart ===
Name: Apple iPhone  Quantity: 2  Price: 999.99
Name: Google Pixel  Quantity: 1  Price: 799.99
```

---

## Step 7 — main() Function

Ab jab humne saare functions samajh liye hain, ab `main()` dekhte hain.
`main()` sirf un functions ko **call** karta hai jo humne upar banaye hain.

```dart
void main() {
  show_product();

  while (true) {
    print('Enter product ID to add to cart (0 to stop):');
    int id = int.parse(stdin.readLineSync()!);

    if (id == 0) {
      break;
    }

    add_to_cart(id);
  }

  show_cart();
}
```
