
---

### 🧼 What is a Pure Function?

A **pure function** is a function that meets **two main criteria**:

#### ✅ 1. **Same Input → Same Output**

* No matter how many times you call the function with the same input, it will always return the **same output**.

  ```python
  def multiply_by_two(lst):
      new_list = []
      for item in lst:
          new_list.append(item * 2)
      return new_list
  ```

  * `multiply_by_two([1, 2, 3])` → always returns `[2, 4, 6]`

#### 🚫 2. **No Side Effects**

* A **side effect** is when a function:

  * Modifies global variables
  * Prints to the screen
  * Reads/writes to files or databases
  * Interacts with outside state

* Example of side effects:

  ```python
  print("Hello")              # Affects the screen
  some_global_list.append(1)  # Modifies external variable
  ```

---

### 💥 Why Avoid Side Effects?

* Code becomes **predictable**, **easier to test**, and **less buggy**
* You **reduce dependencies** on the external world
* Pure functions **don’t rely on external state**, so they are easier to reuse and debug

---

### ⚠️ When a Function is Not Pure

Example:

```python
new_list = []

def multiply_by_two(lst):
    for item in lst:
        new_list.append(item * 2)
```

* This function depends on an **external variable (`new_list`)**
* It’s **not pure** — any external change to `new_list` could break the function

---

### 🧠 Why Does This Matter?

* Pure functions allow:

  * Clean, modular code
  * Easier debugging and testing
  * Reduced chances of bugs from shared state

But remember:

> **Pure functions are a guideline, not a rule.**

* Sometimes side effects are **necessary** — e.g., displaying output, saving files, etc.
* But the **fewer side effects** you have, the better your codebase will be

---

### 💡 Functional Programming Philosophy

* Keep **data** and **functions** separate
* Prefer **pure functions** to reduce interdependencies
* Only a few functions should interact with the “outside world”

Example (Functional Style):

```python
wizard = {'name': 'Merlin', 'power': 50}

def attack(wizard):
    return f"{wizard['name']} attacks with power {wizard['power']}"
```

No need to wrap everything in classes if simple functions will do.

---


Great! Let’s break this down into **clear notes** based on your script, focusing on **Map** and its role in **functional programming in Python**:

---

### 📘 **Functional Programming: Built-in Functions in Python**

Python offers built-in functions that align with **functional programming** principles. The key ones are:

* `map()`
* `filter()`
* `zip()`
* `reduce()` (from `functools`)

---

### 🧠 **Understanding `map()`**

#### 🔹 Purpose:

To **apply a function to each item in an iterable** (e.g., a list), returning a new iterable (a `map` object).

---

### ✅ **Syntax:**

```python
map(function, iterable)
```

* `function`: A function to apply
* `iterable`: A list or other iterable to transform

---

### 🧪 **Example: Multiply List Items by 2**

```python
def multiply_by_2(item):
    return item * 2

print(list(map(multiply_by_2, [1, 2, 3])))  # Output: [2, 4, 6]
```

#### Key Points:

* `map()` **calls the function automatically** on each element.
* It returns a **map object**, so we must wrap it in `list()` to view the results.

---

### 📌 **Pure Function Compatibility**

#### A function is considered *pure* if:

1. **Same input** → **Same output** every time.
2. It **does not produce side effects** (like printing, modifying external state).

Example of pure function with `map()`:

```python
def multiply_by_2(item):
    return item * 2

my_list = [1, 2, 3]
new_list = list(map(multiply_by_2, my_list))

print(new_list)    # [2, 4, 6]
print(my_list)     # [1, 2, 3] — unchanged (immutable)
```

✔️ **No side effects**
✔️ **Same input gives same output**
✅ Pure function confirmed

---

### 🧼 **Benefits of Using `map()` in Functional Programming**

* ✅ Keeps code **clean and readable**
* ✅ Promotes **immutability**
* ✅ Makes functions **reusable and testable**
* ✅ Avoids bugs by **not modifying the original data**

---

### 🧭 Real-Life Use Case

Want to uppercase all usernames?

