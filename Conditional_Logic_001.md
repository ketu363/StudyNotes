
### Conditional Logic in Python

**Conditional logic** is a fundamental concept in programming that allows you to execute certain pieces of code based on whether a condition is true or false.

#### Booleans
- **Booleans** represent two values: `True` and `False`.
- They are crucial for conditional logic because they help determine the flow of a program.

#### Example Scenario
Imagine a car that only starts if the driver is old enough (over 18) and has a valid license.

### Python Code Example

```python
# Variables to check conditions
is_old = True
is_licensed = True

# Conditional logic using if statement
if is_old:
    print("You are old enough to drive.")
else:
    print("You are not of age.")

# Output: You are old enough to drive.
```

#### Indentation
- **Indentation** is important in Python. It defines the scope of conditional blocks.
- Code inside the `if` block is indented.

```python
if is_old:
    print("You are old enough to drive.")
    print("Check check.")  # This is part of the if block
print("Check check.")  # This is outside the if block
```

#### Using `else`
- The `else` keyword provides an alternative action if the `if` condition is false.

```python
is_old = False

if is_old:
    print("You are old enough to drive.")
else:
    print("You are not of age.")

# Output: You are not of age.
```

#### Using `elif`
- The `elif` keyword stands for "else if" and allows for multiple conditions.

```python
is_old = False
is_licensed = True

if is_old:
    print("You are old enough to drive.")
elif is_licensed:
    print("You can drive now.")
else:
    print("You are not of age and not licensed.")

# Output: You can drive now.
```



### Summary
- **Conditional logic** helps control the flow of a program by executing code based on conditions.
- **Booleans** (`True` and `False`) are essential for these conditions.
- **Indentation** defines the scope of conditional blocks.
- **`if`, `else`, and `elif`** keywords are used to create conditional statements.




### Importance of Spacing and Indentation in Python

**Indentation** in Python is crucial for defining the structure and flow of the code. Unlike many other programming languages, Python uses indentation to determine the grouping of statements.

#### Key Points:
1. **Indentation Matters**: In Python, indentation is used to indicate a block of code. For example, the code inside an `if` statement must be indented.
2. **Consistency**: It's important to be consistent with the use of spaces or tabs. The standard practice is to use four spaces per indentation level.
3. **Interpreter's Role**: The Python interpreter uses indentation to understand the hierarchy and grouping of code blocks. Incorrect indentation can lead to errors or unexpected behavior.

#### Example:
```python
is_old = True
is_licensed = True

if is_old and is_licensed:
    print("You are old enough to drive and have a license.")
else:
    print("You are not eligible to drive.")
```

In this example:
- The code inside the `if` and `else` blocks is indented.
- The indentation tells the interpreter that these lines are part of the respective conditional blocks.

#### Comparison with Other Languages:
- **JavaScript**: Uses curly braces `{}` to define code blocks. Indentation is for readability and style, not for defining code structure.
    ```javascript
    if (isOld && isLicensed) {
        console.log("You are old enough to drive and have a license.");
    } else {
        console.log("You are not eligible to drive.");
    }
    ```

#### Tabs vs. Spaces:
- **Tabs and Spaces**: Both can be used for indentation, but mixing them can cause issues. The Python community generally prefers spaces, specifically four spaces per indentation level.
- **Auto-formatting**: Many code editors and IDEs can automatically format your code to ensure consistent indentation.

### Summary:
- **Indentation** is essential in Python for defining code blocks.
- **Consistency** in using spaces or tabs is crucial to avoid errors.
- **Readability**: Proper indentation makes the code more readable and maintainable.



### Notes on Truthy and Falsy Values in Python

**Truthy and Falsy Values** are concepts in Python that determine whether a value evaluates to `True` or `False` in a boolean context.

#### Key Points:
1. **Booleans**: Up until now, we've used booleans (`True` and `False`) directly in conditional statements.
2. **Type Conversion**: Python can automatically convert other types to booleans. This is known as type conversion.

#### Example:
```python
is_old = 5
is_licensed = "hello"

if is_old and is_licensed:
    print("You are old enough to drive and you have a license.")
else:
    print("You are not eligible to drive.")

# Output: You are old enough to drive and you have a license.
```

