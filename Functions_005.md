
---

## 🧠 Lecture Notes: Introduction to Functions in Python

---

### ✅ What Are Functions?

* **Functions** allow us to **perform actions** and **reuse logic** in our programs.
* Up to this point, you've used **built-in functions** like:

  * `print()`
  * `input()`
  * `list()`
  * `bool()`

Now, it's time to create your **own custom functions**!

---

### 🛠 How to Define a Function in Python

```python
def say_hello():
    print("Hello")
```

* `def` keyword is used to **define** a function.
* Function names follow the **same naming rules** as variables (snake\_case is recommended).
* Use parentheses `()` after the name.
* Use a colon `:` to indicate the start of the **function body**.
* **Indent** the body properly (very important in Python!).

---

### ▶ How to Call a Function

```python
say_hello()  # Output: Hello
```

* Functions are **stored in memory** after they're defined.
* To **execute** or **call** them, use the function name **with parentheses**.
* Calling without parentheses:

  ```python
  print(say_hello)  # Shows memory location, not output
  ```

---

### 🔁 Why Use Functions?

1. **DRY Principle** – *Don’t Repeat Yourself*
2. Write logic **once**, reuse it **anytime**.
3. Makes code:

   * Cleaner
   * More maintainable
   * Easier to read

---

### 🎄 Example: Repeating Tree Drawing Code

**Without Function (Not DRY):**

```python
# Manually repeat tree print lines
print("   *")
print("  ***")
print(" *****")
print("*******")
```

**With Function (DRY):**

```python
def show_tree():
    print("   *")
    print("  ***")
    print(" *****")
    print("*******")

# Reuse it multiple times
show_tree()
show_tree()
show_tree()
```

---

### ⚠️ Function Placement Matters

* Always define the function **before** using it.

```python
# ❌ This will throw an error
show_tree()  # NameError: 'show_tree' is not defined

def show_tree():
    print("   *")
    print("  ***")
```

Python reads **top to bottom**, so it must know what `show_tree` is **before** trying to run it.

---

### 🧠 Fun Fact:

```python
print(show_tree)
```

* This prints the **memory location** of the function object.
* Just a reference to where Python stored the definition.

---

### 🧩 Summary

| Concept       | Description                         |
| ------------- | ----------------------------------- |
| `def`         | Used to define a function           |
| `()`          | Used to call (execute) the function |
| DRY Principle | Write once, reuse many times        |
| Indentation   | Very important in Python functions  |
| Placement     | Define before calling               |

---

📌 Next: Learn how to make functions more **dynamic** using **parameters**!






---

## 🧠 Lecture Notes: Arguments vs Parameters in Python Functions

### 🔹 Recap of `say_hello` Function

So far, our `say_hello()` function only prints `"Hello"`. Useful, but limited — it always says the same thing.

---

### 🔸 Parameters (Function Definition)

* **Parameters** are *placeholders* or *variables* listed inside the function definition.
* Think of parameters as *inputs* your function expects when it's defined.

```python
def say_hello(name, emoji):
    print(f"Hello {name} {emoji}")
```

Here:

* `name` and `emoji` are **parameters**.
* Parameters allow the function to become *dynamic* and reusable.

---

### 🔹 Arguments (Function Call)

* **Arguments** are *actual values* you pass to the function when calling it.
* These values get assigned to the function's parameters.

```python
say_hello("Andre", "😛")
say_hello("Dan", "😎")
say_hello("Emily", "😊")
```

Here:

* `"Andre"`, `"😛"` etc. are **arguments**.
* They get passed into `name` and `emoji` respectively.

---

### ⚠️ Common Confusion

| Term          | When Used              | Example            |
| ------------- | ---------------------- | ------------------ |
| **Parameter** | In function definition | `def greet(name)`  |
| **Argument**  | In function call       | `greet("Nishant")` |

