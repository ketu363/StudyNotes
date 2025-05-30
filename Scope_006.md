
---

## 🧠 Lecture Notes: Python Scope

---

### 📌 What is *Scope*?

> **Scope** defines what **variables** you have **access to** at any given point in your program.

---

### 🚫 Example: Undefined Variable

```python
print(name)  # ❌ Error: name is not defined
```

* You’ll get a `NameError` because the variable `name` **does not exist** in the current scope.

---

### 🔄 Types of Scope in Python

Python uses **Function Scope** (aka **local scope**), not block scope.

#### 🔹 Global Scope

* Any variable defined **outside** a function.
* Accessible **everywhere** in the file.

```python
total = 100  # Global scope

def some_func():
    print(total)  # ✅ Can access global variable

some_func()
```

#### 🔹 Function Scope

* Any variable **defined inside** a function.
* Only accessible **within that function**.

```python
def some_func():
    total = 100  # Function scope
    print(total)  # ✅ OK here

print(total)  # ❌ NameError outside the function
```

---

### 🔍 Does Python Have Block Scope?

❌ **No block scope** for conditionals or loops:

```python
if True:
    x = 10

print(x)  # ✅ Works! x is still accessible
```

💡 Unlike other languages like JavaScript or C++, Python **does not** create a new scope for `if`, `for`, or `while` blocks.

---

### 🌍 Think of Scope Like Universes

* Every **function** creates a **new world**.
* Variables **inside** this world can't be seen from **outside**.
* But the **outside** world (global) **can be seen** from within a function.

---

### 🧪 Recap

| Variable Location | Accessible Where?         | Scope Type     |
| ----------------- | ------------------------- | -------------- |
| Outside functions | Everywhere in file        | Global scope   |
| Inside functions  | Only within the function  | Function scope |
| Inside if/for     | Still accessible globally | No block scope |

---

### 🎮 Coming Up Next

A little **game/exercise** to figure out **"Who can access whom?"**
Stay tuned!

---




---

## 🧩 Python Scope Game + Resolution Rules

---

### 🎯 The Game: Predict the Output

```python
a = 1

def confusion():
    a = 5
    return a

print(a)         # ➡️ 1
print(confusion())  # ➡️ 5
```

* `a = 1` is in the **global scope**
* Inside the `confusion()` function, `a = 5` is a **local variable**
* **Function creates a new universe** (scope)
* Global `a` is unaffected by the local `a` inside the function

---

### 🔁 Changing the Order Doesn’t Change Scope

```python
a = 1

def confusion():
    a = 5
    return a

print(confusion())  # ➡️ 5
print(a)            # ➡️ 1
```

* Still the same: Local `a` and global `a` are separate.

---

## 🔍 Python Scope Lookup Rules (LEGB Rule)

Python follows **LEGB** (Local → Enclosing → Global → Built-in) to resolve variables:

### 1️⃣ **Local (L)**

* Inside the current function

```python
def confusion():
    a = 5  # local scope
    return a
```

### 2️⃣ **Enclosing (E)** (a.k.a. parent function’s scope)

* If defined in a nested function, checks the **parent** function.

```python
def parent():
    a = 10  # enclosing scope
    
    def confusion():
        return a  # not defined here, looks up to parent
    
    return confusion()

print(parent())  # ➡️ 10
```

### 3️⃣ **Global (G)**

* Checks the file-level/global scope if not found in local or enclosing.

```python
a = 1  # global

def confusion():
    return a  # no local, no enclosing, uses global

print(confusion())  # ➡️ 1
```

### 4️⃣ **Built-in (B)**

* If not found in local, enclosing, or global, Python checks built-in functions.

```python
print(sum)  # ➡️ <built-in function sum>
```

* Python *knows* `sum` because it's a **built-in function**.

---

## 🧠 Visual Summary

| Scope Level       | Example Code Context                   | Searched In |
| ----------------- | -------------------------------------- | ----------- |
| **Local (L)**     | Inside the current function            | ✅ First     |
| **Enclosing (E)** | Outer function if function is nested   | ✅ Second    |
| **Global (G)**    | Top of the file (not in any func)      | ✅ Third     |
| **Built-in (B)**  | Python default functions (e.g., `sum`) | ✅ Last      |

---

### 🧪 Final Thought

> **Scope = Who has access to what?**
> Whenever a variable is called, Python asks:
> “Where do I find this? Local? Enclosing? Global? Built-in?”

---



---

### 🔁 Parameters and Local Scope

```python
def confusion(b):
    print(b)

confusion(300)
```

* **Parameters** like `b` are part of the **local scope** of the function.
* They're defined when the function is called and **can't be accessed outside** the function.
* So `b` exists **only within** the function `confusion`.

---

### 🔄 Global Scope and the `global` Keyword

```python
total = 0

def count():
    global total
    total += 1
    return total
```

* `global` tells Python that `total` inside the function **refers to the global variable**.
* This allows the function to **modify global state**, but it's often discouraged in large programs because:

  * It breaks encapsulation.
  * It makes code harder to debug.
  * It can cause unexpected side effects.

---

### ✅ Better Practice: Dependency Injection

```python
def count(total):
    return total + 1

total = 0
total = count(total)
total = count(total)
total = count(total)
print(total)
```

