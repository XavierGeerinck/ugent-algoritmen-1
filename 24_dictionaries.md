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
Compare the key we are looking for with the key of the middle element. Now we look further in the left or right sub table. This gives us a performance of $$O(lg(n))$$.

```c++
int binary_search(int s, const vector<int> &v) {
    // v is not empty
    // if found, return index
    // if not found, return -1
    int l = 0, r = v.size() - 1;
    
    // Invariant: v[l] <= s <= v[r]
    while (l < r) {
        int m = l + (r - l) / 2; // l <= m < r
        
        if (s <= v[m]) 
            r = m;
        else
            l = m + 1;
    }
    
    return s == v[l] ? l : -1;
}
```

### 2.9.4.3. Interpolating Search