### Truthy Values
- **Truthy** values are those that evaluate to `True` when converted to a boolean.
- Examples of truthy values:
    ```python
    print(bool("hello"))  # Output: True
    print(bool(5))        # Output: True
    ```

### Falsy Values
- **Falsy** values are those that evaluate to `False` when converted to a boolean.
- Examples of falsy values:
    ```python
    print(bool(""))       # Output: False
    print(bool(0))        # Output: False
    print(bool(None))     # Output: False
    ```

### Common Falsy Values in Python:
- `0`
- `""` (empty string)
- `[]` (empty list)
- `{}` (empty dictionary)
- `()` (empty tuple)
- `None`
- `False`

### Practical Example:
Using truthy and falsy values can simplify conditional checks. For instance, checking if a user has provided both a username and a password:

```python
username = "Johnny"
password = "123"

if username and password:
    print("Logging in...")
else:
    print("Please provide both username and password.")
```

### Summary:
- **Truthy and Falsy Values**: Python evaluates values to `True` or `False` in a boolean context.
- **Type Conversion**: Python automatically converts values to booleans in conditional statements.
- **Simplified Conditional Checks**: Using truthy and falsy values can make code cleaner and more readable.


### Notes on Ternary Operators in Python

**Ternary Operators**, also known as **conditional expressions**, provide a shorthand way to perform conditional logic in Python. They allow you to write concise, one-line conditional statements.

#### Key Points:
1. **Ternary Operator**: A shortcut for `if-else` statements that evaluates to a value based on a condition.
2. **Syntax**: The general syntax is:
    ```python
    value_if_true if condition else value_if_false
    ```

#### Example:
Let's say we want to determine if a user can send a message based on whether they are a friend.

```python
is_friend = True

# Using ternary operator
can_message = "Message allowed" if is_friend else "Not allowed to message"

print(can_message)
# Output: Message allowed
```

### Explanation:
- **Condition**: `is_friend`
- **Value if True**: `"Message allowed"`
- **Value if False**: `"Not allowed to message"`

The ternary operator checks the condition (`is_friend`). If it's `True`, it evaluates to `"Message allowed"`. Otherwise, it evaluates to `"Not allowed to message"`.

### Practical Example:
Consider a scenario where we check if a user is a friend and allow messaging accordingly.

```python
is_friend = False

# Using ternary operator
can_message = "Message allowed" if is_friend else "Not allowed to message"

print(can_message)
# Output: Not allowed to message
```

### Summary:
- **Ternary Operators**: Provide a concise way to write conditional statements.
- **Syntax**: `value_if_true if condition else value_if_false`
- **Use Case**: Useful for simple conditions to make code cleaner and more readable.



### Notes on Short Circuiting in Python

**Short Circuiting** is a concept in Python that makes conditional logic more efficient by stopping the evaluation of expressions as soon as the result is determined.

#### Key Points:
1. **Short Circuiting**: Occurs when the Python interpreter stops evaluating an expression as soon as it knows the result.
2. **Logical Operators**: `and` and `or` are used in short circuiting.

#### Example:
```python
is_friend = True
is_user = True

# Using 'and' operator
if is_friend and is_user:
    print("Best friends forever")

# Output: Best friends forever
```

### Using `or` Operator:
- **`or` Operator**: Evaluates to `True` if at least one condition is true. If the first condition is true, the second condition is not evaluated.

```python
is_friend = True
is_user = False

if is_friend or is_user:
    print("Best friends forever")

# Output: Best friends forever
```

### Performance:
- **Efficiency**: `or` is more efficient in cases where the first condition is true because it avoids evaluating the second condition.
- **Example**:
    ```python
    is_friend = True
    is_user = False

    if is_friend or is_user:
        print("Best friends forever")
    ```

### Short Circuiting with `and`:
- **`and` Operator**: Evaluates to `True` only if both conditions are true. If the first condition is false, the second condition is not evaluated.

```python
is_friend = False
is_user = True

if is_friend and is_user:
    print("Best friends forever")
else:
    print("Not best friends")

# Output: Not best friends
```

### Summary:
- **Short Circuiting**: Improves efficiency by stopping evaluation once the result is known.
- **Logical Operators**: `and` and `or` are used for short circuiting.
- **Efficiency**: `or` stops evaluating if the first condition is true; `and` stops if the first condition is false.



---

### Logical Operators

Logical operators are essential for conditional logic in programming. They allow us to perform logic between two or more conditions.

