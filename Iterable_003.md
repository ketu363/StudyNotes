
---

# 📘 **Understanding "Iterable" in Python**

## 🔑 What is an *Iterable*?

* An **iterable** is **any object** in Python that can be **looped over (iterated)** one item at a time.
* You’ll commonly hear:

  * “Loop over an iterable”
  * “Iterate through a collection”
  * “This object is not iterable”

### ✅ Examples of Iterable Objects:

| Object Type    | Example                           |
| -------------- | --------------------------------- |
| **List**       | `['apple', 'banana', 'cherry']`   |
| **Tuple**      | `(1, 2, 3)`                       |
| **Set**        | `{10, 20, 30}`                    |
| **String**     | `'Hello'`                         |
| **Dictionary** | `{'name': 'Gollum', 'age': 5000}` |

---




## 🔁 What Does "Iterate" Mean?

* To **iterate** means to **go through items one by one** in a collection.
* **Iterable** = the object (noun)
* **Iterate** = the action (verb)

---

## 📦 Working with a Dictionary as an Iterable

### Example Dictionary:

```python
user = {
    "name": "Gollum",
    "age": 5000,
    "can_swim": False
}
```

### 🔹 Iterating Over Keys (Default)

```python
for item in user:
    print(item)
```

**Output:**

```
name
age
can_swim
```

> 🔍 By default, iterating over a dictionary gives the **keys**.

---

## 📂 Useful Dictionary Methods for Iteration

### 1. `items()`: Returns **key-value pairs** as tuples

```python
for item in user.items():
    print(item)
```

**Output:**

```
('name', 'Gollum')
('age', 5000)
('can_swim', False)
```

🔹 Tuple unpacking to extract key and value:

```python
for key, value in user.items():
    print(key, value)
```

**Output:**

```
name Gollum
age 5000
can_swim False
```

> ✅ Cleaner and more Pythonic!

---

### 2. `values()`: Returns **only the values**

```python
for value in user.values():
    print(value)
```

**Output:**

```
Gollum
5000
False
```

---

### 3. `keys()`: Returns **only the keys** (explicitly)

```python
for key in user.keys():
    print(key)
```

**Output:**

```
name
age
can_swim
```

---

## ⚠️ Not All Objects Are Iterable

### ❌ Example: Trying to iterate over an `int`

```python
for i in 50:
    print(i)
```

**Error:**

```
TypeError: 'int' object is not iterable
```

> 🧠 **Why?** Because `int` is a **single value**, not a **collection**.

---

## 🧠 Summary

| Concept                  | Description                                              |
| ------------------------ | -------------------------------------------------------- |
| **Iterable**             | An object you can loop through (e.g., list, tuple, dict) |
| **Iterate**              | The action of going through items in a collection        |
| **Dictionary Iteration** | Use `.keys()`, `.values()`, or `.items()` for control    |
| **Tuple Unpacking**      | Handy way to access key/value from `.items()`            |
| **Error to Know**        | `TypeError: 'int' object is not iterable`                |

---

## 💡 Pro Tip:

In real-world Python code, you'll often see:

```python
for k, v in my_dict.items():
    print(f"Key: {k}, Value: {v}")
```

> Keep variable names meaningful for better readability!

---



---

### 🔁 Introduction to `range()`

* In Python, `range()` is a built-in function used primarily for looping.
* It returns a **range object**, which is a special type that generates a sequence of integers from a starting point to an endpoint.

```python
range(100)  # Output: range(0, 100)
```

* Though it might look like a tuple or list, it's actually its own object type.

### 📌 Syntax of `range()`

```python
range(stop)             # Starts from 0 to stop - 1
range(start, stop)      # Starts from start to stop - 1
range(start, stop, step)# Adds a step (default is 1)
```

### ✅ Using `range()` in Loops

The most common use of `range()` is within `for` loops:

```python
for number in range(100):
    print(number)
```

* This prints numbers from 0 to 99.
* Loop runs 100 times.

Use-case example:

```python
for _ in range(10):
    print("Sending email...")
```

* The underscore `_` is used as a throwaway variable (not needed in the loop).

### 🔄 Looping with Step

```python
for number in range(0, 10, 2):
    print(number)
```

* Prints: 0, 2, 4, 6, 8

Step can also be negative:

```python
for number in range(10, 0, -1):
    print(number)
```

