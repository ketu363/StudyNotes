###  Sets

#### Introduction to Sets
- **Final Data Type**: Sets are the last main data type in Python.
- **Unordered Collections**: Sets are unordered collections of unique objects.
- **Unique Items**: Sets do not allow duplicate values.

#### Creating and Using Sets
- **Creating a Set**: Use curly brackets to create a set, e.g., `my_set = {1, 2, 3, 4, 5}`.
- **Adding Items**: Add items to a set using the `add` method:
  ```python
  my_set.add(100)
  my_set.add(2)  # 2 will not be added again
  ```
- **No Duplicates**: If you try to add a duplicate item, it will not be added.

#### Accessing Set Items
- **No Indexing**: Sets do not support indexing. You cannot access items by their position.
- **Checking Membership**: Use the `in` keyword to check if an item exists in a set:
  ```python
  print(1 in my_set)  # Output: True
  ```

#### Converting Lists to Sets
- **Removing Duplicates**: Convert a list to a set to remove duplicates:
  ```python
  my_list = [1, 2, 3, 4, 5, 5]
  my_set = set(my_list)
  print(my_set)  # Output: {1, 2, 3, 4, 5}
  ```
- **Use Case**: Useful for ensuring unique usernames or email addresses.

#### Set Methods
- **Copying a Set**: Create a copy of a set:
  ```python
  new_set = my_set.copy()
  ```
- **Clearing a Set**: Remove all items from a set:
  ```python
  my_set.clear()
  print(my_set)  # Output: set()
  ```

#### Built-in Functions
- **Length Function**: Determine the number of unique items in a set:
  ```python
  print(len(my_set))  # Output: 5
  ```

#### Summary
- **Sets vs Dictionaries**: Sets are similar to dictionaries but only contain values, not key-value pairs.
- **Unique and Unordered**: Sets are unique and unordered collections.
- **Practical Applications**: Useful for tasks requiring unique collections, such as filtering duplicates.



###  Set Methods

#### Introduction to Set Methods
- **Overview**: Sets have several methods that are useful for comparing and manipulating sets.
- **Example Sets**: 
  ```python
  my_set = {1, 2, 3, 4, 5}
  your_set = {4, 5, 6, 7, 8, 9, 10}
  ```

#### Difference
- **Purpose**: Finds the difference between two sets.
- **Usage**:
  ```python
  difference = my_set.difference(your_set)
  print(difference)  # Output: {1, 2, 3}
  ```
  - **Explanation**: Shows items in `my_set` that are not in `your_set`.

#### Discard
- **Purpose**: Removes a specified element from the set.
- **Usage**:
  ```python
  my_set.discard(5)
  print(my_set)  # Output: {1, 2, 3, 4}
  ```

#### Difference Update
- **Purpose**: Removes all elements of another set from this set.
- **Usage**:
  ```python
  my_set.difference_update(your_set)
  print(my_set)  # Output: {1, 2, 3}
  ```

#### Intersection
- **Purpose**: Finds the common elements between two sets.
- **Usage**:
  ```python
  intersection = my_set.intersection(your_set)
  print(intersection)  # Output: {4, 5}
  ```

#### Is Disjoint
- **Purpose**: Checks if two sets have no elements in common.
- **Usage**:
  ```python
  disjoint = my_set.isdisjoint(your_set)
  print(disjoint)  # Output: False
  ```

#### Union
- **Purpose**: Combines all elements from both sets, removing duplicates.
- **Usage**:
  ```python
  union = my_set.union(your_set)
  print(union)  # Output: {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
  ```
  - **Shorthand**: 
    ```python
    union = my_set | your_set
    ```

#### Is Subset
- **Purpose**: Checks if all elements of one set are in another set.
- **Usage**:
  ```python
  subset = my_set.issubset(your_set)
  print(subset)  # Output: False
  ```

#### Is Superset
- **Purpose**: Checks if a set contains all elements of another set.
- **Usage**:
  ```python
  superset = my_set.issuperset(your_set)
  print(superset)  # Output: False
  ```

#### Practical Tips
- **No Need to Memorize**: It's more important to understand that these methods exist and how to find them when needed.
- **Real-Life Programming**: In practice, programmers often refer to documentation or search online for specific methods.

#### Summary
- **Sets**: Unordered collections of unique items.
- **Methods**: Useful for comparing and manipulating sets.
- **Programming Tip**: Focus on understanding concepts rather than memorizing methods.