#### Common Logical Operators:
1. **Greater than (>)**
2. **Less than (<)**
3. **Equal to (==)**
4. **Not equal to (!=)**
5. **Greater than or equal to (>=)**
6. **Less than or equal to (<=)**
7. **And (&&)**
8. **Or (||)**
9. **Not (!)**

#### Examples:

1. **Greater than (>)**
   ```python
   print(4 > 5)  # Output: False
   ```

2. **Less than (<)**
   ```python
   print(4 < 5)  # Output: True
   ```

3. **Equal to (==)**
   ```python
   print(4 == 5)  # Output: False
   ```

4. **Not equal to (!=)**
   ```python
   print(4 != 5)  # Output: True
   ```

5. **Greater than or equal to (>=)**
   ```python
   print(4 >= 4)  # Output: True
   ```

6. **Less than or equal to (<=)**
   ```python
   print(4 <= 5)  # Output: True
   ```

7. **And (&&)**
   ```python
   print((4 < 5) && (5 < 6))  # Output: True
   ```

8. **Or (||)**
   ```python
   print((4 > 5) || (5 < 6))  # Output: True
   ```

9. **Not (!)**
   ```python
   print(not (4 > 5))  # Output: True
   ```

#### Important Notes:
- **Double Equals (==)**: Used for comparison, not assignment.
  ```python
  print(4 == 5)  # Output: False
  ```

- **Assignment Operator (=)**: Used to assign values to variables.
  ```python
  x = 5
  ```

- **Short-Circuiting**: In logical expressions, evaluation stops as soon as the result is determined.
  ```python
  print((4 > 5) && (5 < 6))  # Output: False (stops after first condition)
  ```

- **Case Sensitivity**: Comparing strings can be case-sensitive.
  ```python
  print('a' > 'A')  # Output: True
  ```

#### Exercise:
Try to understand why `'a' > 'A'` evaluates to `True` by researching string comparison in Python.

---


### Notes on Equality Checks in Python

In this video, the focus is on understanding equality checks in Python, specifically using `==` and `is`.

#### Key Points:

1. **Equality (`==`)**:
   - Checks if the values of two objects are equal.
   - Converts types if necessary to compare values.
   - Examples:
     ```python
     print(True == 1)  # Output: True
     print("" == 1)    # Output: False
     print([] == 1)    # Output: False
     print(10 == 10.0) # Output: True
     print([] == [])   # Output: True
     ```

2. **Identity (`is`)**:
   - Checks if two objects refer to the same memory location.
   - Does not convert types.
   - Examples:
     ```python
     print(True is 1)  # Output: False
     print("" is 1)    # Output: False
     print([] is 1)    # Output: False
     print(10 is 10.0) # Output: False
     print([] is [])   # Output: False
     ```

#### Detailed Explanation:

- **Equality (`==`)**:
  - **True == 1**: Evaluates to `True` because `True` is converted to `1` (boolean to integer conversion).
  - **"" == 1**: Evaluates to `False` because an empty string is considered `False` and does not equal `1`.
  - **[] == 1**: Evaluates to `False` because an empty list is considered `False` and does not equal `1`.
  - **10 == 10.0**: Evaluates to `True` because `10` (integer) is equal to `10.0` (float).
  - **[] == []**: Evaluates to `True` because both lists are empty and have the same value.

- **Identity (`is`)**:
  - **True is 1**: Evaluates to `False` because `True` and `1` are not the same object in memory.
  - **"" is 1**: Evaluates to `False` because an empty string and `1` are not the same object in memory.
  - **[] is 1**: Evaluates to `False` because an empty list and `1` are not the same object in memory.
  - **10 is 10.0**: Evaluates to `False` because `10` (integer) and `10.0` (float) are not the same object in memory.
  - **[] is []**: Evaluates to `False` because each empty list is a different object in memory.

#### Important Concepts:

- **Type Conversion**:
  - Python automatically converts types to compare values when using `==`.
  - Example:
    ```python
    print(True == 1)  # Output: True
    ```

- **Memory Location**:
  - `is` checks if two variables point to the same memory location.
  - Example:
    ```python
    a = []
    b = []
    print(a is b)  # Output: False
    ```

#### Exercise:
Try changing the equality checks to identity checks (`is`) and observe the differences in output.

---