* Prints in reverse from 10 to 1
* Just using `range(10, 0)` **won’t work**, you must specify the step as `-1` or another negative number.

### 📃 Convert Range to List

You can convert a range into a list using `list()`:

```python
list(range(10))
# Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Example:

```python
for i in range(2):
    print(i)
```

* Loops 2 times and prints 0 and 1.

---

### 🎯 Key Takeaways

* `range()` is powerful and memory-efficient.
* Commonly used in `for` loops.
* Can be ascending or descending.
* Easily converted to a list when needed.

---


### Looping with `enumerate()` in Python

Another useful function similar to `range()` is `enumerate()`. Though not as common as `range()`, it can be very handy when you want both the index and the value from an iterable.

#### Basic Usage of `enumerate()`

You can use `enumerate()` in a for loop to get the index and value of each item in a sequence. For example:

```python
for i, character in enumerate("hello"):
    print(i, character)
```

This prints:

```
0 h
1 e
2 l
3 l
4 o
```

The `enumerate()` function wraps around any iterable (like strings, lists, or tuples) and provides a counter alongside the values.

#### Using `enumerate()` with Lists and Tuples

```python
for i, item in enumerate([1, 2, 3]):
    print(i, item)

for i, item in enumerate(("a", "b", "c")):
    print(i, item)
```

This will print both the index and the item from the list and tuple.

#### Exercise: Find the Index of a Value

Suppose we want to find the index of the value `50` in a list of numbers from `0` to `99`:

```python
numbers = list(range(100))
for i, num in enumerate(numbers):
    if num == 50:
        print(f"The index of 50 is {i}")
```

Output:

```
The index of 50 is 50
```

We use a conditional inside the loop to check for the value `50` and print its index using an f-string.

#### Summary

* `enumerate()` is useful when you need both the index and the value in a loop.
* It works with any iterable.
* Though not as commonly used as `range()`, it's an important tool to know when working with Python loops.



---

### 🔁 **While Loops in Python**

* A `while` loop runs **as long as a condition is true** ✅

```python
i = 0
while i < 50:
    print(i)
    i += 1
```

* ⚠️ **Infinite Loop Alert!**
  If you forget to update the condition, it loops forever 🔁🔁🔁

```python
i = 0
while i < 50:
    print(i)  # ❗Runs forever since i never changes
```

* ✅ **Avoiding Infinite Loops**

  * Use `i += 1` to change the condition each time 🔢
  * Or use a `break` statement to exit early ⛔

```python
i = 0
while i < 50:
    print(i)
    break  # 🚪 Exits loop immediately
```

---

### 🔚 **Using `else` with While Loops**

* The `else` block runs **only if the `while` loop finishes naturally** (no `break`) 🏁

```python
i = 0
while i < 3:
    print(i)
    i += 1
else:
    print("✅ Done with all the work!")
```

* If a `break` is used, the `else` is skipped 🚫

```python
i = 0
while i < 3:
    print(i)
    break
else:
    print("❌ You won’t see this")
```

---

### 📝 **Summary**

✅ Use `while` when:

* You don't know in advance how many times to loop 🔄
* You want to run a block of code *while* a condition is true 🧠
* You understand how to avoid infinite loops 🚨

✨ `else` gives you a way to handle post-loop actions — but only if the loop wasn't interrupted by `break`.

---


---

## 🌀 For Loop vs While Loop in Python 🐍

### ❓ **When to use what?**

It really depends on **what problem you're trying to solve** 🤔

---

### 🔁 `for` loop: Clear and concise

```python
for item in [1, 2, 3]:
    print(item)
```

✅ You **know upfront** how many times it will loop – **3 times** in this case.
✅ Simple and **clean to read** 👓

---

### 🔄 `while` loop: More control, more flexibility 🔧

```python
i = 0
my_list = [1, 2, 3]
while i < len(my_list):
    print(my_list[i])
    i += 1
```

🛠️ You **control the condition** – you must:

* initialize `i` 🟢
* update `i` 🔼
* and avoid infinite loops! ⚠️

---

### 🔍 Which is better?

💡 **Use `for` loop** when:

* You’re **iterating over an iterable** (list, tuple, range)
* You **know** the number of iterations

💡 **Use `while` loop** when:

* You **don’t know** how many times the loop should run
* You loop until a **condition becomes false**

---

### 📧 Example: Sending emails

```python
while email_list:
    send_email(email_list.pop())
