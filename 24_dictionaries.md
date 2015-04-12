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
We first search for the key and then we can just remove this line. This results in a performance of O(1) for removing. Note that searching has a separate performance.

## 2.9.3. Table ordered by search chance
Here we will order the table by the chance of searching, we can do this when we know the different chances of a key being searched. This will improve our performance.

## 2.9.4. Ordered table
We order the table, for example in top down order. We now have several operations:

### 2.9.4.1. Sequential Search
This method is faster if we want to know if an element appears in the table, this because when a value is bigger then our current then we can stop searching. This method however is not faster if we found the value, which is why we use the other methods more.

### 2.9.4.2. Binary Search