* **No global keyword needed.**
* Variables are passed **as arguments** and returned, keeping everything clean and contained.
* This approach is more **functional and testable**.

---

### 🌍 Scope Resolution Order (LEGB Rule)

1. **Local** – Inside the function.
2. **Enclosing** – Parent functions (if using nested functions).
3. **Global** – Top-level of the script/module.
4. **Built-in** – Python's built-in names (`sum`, `len`, etc).

This is what Python checks when trying to resolve a variable.

---

### 🔜 Coming Up: `nonlocal`

You hinted at `nonlocal`, which is useful in nested functions when:

* You want to **modify a variable in the enclosing (not global)** scope.
* It's like a middle ground between local and global.

Stay tuned — it's a super useful concept for closures and decorators.

---

Great job sticking with this! You're now learning about **`nonlocal`**, one of Python's more advanced (and rarely used) keywords. Let’s break down what’s happening in this confusing example and why it matters.

---

## 🧠 Understanding `nonlocal`

### ❓ What is `nonlocal`?

* It allows **inner functions** to modify a **variable from an outer (but non-global) scope**.
* Think of it as: “I want to reach up one level in scope—not the global level, just the immediate enclosing function.”

---

## 💡 Example Breakdown

```python
def outer():
    x = "local"
    
    def inner():
        nonlocal x
        x = "non-local"
        print("inner:", x)
    
    inner()
    print("outer:", x)

outer()
```

### 🔄 What Happens Step by Step:

1. `outer()` is called.
2. `x = "local"` creates a variable **local to `outer()`**.
3. `inner()` is defined inside `outer()`.
4. When `inner()` runs:

   * `nonlocal x` tells Python:

     > “Don't make a new `x`. Use the one from the outer function.”
   * So when we assign `x = "non-local"`, we **change the `x` from `outer()`**, not a new one.
5. `print("inner:", x)` prints `"non-local"`.
6. After `inner()` runs, `print("outer:", x)` also prints `"non-local"` because the variable was **modified**.

---

### 🧪 Without `nonlocal`

```python
def outer():
    x = "local"
    
    def inner():
        x = "non-local"  # New variable inside inner()
        print("inner:", x)
    
    inner()
    print("outer:", x)

outer()
```

* Now `inner()` creates its **own new `x`**, so the outer one is untouched.
* You get:

  ```
  inner: non-local
  outer: local
  ```

---

## ⚠️ When to Use `nonlocal`?

🟢 Good for:

* **Closures**, e.g., when defining a function that remembers a value.
* Simple state retention inside nested functions.

🔴 Bad for:

* General use in large apps—it adds mental overhead.
* Replacing `global`—if you need persistent state, consider using a class.

---

## ✅ Takeaway

> `nonlocal` is a powerful tool—but with great power comes great responsibility.

### 📌 Rule of Thumb:

* Prefer **clean function design** where all variables are passed in or returned.
* Use `nonlocal` **only when absolutely necessary**, such as in **decorators**, **closures**, or **currying functions**.

---



---

## 🧠 **Why Not Use Global Variables for Everything?**

You're right to ask:

> "Why not just use global variables and be done with all this headache?"

Here’s why:

---

### ⚠️ **1. Global Variables Stay in Memory — Forever (Until Program Ends)**

When you define something globally:

```python
x = "I'm global!"
```

It sits in memory **for the entire life of the program**, even if it's only needed once.
This means:

* **Wasted memory.**
* Can **accidentally get changed** by something else in your code.

---

### 🗑️ **2. Local Variables Get Cleaned Up Automatically**

When a function ends, Python’s **garbage collector** comes in and says:

> “Oh, we’re done with this? Let’s free up that memory.”

Example:

```python
def outer():
    x = "temporary"
    print(x)

outer()
print(x)  # ❌ Error: x is not defined
```

* ✅ `x` exists only while the function runs.
* ✅ Saves memory.
* ✅ Prevents bugs due to unexpected interference.

---

### 💥 **3. Global Variables Can Create Hidden Bugs**

Imagine:

```python
x = 5

def do_something():
    x = 10  # Did you mean to overwrite the global x? Or create a new one?

do_something()
print(x)  # Still 5? Or now 10? You’re never quite sure.
```

* It’s very easy to **accidentally overwrite a global** and cause subtle bugs.

---

### 🧼 **4. Functions Help Keep Code Clean and Predictable**

Functions do **two** powerful things:

1. **Encapsulation**: Hide inner logic so it's easier to test, debug, and reuse.
2. **Memory Management**: Use memory only when needed, then release it.

If everything is global, you're back to writing one long spaghetti script instead of clean, modular code.

---

### 🧪 Recap With an Analogy

Imagine your program is a library:

* 🏛️ **Global variables** = Permanent billboards everyone can see and write on. Crowded and risky.
* 📦 **Local variables** = Notes passed around in a meeting room. When the meeting ends, they’re shredded. Neat and efficient.

---

## ✅ So, When *Should* You Use Global Variables?

Only in special cases, such as:

* Constants (like `PI = 3.1415`)
* Config values you want accessible throughout the app
* Shared state for very small programs or scripts

Otherwise:

> 🔁 **Pass variables into functions. Return results.**
> 🧼 Keep everything as local and encapsulated as possible.

---