> ✅ Think of parameters as *variable names*, and arguments as *actual data* you feed into them.

---

### 🧩 Why This Matters

* You can **reuse** one function with **many different inputs**.
* Makes code **DRY** (Don’t Repeat Yourself).
* Critical for real-world programs like games, chatbots, forms, etc.

---

### 🧪 Bonus: Function Terminology

* `Call` or `Invoke` a function → means running it.
* Functions can accept any number of parameters.
* You can mix strings, numbers, emojis, etc., depending on what you want to do.

---



---

## 🧠 Lecture Notes: Positional Arguments, Keyword Arguments & Default Parameters

---

### 🔹 1. Positional Arguments

* These are the **most common** way to call functions.
* The **order matters** — arguments are matched to parameters by position.

```python
def say_hello(name, emoji):
    print(f"Hello {name} {emoji}")

say_hello("Andre", "😛")  # ✅ Correct
say_hello("😛", "Andre")  # ❌ Wrong order → "Hello 😛 Andre"
```

> 🟠 You **must** provide arguments in the order the parameters were defined.

---

### 🔸 2. Keyword Arguments

* These allow you to specify **which parameter** gets which value using the `param=value` syntax.
* **Order doesn't matter** as long as you use the parameter names correctly.

```python
say_hello(emoji="😛", name="Bibi")  # ✅ Works fine
```

> ✅ Useful for improving **clarity** when calling functions with many parameters.
> ⚠️ Can reduce readability if used inconsistently.

---

### ⚠️ Best Practice Tip:

Even though keyword arguments give flexibility, **follow the original function signature** when possible for better readability and team consistency.

```python
# Better readability
say_hello(name="Bibi", emoji="😛")
```

---

### 🔹 3. Default Parameters

* Allow you to **define fallback values** in the function definition.
* The function will use these if no corresponding argument is passed.

```python
def say_hello(name="Darth Vader", emoji="😠"):
    print(f"Hello {name} {emoji}")
```

#### Examples:

```python
say_hello()                         # Uses both defaults → Hello Darth Vader 😠
say_hello("Luke")                  # Only overrides name → Hello Luke 😠
say_hello(emoji="🙂")              # Only overrides emoji → Hello Darth Vader 🙂
```

---

### ✅ Benefits of Each:

| Method             | Pros                                    | Cons                                      |
| ------------------ | --------------------------------------- | ----------------------------------------- |
| **Positional**     | Simple and clean                        | Requires remembering correct order        |
| **Keyword**        | Clear and explicit                      | Verbose if overused                       |
| **Default Values** | Makes functions safer and more flexible | Must be used carefully to avoid confusion |

---

### 📌 Final Thought:

Understanding the difference between **parameters (in definition)** and **arguments (in call)**, and using **positional**, **keyword**, and **default** values wisely, will help make your code **more robust, reusable, and readable**.

---


---

## 🧠 Python Functions – The Power of `return`

### 🔑 What is `return`?

* The `return` keyword **exits a function** and **sends back a value** to the caller.
* If a function has no `return`, it **implicitly returns `None`**.

---

### ✅ Basic Usage Example:

```python
def sum(num1, num2):
    return num1 + num2

print(sum(4, 5))  # Output: 9
```

* `return num1 + num2` gives back the result to whoever called the function.
* This result can be printed, stored in a variable, or used in other operations.

---

### 🔍 Why Do We Get `None` Sometimes?

```python
def sum(num1, num2):
    print(num1 + num2)

print(sum(4, 5))  # Output: 9 and then None
```

* The function prints the result but doesn't return anything.
* So the `print()` around the function prints the result from inside the function and then prints `None`.

---

### 🧼 Best Practice:

Functions should:

1. Do **one thing really well**.
2. Ideally **return something** instead of just printing or modifying something.

---

### 🔄 Modifying vs Returning

```python
def modify_list(l):
    l.clear()        # modifies input
    # No return

def get_sum(a, b):
    return a + b     # returns new data
```

