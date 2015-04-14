# 2.10. HashTables
A hash table is a really efficient key-value store, it will hash the key and place the value at this hash in a table. Do note that this method can cause collisions. This can happen due to our hashing mechanism being of a fixed length while our key is of a variable length. This is why every HashTable also has to have a method to catch collisions.


![](315px-Hash_table_3_1_1_0_1_0_0_SP.svg.png)