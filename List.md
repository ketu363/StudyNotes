### **Actions on Lists in Python**

1. **Built-in Functions:**
   - **Length Function (`len()`):**
     - **Usage:** `len(basket)`
     - **Explanation:** Returns the number of items in the list.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       print(len(basket))  # Output: 5
       ```

2. **List Methods:**
   - **Append (`append()`):**
     - **Usage:** `basket.append(100)`
     - **Explanation:** Adds an item to the end of the list. This method modifies the list in place and does not return a new list.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       basket.append(100)
       print(basket)  # Output: [1, 2, 3, 4, 5, 100]
       ```
   - **Insert (`insert()`):**
     - **Usage:** `basket.insert(4, 100)`
     - **Explanation:** Adds an item at a specified index. This method also modifies the list in place.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       basket.insert(4, 100)
       print(basket)  # Output: [1, 2, 3, 4, 100, 5]
       ```
   - **Extend (`extend()`):**
     - **Usage:** `basket.extend([100, 101])`
     - **Explanation:** Adds multiple items to the end of the list. This method modifies the list in place.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       basket.extend([100, 101])
       print(basket)  # Output: [1, 2, 3, 4, 5, 100, 101]
       ```

3. **Removing Methods:**
   - **Pop (`pop()`):**
     - **Usage:** `basket.pop(0)`
     - **Explanation:** Removes and returns an item at a specified index. If no index is provided, it removes the last item.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       item = basket.pop(0)
       print(item)    # Output: 1
       print(basket)  # Output: [2, 3, 4, 5]
       ```
   - **Remove (`remove()`):**
     - **Usage:** `basket.remove(4)`
     - **Explanation:** Removes the first occurrence of a specified value. This method modifies the list in place.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       basket.remove(4)
       print(basket)  # Output: [1, 2, 3, 5]
       ```
   - **Clear (`clear()`):**
     - **Usage:** `basket.clear()`
     - **Explanation:** Removes all items from the list, effectively emptying it.
     - **Example:** 
       ```python
       basket = [1, 2, 3, 4, 5]
       basket.clear()
       print(basket)  # Output: []
       ```

These methods are essential for manipulating lists in Python, allowing you to add, insert, extend, and remove items efficiently.

### **String Methods in Python**

1. **Index (`index()`):**
   - **Usage:** `basket.index('D')`
   - **Explanation:** Finds the index of a specified value in the list. You can also specify a start and stop index to narrow the search.
   - **Example:** 
     ```python
     basket = ['a', 'b', 'c', 'd', 'e']
     index = basket.index('d')
     print(index)  # Output: 3
     ```

2. **Keyword (`in`):**
   - **Usage:** `'D' in basket`
   - **Explanation:** Checks if a specified value exists in the list. Returns `True` if the value is found, otherwise `False`.
   - **Example:** 
     ```python
     basket = ['a', 'b', 'c', 'd', 'e']
     print('d' in basket)  # Output: True
     print('x' in basket)  # Output: False
     ```

3. **Count (`count()`):**
   - **Usage:** `basket.count('D')`
   - **Explanation:** Counts the number of occurrences of a specified value in the list.
   - **Example:** 
     ```python
     basket = ['a', 'b', 'c', 'd', 'd', 'e']
     count = basket.count('d')
     print(count)  # Output: 2
     ```

These methods help in efficiently searching and counting items in a list, enhancing your ability to manipulate and analyze data in Python.

### **More List Methods in Python**

1. **Sort (`sort()`):**
   - **Usage:** `basket.sort()`
   - **Explanation:** Sorts the list in place, modifying the original list.
   - **Example:** 
     ```python
     basket = ['e', 'd', 'c', 'b', 'a']
     basket.sort()
     print(basket)  # Output: ['a', 'b', 'c', 'd', 'e']
     ```

2. **Sorted (`sorted()`):**
   - **Usage:** `sorted(basket)`
   - **Explanation:** Returns a new sorted list without modifying the original list.
   - **Example:** 
     ```python
     basket = ['e', 'd', 'c', 'b', 'a']
     sorted_basket = sorted(basket)
     print(sorted_basket)  # Output: ['a', 'b', 'c', 'd', 'e']
     print(basket)         # Output: ['e', 'd', 'c', 'b', 'a']
     ```

3. **Copy (`copy()`):**
   - **Usage:** `new_basket = basket.copy()`
   - **Explanation:** Creates a copy of the list.
   - **Example:** 
     ```python
     basket = ['a', 'b', 'c', 'd', 'e']
     new_basket = basket.copy()
     print(new_basket)  # Output: ['a', 'b', 'c', 'd', 'e']
     ```

4. **Reverse (`reverse()`):**
   - **Usage:** `basket.reverse()`
   - **Explanation:** Reverses the order of the list in place.
   - **Example:** 
     ```python
     basket = ['a', 'b', 'c', 'd', 'e']
     basket.reverse()
     print(basket)  # Output: ['e', 'd', 'c', 'b', 'a']
     ```

These methods enhance your ability to manipulate lists by sorting, copying, and reversing them efficiently.

### **Useful Tricks with Lists in Python**

1. **Length (`len()`):**
   - **Usage:** `len(basket)`
   - **Explanation:** Returns the number of items in the list.
   - **Example:** 
     ```python
     basket = [1, 2, 3, 4, 5, 6, 7]
     print(len(basket))  # Output: 7
     ```

2. **Reverse with List Slicing:**
   - **Usage:** `basket[::-1]`
   - **Explanation:** Reverses the list by creating a new list.
   - **Example:** 
     ```python
     basket = ['a', 'b', 'c', 'd', 'e']
     reversed_basket = basket[::-1]
     print(reversed_basket)  # Output: ['e', 'd', 'c', 'b', 'a']
     ```

3. **Range (`range()`):**
   - **Usage:** `list(range(100))`
   - **Explanation:** Generates a list of numbers from 0 to 99.
   - **Example:** 
     ```python
     numbers = list(range(100))
     print(numbers)  # Output: [0, 1, 2, ..., 99]
     ```

4. **Join (`join()`):**
   - **Usage:** `' '.join(['Hi', 'my', 'name', 'is', 'Jojo'])`
   - **Explanation:** Combines list items into a single string.
   - **Example:** 
     ```python
     words = ['Hi', 'my', 'name', 'is', 'Jojo']
     sentence = ' '.join(words)
     print(sentence)  # Output: "Hi my name is Jojo"
     ```

These tricks are commonly used in Python to manipulate lists efficiently. They help you perform operations like finding the length, reversing the order, generating sequences, and combining elements into a string.

### **List Unpacking in Python**

**List Unpacking:**
- **Definition:** Assigns individual variables to items in a list.
- **Basic Example:**
  ```python
  basket = [1, 2, 3]
  a, b, c = basket
  print(a)  # Output: 1
  print(b)  # Output: 2
  print(c)  # Output: 3
 