* Some functions modify external variables (like lists), others return new values.
* Returning is usually preferred for **clean, testable, and reusable code**.

---

### 🧠 Assigning Returned Values:

```python
def sum(num1, num2):
    return num1 + num2

total = sum(10, 5)
print(total)  # Output: 15

print(sum(10, total))  # Output: 25
```

* Returned values can be assigned to variables and reused.

---

### 🧩 Nested Functions with Return:

```python
def sum(num1, num2):
    def another_func(a, b):
        return a + b
    return another_func(num1, num2)

print(sum(10, 20))  # Output: 30
```

* Functions can **define other functions** and return their results.
* Careful with **naming conflicts** – avoid using the same parameter names in nested scopes.

---

### ⚠️ Common Pitfalls:

* If you define a function inside another but **don’t call it**, nothing runs.
* Returning a function vs calling it:

  ```python
  return another_func    # returns the function
  return another_func(10, 20)  # calls and returns the result
  ```

---

### 🛑 return Exits Immediately

```python
def example():
    return 10
    print("This won't run")
```

* Once `return` is hit, the function **immediately exits**.

---

### 📌 Summary Tips:

* Use `return` to **send back results** from functions.
* Avoid functions doing too many things (e.g., computing *and* printing).
* Nested functions can be powerful but keep them **readable and purposeful**.
* Always know whether your function is **returning or modifying** something.

---


---

## 🧠 Lecture Notes: Functions vs Methods in Python

### 🔹 What Are Functions?

* **Functions** are blocks of reusable code that perform a specific task.
* Python provides many **built-in functions**, such as:

  * `print()`
  * `max()`
  * `input()`
* You can also create **custom functions** using the `def` keyword.

```python
def some_random_stuff():
    pass  # This function does nothing
```

### 🔹 How Do You Call a Function?

* Simply use the function name followed by parentheses:

```python
print("Hello")
max(5, 10)
some_random_stuff()
```

---

### 🔸 What Are Methods?

* **Methods** are functions that **belong to objects** (like strings, lists, sets, etc.).
* They are accessed using **dot notation**:

```python
"hello".capitalize()
```

* If you try to use a method like a regular function:

```python
capitalize("hello")  # ❌ Error: NameError
```

It will fail because `capitalize` is a **method**, not a standalone function.

---

### 🏷️ Ownership of Methods

* The object to the **left of the dot (`.`)** owns the method.

```python
greeting = "hello"
greeting.capitalize()  # 'Hello'
```

### 🔍 Exploring Methods

