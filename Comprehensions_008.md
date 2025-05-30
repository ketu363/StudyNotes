
---

## 🐍 Python Comprehensions

### 🎯 What Are Comprehensions?

**Comprehensions** in Python provide a **concise way** to create **lists, sets, or dictionaries** without using traditional loops and `append()` or `add()` methods.

* ✅ **List Comprehension**
* ✅ **Set Comprehension**
* ✅ **Dictionary Comprehension**

Comprehensions are one of the **unique and elegant features** of Python, allowing for **cleaner, faster, and more readable** code.

---

### 📃 Traditional vs Comprehension (List Example)

#### Traditional Way:

```python
my_list = []
for character in "hello":
    my_list.append(character)
print(my_list)
```

#### With List Comprehension:

```python
my_list = [character for character in "hello"]
print(my_list)
```

📌 **Explanation**:

* Create a list
* For each character in the iterable `"hello"`
* Add it to the list

---

### 📈 Creating Number Lists

```python
my_list2 = [number for number in range(100)]
print(my_list2)
```

✅ Generates numbers from **0 to 99**

---

### 🔁 Apply an Expression (e.g., Multiply by 2)

```python
my_list3 = [number * 2 for number in range(100)]
print(my_list3)
```

🧠 **Think of it like Lambda**: You apply an **operation** to each element.

---

### 🔍 Add a Condition – Keep Only Even Squares

```python
my_list4 = [number ** 2 for number in range(100) if number ** 2 % 2 == 0]
print(my_list4)
```

🧩 Format:

```python
[expression for variable in iterable if condition]
```

📌 **Explanation**:

* Compute `number ** 2`
* Include only if the result is even

---

### 💡 Why Use Comprehensions?

* ✅ **Short and clean** code
* ✅ **Efficient** (in both time and space)
* ✅ Great for **one-liner transformations and filters**

But...

> ❗ **Readability trade-off**
> If your logic gets too complex, it’s often better to write a function with a clear name.

```python
def generate_even_squares():
    return [n**2 for n in range(100) if n**2 % 2 == 0]
```

---

### 📌 Key Takeaways

| Type        | Syntax Example                            |
| ----------- | ----------------------------------------- |
| **List**    | `[x for x in iterable]`                   |
| **With If** | `[x for x in iterable if condition]`      |
| **Set**     | `{x for x in iterable}`                   |
| **Dict**    | `{key: value for key, value in iterable}` |

---

### 🐦 Fun Fact:

> The video was recorded with birds chirping in the background – for a peaceful learning vibe!

---

### 🧭 Coming Up Next

➡️ In the next video, we’ll explore:

* **Set Comprehension**
* **Dictionary Comprehension**

---


---

## 📘 Python Comprehensions (Set & Dictionary)

### 🔁 **Recap: Comprehensions in Python**

Comprehensions are a quick, readable way to create collections (like lists, sets, or dictionaries) in Python using a single line of code, often replacing longer loops with `append()` or `add()` methods.

---

## 🔸 **Set Comprehension**

Set comprehension works just like list comprehension but uses **curly braces `{}`**.

### 🔹 Syntax:

```python
{expression for item in iterable}
```

### 🔹 Example:

```python
my_set = {char for char in "hello"}
print(my_set)  # Output: {'h', 'e', 'l', 'o'} — duplicates removed
```

Set comprehensions automatically **remove duplicates** because sets only store **unique elements**.

You can also apply transformations:

```python
my_set = {num**2 for num in range(10) if num % 2 == 0}
print(my_set)  # Output: {0, 4, 16, 36, 64}
```

---

## 🔸 **Dictionary Comprehension**

Dictionary comprehensions let you create dictionaries from iterables.

### 🔹 Syntax:

```python
{key_expr: value_expr for key, value in iterable}
```

### 🔹 Example 1 – From Existing Dictionary:

```python
simple_dict = {"a": 1, "b": 2}
new_dict = {k: v**2 for k, v in simple_dict.items()}
print(new_dict)  # Output: {'a': 1, 'b': 4}
```

With a condition:

```python
even_dict = {k: v**2 for k, v in simple_dict.items() if v % 2 == 0}
print(even_dict)  # Output: {'b': 4}
```

### 🔹 Example 2 – From a List:

```python
numbers = [1, 2, 3]
squared_dict = {num: num*2 for num in numbers}
print(squared_dict)  # Output: {1: 2, 2: 4, 3: 6}
```

---

## 🧠 Summary

| Comprehension Type | Syntax Example                      | Output Structure           |
| ------------------ | ----------------------------------- | -------------------------- |
| List               | `[x for x in range(5)]`             | List `[0, 1, 2, 3, 4]`     |
| Set                | `{x for x in "hello"}`              | Set `{'h', 'e', 'l', 'o'}` |
| Dict               | `{k: v*2 for k, v in dict.items()}` | Dict `{'a': 2, 'b': 4}`    |

---

## ⚠️ Tips

* Comprehensions make code **shorter**, but **can hurt readability** if overused or complex.
* Use them when they **improve clarity**, not just to write fewer lines.

---