```

➡️ Keep looping **while there's work left**.

---

### 💬 The ultimate while loop trick:

```python
while True:
    response = input("Say something: ")
    if response == "bye":
        break
```

🧠 This is a powerful **infinite loop** structure (unless broken manually):

* Keeps asking for input ⌨️
* Ends only when condition met (`"bye"`) 🔚

---

### 🧠 Summary

| Situation                           | Loop Type       | Why ✅                  |
| ----------------------------------- | --------------- | ---------------------- |
| Fixed number of iterations          | `for` loop 🧾   | Simple, readable       |
| Unknown or conditional iteration    | `while` loop 🔄 | Flexible, dynamic      |
| Need infinite loop with exit option | `while True` ♾️ | Controlled via `break` |

---

### 💬 Final Tip

> ✅ Use **what solves your problem**
> 🧘 With practice, you'll instinctively know when to use what!

---



---

## 🌀 Loop Control Statements in Python: `break`, `continue`, `pass` 🚦

In Python, loops like `for` and `while` can be controlled using three special keywords:

### ✅ 1. `break` – **Exit the Loop Immediately** 🚪

```python
for item in [1, 2, 3]:
    if item == 2:
        break
    print(item)
```

* 💥 **Breaks** out of the *entire* loop as soon as the condition is met.
* 🛑 Useful when you want to **stop looping** altogether.
* ✔️ Works with both `for` and `while` loops.

### 🔄 2. `continue` – **Skip the Rest of This Iteration** ⏩

```python
for item in [1, 2, 3]:
    if item == 2:
        continue
    print(item)
```

* 🧠 Skips the current loop iteration and **goes back to the top** of the loop.
* 📌 Code **after** the `continue` statement **won’t run** in that iteration.

#### 🧪 Example with extra print:

```python
for i in range(5):
    if i == 3:
        continue
    print("Number:", i)
```

📤 Output:

```
Number: 0
Number: 1
Number: 2
Number: 4
```

🧩 `continue` is very helpful when applying **conditional logic** in loops.

---

### 🧘 3. `pass` – **Do Nothing at All** 😶

```python
for i in range(3):
    pass
```

* ⚙️ A **placeholder** that tells Python: *“Hey, I’m not ready to write code here yet!”*
* 🧱 Prevents errors like:

  ❌ `IndentationError: expected an indented block`

#### 🛠️ Example Use Case:

```python
for item in range(5):
    # Logic to be added later
    pass
```

✅ This code runs fine, even though nothing happens inside the loop.

---

### ⚖️ Summary Table

| Keyword    | Behavior                                   | Use Case 🧠                            |
| ---------- | ------------------------------------------ | -------------------------------------- |
| `break`    | ❌ Exits the loop entirely                  | Stop looping under a certain condition |
| `continue` | 🔁 Skips current iteration, continues loop | Skip certain items but keep looping    |
| `pass`     | 💤 Does nothing at all                     | Placeholder during code development    |

---

### 👨‍💻 Developer Insight:

> 🧪 **`pass`** isn’t used often in production, but it’s a **life-saver** while writing and testing unfinished code blocks! 🧪

---

🧵 And there you have it — the **three powerful tools** to control your Python loops like a boss! 😎
See you in the next one. 👋✨

---






#### 🖼️ **Exercise: Drawing an ASCII Image from a 2D List**

**Goal:** Simulate a graphical pixel-based image using `*` for pixels (`1`) and space (` `) for blanks (`0`).

##### ✅ Steps to Build:

1. **Understand the structure** – a 2D list representing an image:

   ```python
   picture = [
       [0,0,1,0,0],
       [0,1,1,1,0],
       [1,1,1,1,1],
       [0,1,1,1,0],
       [0,0,1,0,0],
   ]
   ```

2. **Nested loop to iterate through rows and pixels:**

   ```python
   for row in picture:
       for pixel in row:
           if pixel == 1:
               print("*", end="")
           else:
               print(" ", end="")
       print()  # Print a newline at the end of each row
   ```

3. **Important Tip:**

   * Use `print(..., end="")` to avoid a newline after every character.
   * Use `print()` to move to the next row after each inner loop.

##### 🎄 Output Example (ASCII Art):

```
  *  
 *** 
*****
 *** 
  *  
```

---