* IDEs and editors often show a list of available methods when you type the dot (`.`).
* You can also explore official documentation:
  [Python 3 Library Reference](https://docs.python.org/3/library/index.html)

  * Example: [Set Methods](https://docs.python.org/3/library/stdtypes.html#set)

---

### ⚙️ Examples of Built-in Object Methods

```python
# String method
"python".upper()  # 'PYTHON'

# Set methods
my_set = {1, 2, 3}
my_set.add(4)
my_set.remove(2)
```

---

### ✅ Summary: Methods vs Functions

| Feature     | Function      | Method                   |
| ----------- | ------------- | ------------------------ |
| Call syntax | `function()`  | `object.method()`        |
| Ownership   | Global        | Belongs to an object     |
| Example     | `print("Hi")` | `"hi".upper()`           |
| Use case    | General logic | Operations on data types |

---



---

## 🧠  **Docstrings in Python**

### 🔹 What Is a Docstring?

A **docstring** (documentation string) is a special kind of comment in Python used to describe **what a function, class, or module does**.

* Written using **triple quotes (`'''` or `"""`)**
* Placed **at the beginning of the function**
* Helps others understand your code—especially in large projects

---

### 🧪 Example: Using a Docstring

```python
def test(a):
    '''
    This function tests and prints param a.
    '''
    print(a)
```

When you run:

```python
test("Hello!")  # Output: Hello!
```

---

### 📋 What Does the Docstring Do?

* **When calling the function**, the editor shows the docstring as a tooltip or hint:

  ```python
  test(  # tooltip: This function tests and prints param a.
  ```

* **This helps developers know what the function does** without opening the full code.

---

### 🔍 Ways to View a Docstring

1. **Using the `help()` function**:

```python
help(test)
```

📤 Output:

```
Help on function test in module __main__:

test(a)
    This function tests and prints param a.
```

---

2. **Using the `.__doc__` attribute** (a dunder or magic method):

```python
print(test.__doc__)
```

📤 Output:

```
This function tests and prints param a.
```

---

### ✅ Why Use Docstrings?

| Benefit                             | Description                                              |
| ----------------------------------- | -------------------------------------------------------- |
| Improves readability                | Helps teammates or your future self understand code      |
| Boosts collaboration                | Others can see what your function does at a glance       |
| IDE integration                     | Most code editors show docstrings as hints/autocompletes |
| Helps with documentation generation | Tools like Sphinx use docstrings to auto-generate docs   |

---

### 🧪 Bonus Tip: Docstrings Aren't Just for Functions

You can also use docstrings with:

* **Classes**
* **Modules (Python files)**
* **Methods (functions inside classes)**

---

### 🧠 Summary

* Docstrings = Descriptive strings inside functions/classes/modules.
* Write them using triple quotes at the top of your function.
* View with `help()` or `.__doc__`.
* Makes your code easier to understand and maintain.

---


---

## 🧠 Lecture Notes: Python `*args` and `**kwargs`

### ✅ What Are `*args` and `**kwargs`?

They are **special syntax** used to pass a **variable number of arguments** to a function.

---

### 🔹 `*args` (Non-keyworded Variable-length Arguments)

* Collects extra **positional arguments** into a **tuple**.
* Use case: when you want your function to accept **any number of positional arguments**.

#### Example:

```python
def super_func(*args):
    return sum(args)

print(super_func(1, 2, 3, 4, 5))  # Output: 15
```

#### Behind the scenes:

```python
print(args)  # Output: (1, 2, 3, 4, 5)
```

---

### 🔹 `**kwargs` (Keyworded Variable-length Arguments)

* Collects extra **keyword arguments** into a **dictionary**.
* Use case: when you want to accept **named arguments with values**.

#### Example:

```python
def super_func(*args, **kwargs):
    total = sum(args)
    for value in kwargs.values():
        total += value
    return total

print(super_func(1, 2, 3, num1=5, num2=10))  # Output: 21
```

#### Behind the scenes:

```python
print(kwargs)  # Output: {'num1': 5, 'num2': 10}
```

---

### ⚠️ Naming Convention

While you can technically name them anything (e.g., `*hooo`, `**whatever`), the **convention** is:

```python
*args
**kwargs
```

This improves **readability** and follows **Python community standards**.

---

### 🧾 Function Parameter Ordering Rule

When combining different types of parameters, follow this order:

```
1. Regular positional parameters
2. *args
3. Default parameters
4. **kwargs
```

#### Example:

```python
def super_func(name, *args, i="hi", **kwargs):
    print(name, args, i, kwargs)

super_func("Nishant", 1, 2, 3, num1=5, num2=10)
```

---

### 🧼 Clean Code Tips

* Don't overuse all types of arguments in one function — it gets confusing.
* Stick to `*args` or `**kwargs` only when needed.
* Use clear and descriptive names if deviating from conventions (but ideally stick to `args` and `kwargs`).

---

### 🔚 Summary

* `*args` allows you to pass any number of **positional arguments**.
* `**kwargs` allows you to pass any number of **keyword arguments**.
* These are powerful tools for building flexible, reusable functions.
* Remember the order: `params`, `*args`, `defaults`, `**kwargs`.

---