```python
usernames = ['alice', 'bob', 'charlie']
uppercased = list(map(str.upper, usernames))
print(uppercased)  # ['ALICE', 'BOB', 'CHARLIE']
```

---

### 🔚 Conclusion:

* `map()` is **core to functional programming** in Python.
* It allows **transforming data immutably** using **pure functions**.
* It’s a **cleaner alternative to loops** for many transformation tasks.

---

Next up: 🔍 `filter()` — let’s see how we can **select** elements from a list based on a condition.

Perfect! Here's a concise and clear **note summary for the `filter()` function**, continuing from your lesson on `map()` and emphasizing its use in functional programming:

---

### 🧪 **Understanding `filter()` in Python**

---

### 🔹 **Purpose:**

To **filter elements** in an iterable based on a condition.

Unlike `map()`, which returns the same number of elements, `filter()` may return **fewer elements**, depending on whether each element passes the **test function**.

---

### ✅ **Syntax:**

```python
filter(function, iterable)
```

* `function`: A function that returns `True` or `False` (Boolean).
* `iterable`: A list or any iterable object.

---

### 🧠 **Example: Filter Odd Numbers**

```python
def only_odd(item):
    return item % 2 != 0

print(list(filter(only_odd, [1, 2, 3])))  # Output: [1, 3]
```

#### ✔️ Explanation:

* Each item is passed to `only_odd()`.
* If the function returns `True`, the item is **kept**.
* If the function returns `False`, the item is **filtered out**.

---

### 📌 **Key Concepts:**

* `filter()` **does not modify the original list**.
* It returns a **new filtered iterable** (a `filter` object), which needs to be converted to a list if you want to see the result.
* Just like `map()`, the function passed to `filter()` is not called directly—you simply provide a reference to it.

---

### 🧪 **Real-Life Use Case:**

Want to filter users whose names start with **"A"?**

```python
def starts_with_a(user):
    return user.startswith('A')

users = ['Alice', 'Bob', 'Angela', 'Mark']
filtered_users = list(filter(starts_with_a, users))
print(filtered_users)  # ['Alice', 'Angela']
```

---

### 🧼 **Why It Fits Functional Programming**

* ✅ Pure function — doesn't affect external state
* ✅ Immutable input — original list stays the same
* ✅ Returns a new result without side effects
* ✅ Focused single-responsibility logic

---

### 🧵 Comparison Recap: `map()` vs `filter()`

| Feature       | `map()`                   | `filter()`                      |
| ------------- | ------------------------- | ------------------------------- |
| Output Size   | Same as input             | Equal or smaller than input     |
| Function Type | Returns transformed value | Returns `True` or `False`       |
| Use Case      | Modify items              | Select items based on condition |

---

Next up: 🔗 **`zip()`** — used to pair elements from multiple iterables together.


---

### 🔗 **Understanding `zip()` in Python**

---

### 🔹 **Purpose:**

To **combine multiple iterables** element-wise into **tuples** — just like how a zipper joins two sides together.

---

### ✅ **Syntax:**

```python
zip(iterable1, iterable2, ...)
```

* Takes any number of **iterables** (lists, tuples, etc.)
* Returns a **zip object** — pairs of elements as **tuples**

---

### 🧠 **Example: Zipping Two Lists**

```python
my_list = [1, 2, 3]
your_list = [10, 20, 30]

zipped = list(zip(my_list, your_list))
print(zipped)  # Output: [(1, 10), (2, 20), (3, 30)]
```

---

### 🧵 **How It Works:**

* Takes the **1st item** from each iterable → creates a tuple.
* Repeats for **2nd**, **3rd**, etc., until the **shortest iterable ends**.
* Like a **zipper**, it closes together corresponding items.

---

### 📦 **Supports All Iterables:**

```python
print(list(zip((1, 2, 3), [10, 20, 30])))
# Output: [(1, 10), (2, 20), (3, 30)]
```

✔️ You can mix tuples, lists, sets, etc. as long as they’re iterable.

---

### 🧪 **Real-Life Use Case:**

Let’s say you fetched:

* Usernames from one DB column
* Phone numbers from another column

You can zip them together like:

