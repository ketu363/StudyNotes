### Notes on Loops in Python

Loops are a powerful feature in programming that allow us to execute lines of code repeatedly. This is particularly useful for tasks that need to be performed multiple times.

#### Key Points:

1. **Concept of Loops**:
   - Loops enable running code multiple times.
   - Useful for repetitive tasks that machines excel at.

2. **Types of Loops**:
   - **For Loops**: Used to iterate over a sequence (e.g., list, string, set, tuple).

#### Creating a For Loop:
- **Syntax**:
  ```python
  for item in iterable:
      # Code to execute
  ```

- **Example**:
  ```python
  for item in "Zero to Mastery":
      print(item)
  ```
  This prints each character in the string "Zero to Mastery".

#### Iterables:
- **Strings**:
  ```python
  for char in "Hello":
      print(char)
  ```

- **Lists**:
  ```python
  for num in [1, 2, 3, 4, 5]:
      print(num)
  ```

- **Sets**:
  ```python
  for num in {1, 2, 3, 4, 5}:
      print(num)
  ```

- **Tuples**:
  ```python
  for num in (1, 2, 3, 4, 5):
      print(num)
  ```

#### Nested Loops:
- **Example**:
  ```python
  for item in [1, 2, 3]:
      for letter in ['A', 'B', 'C']:
          print(item, letter)
  ```
  This prints combinations of numbers and letters.

#### Indentation:
- Indentation is crucial in Python to define the scope of loops.
  ```python
  for num in [1, 2, 3]:
      print(num)  # Inside the loop
  print("Done")  # Outside the loop
  ```

#### Practical Use:
- Loops are useful for tasks like processing items in a list, performing repetitive calculations, etc.

#### Exercise:
Try creating a nested loop with different iterables and observe the output.

---

### Notes on Iterables in Python

An **iterable** is an object or collection that can be looped over, meaning you can go through each item one by one. This concept is fundamental in Python and other programming languages.

#### Key Points:

1. **Definition of Iterable**:
   - An iterable is any object that can be iterated over.
   - Common iterables include lists, dictionaries, tuples, sets, and strings.

2. **Iterating Over Different Types of Iterables**:
   - **Lists**:
     ```python
     for item in [1, 2, 3, 4, 5]:
         print(item)
     ```
   - **Tuples**:
     ```python
     for item in (1, 2, 3, 4, 5):
         print(item)
     ```
   - **Sets**:
     ```python
     for item in {1, 2, 3, 4, 5}:
         print(item)
     ```
   - **Strings**:
     ```python
     for char in "Hello":
         print(char)
     ```

3. **Iterating Over Dictionaries**:
   - **Keys**:
     ```python
     user = {"name": "Gollum", "age": 5000, "can_swim": False}
     for key in user:
         print(key)
     ```
   - **Values**:
     ```python
     for value in user.values():
         print(value)
     ```
   - **Items (key-value pairs)**:
     ```python
     for key, value in user.items():
         print(key, value)
     ```

4. **Tuple Unpacking**:
   - Simplifies accessing key-value pairs in dictionaries.
   - Example:
     ```python
     for key, value in user.items():
         print(f"Key: {key}, Value: {value}")
     ```

5. **Non-Iterable Objects**:
   - Not all objects are iterable. For example, integers are not iterable.
   - Example:
     ```python
     for item in 50:
         print(item)  # Raises TypeError: 'int' object is not iterable
     ```

#### Important Methods for Dictionaries:
- **items()**: Returns key-value pairs as tuples.
- **values()**: Returns values of the dictionary.
- **keys()**: Returns keys of the dictionary.

#### Exercise:
Try iterating over different types of iterables and use the dictionary methods to access keys, values, and items.

---



