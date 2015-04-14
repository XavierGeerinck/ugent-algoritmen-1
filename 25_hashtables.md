# 2.10. HashTables
A hash table is a really efficient key-value store, it will hash the key and place the value at this hash in a table. Do note that this method can cause collisions. This can happen due to our hashing mechanism being of a fixed length while our key is of a variable length. This is why every HashTable also has to have a method to catch collisions.


![](315px-Hash_table_3_1_1_0_1_0_0_SP.svg.png)

## 2.10.1. Conflict Catching
### 2.10.1.1. Separate Chaining
In this method we will use some sort of list of entries with the same index.

### 2.10.1.2. Separate Chaining with linked lists
We will combine every key that fit into the same bucket in a LinkedList. Every ListNode has a key with the designated information.

![](450px-Hash_table_5_0_1_1_1_1_1_LL.svg.png)

##### 2.10.1.2.1. Searching
We can search by the hash value of the key, we now end up in the LinkedList containing the value that we want. If we have bad luck, then we find ourselves in a LinkedList where all the keys are collected because they have the same hash ($$O(n)$$). However in the average case when our hash is of a good quality this won't happen. We can speak of a good quality when our length of the list is $$n/m$$. This is the expectation of the individual List Length. We call this $$n/m$$ equation the load factor $$\Alpha$$.