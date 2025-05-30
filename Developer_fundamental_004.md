
---

## 🎯 **Developer Fundamentals: What is Good Code?**

When someone says they're a *"good programmer"* or an *"expert developer"*, what does that actually mean? The answer lies in writing **good code**. But what exactly is good code?

Let's break it down into **four key principles** every developer should follow:

---

### 1. 🧼 Clean Code

* **Follow a consistent style** (e.g., PEP8 in Python).
* Avoid messy formatting (like inconsistent spacing or poorly structured lists).
* **Eliminate clutter**: No unnecessary comments or unused variables.
* Make every line purposeful and visually neat.

🛠️ *Example*:

```python
# Bad
myList=[1,2,3] #list

# Good
my_list = [1, 2, 3]
```

---

### 2. 👓 Readable Code

* Write code that’s **easy to read and understand**, even after months or years.
* Use **clear, descriptive variable names**.
* Add **comments only when necessary** to explain *why* (not *what*) something is done.

🧠 *Think:* Can my teammate understand this in 30 seconds?

---

### 3. 🔁 Predictable Code

* Don’t try to be "clever" by using obscure or complex constructs just to look smart.
* Keep it **simple, logical, and easy to follow**.
* Focus on **doing one thing well** at a time.

🧘‍♂️ Code should be *boringly reliable*, not surprisingly clever.

---

### 4. ♻️ DRY Principle — *Don't Repeat Yourself*

* Repetition leads to **bloated, hard-to-maintain code**.
* Use variables, loops, and functions to **reduce redundancy**.
* Updating one place should update everywhere.

🛠️ *Instead of this*:

```python
print("*****")
print("*****")
```

*Do this*:

```python
for _ in range(2):
    print("*****")
```

---

### 🧪 Example: Refactoring Code

Before:

```python
pixels = 1
if pixels == 1:
    print("*")
```

After (cleaner & readable):

```python
if pixels:
    print("*")
```

---

### 🧰 Extensibility Tip

Instead of hardcoding characters, use variables:

```python
fill = "*"
empty = " "
print(fill)
```

Want to switch to `#` or `$` later? Change it in one place.

---

## 🧠 Summary

Good code is:

* ✅ **Clean**
* ✅ **Readable**
* ✅ **Predictable**
* ✅ **DRY**

Keep these principles in mind — they’ll help you write better, scalable, and maintainable code as you grow into a professional developer. See you in the next lesson!

---

