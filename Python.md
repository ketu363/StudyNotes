

### **Actions on Lists in Python**

1. **Built-in Functions:**
   - **Length Function (`len()`):**
     - **Usage:** `len(basket)`
     - **Explanation:** Returns the number of items in the list. For example, if `basket = [1, 2, 3, 4, 5]`, then `len(basket)` returns 5.

2. **List Methods:**
   - **Append (`append()`):**
     - **Usage:** `basket.append(100)`
     - **Explanation:** Adds an item to the end of the list. This method modifies the list in place and does not return a new list. For example, if `basket = [1, 2, 3, 4, 5]`, then `basket.append(100)` changes `basket` to `[1, 2, 3, 4, 5, 100]`.
   - **Insert (`insert()`):**
     - **Usage:** `basket.insert(4, 100)`
     - **Explanation:** Adds an item at a specified index. This method also modifies the list in place. For example, if `basket = [1, 2, 3, 4, 5]`, then `basket.insert(4, 100)` changes `basket` to `[1, 2, 3, 4, 100, 5]`.
   - **Extend (`extend()`):**
     - **Usage:** `basket.extend([100, 101])`
     - **Explanation:** Adds multiple items to the end of the list. This method modifies the list in place. For example, if `basket = [1, 2, 3, 4, 5]`, then `basket.extend([100, 101])` changes `basket` to `[1, 2, 3, 4, 5, 100, 101]`.

3. **Removing Methods:**
   - **Pop (`pop()`):**
     - **Usage:** `basket.pop(0)`
     - **Explanation:** Removes and returns an item at a specified index. If no index is provided, it removes the last item. For example, if `basket = [1, 2, 3, 4, 5]`, then `basket.pop(0)` removes and returns `1`, changing `basket` to `[2, 3, 4, 5]`.
   - **Remove (`remove()`):**
     - **Usage:** `basket.remove(4)`
     - **Explanation:** Removes the first occurrence of a specified value. This method modifies the list in place. For example, if `basket = [1, 2, 3, 4, 5]`, then `basket.remove(4)` changes `basket` to `[1, 2, 3, 5]`.
   - **Clear (`clear()`):**
     - **Usage:** `basket.clear()`
     - **Explanation:** Removes all items from the list, effectively emptying it. For example, if `basket = [1, 2, 3, 4, 5]`, then `basket.clear()` changes `basket` to `[]`.

These methods are essential for manipulating lists in Python, allowing you to add, insert, extend, and remove items efficiently.

### **String Methods in Python**

1. **Index (`index()`):**
   - **Usage:** `basket.index('D')`
   - **Explanation:** Finds the index of a specified value in the list. You can also specify a start and stop index to narrow the search. Example: `basket.index('D', 0, 4)` returns the index of 'D' within the specified range.

2. **Keyword (`in`):**
   - **Usage:** `'D' in basket`
   - **Explanation:** Checks if a specified value exists in the list. Returns `True` if the value is found, otherwise `False`. Example: `'D' in basket` returns `True` if 'D' is in the list.

3. **Count (`count()`):**
   - **Usage:** `basket.count('D')`
   - **Explanation:** Counts the number of occurrences of a specified value in the list. Example: `basket.count('D')` returns the number of times 'D' appears in the list.

These methods help in efficiently searching and counting items in a list, enhancing your ability to manipulate and analyze data in Python.

### **More List Methods in Python**

1. **Sort (`sort()`):**
   - **Usage:** `basket.sort()`
   - **Explanation:** Sorts the list in place, modifying the original list. Example: `basket.sort()` changes `basket` to a sorted order.

2. **Sorted (`sorted()`):**
   - **Usage:** `sorted(basket)`
   - **Explanation:** Returns a new sorted list without modifying the original list. Example: `sorted(basket)` returns a new sorted list, leaving `basket` unchanged.

3. **Copy (`copy()`):**
   - **Usage:** `new_basket = basket.copy()`
   - **Explanation:** Creates a copy of the list. Example: `new_basket = basket.copy()` creates a new list `new_basket` that is a copy of `basket`.

4. **Reverse (`reverse()`):**
   - **Usage:** `basket.reverse()`
   - **Explanation:** Reverses the order of the list in place. Example: `basket.reverse()` changes the order of items in `basket` to the reverse order.

These methods enhance your ability to manipulate lists by sorting, copying, and reversing them efficiently.





