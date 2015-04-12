# 2.9. Dictionaries
Dictionaries are structures that make it easy to find values based on keys.

## 2.9.1. Direct Addressable Table
We can use a key to access and set a value in a dictionary. If multiple values have the same key then we will use a LinkedList.

Every operation here is O(1).

## 2.9.2. Unordered table.
### 2.9.2.1. Searching
We perform a linear search over the complete dictionary to find the value we are looking for. This has a performance of O(n).

### 2.9.2.2. Adding
This happens on the back of the dictionary, so the performance is O(1).
### 2.9.2.3. Removing

