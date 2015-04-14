# 2.10. HashTables
A hash table is a really efficient key-value store, it will hash the key and place the value at this hash in a table. Do note that this method can cause collisions. This can happen due to our hashing mechanism being of a fixed length while our key is of a variable length. This is why every HashTable also has to have a method to catch collisions.


![](315px-Hash_table_3_1_1_0_1_0_0_SP.svg.png)

# 2.10.1. Conflict Catching
# 2.10.1.1. Separate Chaining
In this method we will use some sort of list of entries with the same index.

# 2.10.1.2. Separate Chaining with linked lists
We use LinkedLists here, see  the picture for how this works.