```python
usernames = ['alice', 'bob', 'carol']
phones = ['123', '456', '789']

user_data = list(zip(usernames, phones))
print(user_data)
# Output: [('alice', '123'), ('bob', '456'), ('carol', '789')]
```

Now you’ve got a combined structure with each user’s name and phone number.

---

### ➕ **Zipping More Than Two Lists:**

```python
a = [1, 2, 3]
b = [4, 5, 6]
c = [7, 8, 9]

print(list(zip(a, b, c)))
# Output: [(1, 4, 7), (2, 5, 8), (3, 6, 9)]
```

✅ `zip()` stops at the **shortest list** to avoid index errors.

---

### 🧼 Functional Style

* ✅ Doesn't modify existing data
* ✅ Returns a **new iterable**
* ✅ Keeps data **immutable and clean**
* ✅ Great for creating **structured pairings**

---

### ⛔ What Happens with Uneven Lists?

```python
a = [1, 2]
b = [10, 20, 30]

print(list(zip(a, b)))  # Output: [(1, 10), (2, 20)]
```

✔️ Stops at the shortest list (`[1, 2]`), ignoring the leftover `30` in `b`.

---

### 📌 Summary Table

| Feature            | `zip()`                       |
| ------------------ | ----------------------------- |
| Input              | Two or more iterables         |
| Output             | `zip` object → list of tuples |
| Use Case           | Combine items by position     |
| Stops at           | Shortest iterable             |
| Modifies original? | ❌ No                          |

---

Next up: 🧮 **`reduce()`** — reducing a list to a single value by applying a function cumulatively.



Let me give you a quick **summary and comparison**, then show a **real-life analogy** and **practical examples** for all three.

---

### ✅ **1. map()**

**Purpose**: Transforms **every element** in an iterable using a function.

#### Syntax:

```python
map(function, iterable)
```

#### Example:

```python
numbers = [1, 2, 3]
squares = list(map(lambda x: x**2, numbers))
# Output: [1, 4, 9]
```

---

### ✅ **2. filter()**

**Purpose**: Filters elements **based on a condition** (function that returns True/False).

#### Syntax:

```python
filter(function, iterable)
```

#### Example:

```python
numbers = [1, 2, 3, 4]
even = list(filter(lambda x: x % 2 == 0, numbers))
# Output: [2, 4]
```

---

### ✅ **3. reduce()**

**Purpose**: Repeatedly applies a function to **reduce** the iterable into a **single value**.

#### Syntax:

```python
from functools import reduce
reduce(function, iterable, [initial])
```

#### Example:

```python
from functools import reduce
numbers = [1, 2, 3]
total = reduce(lambda acc, item: acc + item, numbers, 0)
# Output: 6
```

---

## 🔄 Real-Life Analogy

* **map** is like a **factory line** where every item gets painted red.
* **filter** is like a **quality control** line where only items with no defects are kept.
* **reduce** is like a **crusher** that compresses a box of items into one block.

---

## 🛠️ Practical Real-Life Example

Imagine you're working with users from a database:

```python
usernames = ['alice', 'bob', 'charlie']
phone_numbers = ['123', '456', '789']
```

### Use `zip` to combine them:

```python
combined = list(zip(usernames, phone_numbers))
# [('alice', '123'), ('bob', '456'), ('charlie', '789')]
```

### Use `map` to format:

```python
formatted = list(map(lambda pair: f"{pair[0]}: {pair[1]}", combined))
# ['alice: 123', 'bob: 456', 'charlie: 789']
```

### Use `filter` to keep only users with phone number starting with '1':

```python
filtered = list(filter(lambda pair: pair[1].startswith('1'), combined))
# [('alice', '123')]
```

### Use `reduce` to count total characters in all usernames:

```python
from functools import reduce
total_chars = reduce(lambda acc, name: acc + len(name), usernames, 0)
# Output: 18
```

---

## 🚀 Pro Tip

You can **chain them** together:

```python
from functools import reduce

data = ['  Alice ', ' Bob', 'Charlie  ']
# Clean names and count total characters
result = reduce(lambda acc, name: acc + len(name),
                map(str.strip, filter(lambda x: x.strip(), data)), 0)

# Output: 15
```

---



