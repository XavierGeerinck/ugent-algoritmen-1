# Backtracking with Trees
Backtracking can be used for many practical problems. Many of these problems require a bruteforce method to solve them. This algorithm is designed so that we will try every possibility once.

Too illustrate the used method see the following code:

```c++
void backtracking() {
    int k = 1;
    find V1;
    
    while (k > 0) {
        while (Vk not empty) {
            wk = next element from Vk;
            remove wk from Vk;
            
            if (<w1,w2,...,wk> is a solution) {
                write <w1,w2,...,wk>;
            }
            
            k++; // next
            find Vk; // is empty if k > n
        }
        
        k--; // backtracking
    }
}
```

Because we can get huge trees, even with small n. We decide to reduce the nodes that we will check (pruning). This can lead to huge performance gains. To do this we have several methods:

* Sort variables: The order can have a huge impact, that's why we put the variables in ascending order.
* Sort values: This order has no impact on the size of the tree, but it has an impact on the order that is used to search. If we want just one solution then we should use this. If we put this in descending order, then we will get the easiest values first.
* Backjumping: Instead of going back to the previous variable, we go back to the variable that made the solution impossible.
* Forward Checking: When assigning a new value we check if there still remains 1 possible value for the other variables.
* Symmetries: Remove the subtrees that will come to the same solution.


## Example: Solving a sudoku with backtracking
A famous example of using backtracking is with a sudoku in pseudocode:

    Find row, col of an unassigned cell
    If there is none, return true
    For digits from 1 to 9
        a) If there is no conflict for digit at row, col assign digit to row, col and recursively try fill in rest of grid.
        b) If recursion successful, return true
        c) Else, remove digit and try another
    If all digits have been tried and nothing worked, return false
    
> Reference: http://www.geeksforgeeks.org/backtracking-set-7-suduku/