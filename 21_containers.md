# 2. Containers
# 2.1. Table

* Is directly supported by the internal memory of a computer
* Has a fixed size
* Adding elements is O(1), but at a full table the performance is worse (but amortised this is still O(1)).

# 2.2. List

* Variable size
* Nodes can be fragmented in the memory.
* Only the ends are easy to reach.
* Closing list has multiple possibilities:
    *  nullpointer as last element
    *  pointer to temp node that points to itself.
    *  pointer to temp node that points to first node (ring list).

# 2.3. Stack

* Several operations:
    * push (add on top)
    * pop (remove from top, last in first out (LIFO))
    * isEmpty (Test if empty)
    * top (get top element)
* We can use a linked list or normal list to create this.
* Performance is O(1) for both the implementations.
* One of the most used structures.

# 2.4. Queue

* Several operations:
    * enqueue (add)
    * dequeue (remove, first in first our principle (FIFO))
    * isEmpty
* Implementation uses a table:
    * Remove and add elements at the same side
    * 2 pointers, one to head and one to tail
    * when one of the indexes reaches one end of the table, start from the beginning.
* Implementation uses a linked list:
    * Add at the end of the list
    * Remove the front
    * no problems with indexes and table size.
* Performance is O(1) for both.

# 2.5. Deque

* Combination of stack and queue.
* We can add at both sides

# 2.6. Priority Queue

* Several operations:
    * Add
    * Remove
    * isEmpty
* Different implementations:
    * Sorted table: Sort by priority, highest priority is O(1), smallest is O(n)
    * Unsorted table: Adding is O(1), removing is O(n).
    * Binary Tree: Adding and removing is O(lg(n)), biggest priority is the root.
    * D-heap: tree with d childs, height is $log_d(n)$. Adding is $lg(d)$ and descending is $O(d*log_d(n))$.
    * Other: Sometimes needed to merge queues.

# 2.7. Tree