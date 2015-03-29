# 1.6. Quick Sort
QuickSort is also a **Divide And Conquer** algorithm with a performance of $$O(n * log(n))$$, however in the worst case this becomes $$O(n^2)$$.

## 1.6.1. How
We start by picking an element which is called the **pivot**, then we will rearrange the array so that every element smaller than the pivot will be on the left of the pivot and all elements larger than the pivot will be on the right. this operation is called the **partitioning**.

Now we just recursively apply the above steps to the sub array of elements.

![Quicksort](https://lh4.googleusercontent.com/-YOOXyghASUo/VQWuKwYPQlI/AAAAAAAAKjs/MQWXdyPO6FQ/s0/Screen+Shot+2015-03-15+at+17.05.54.png "Quick Sort")

Take the following array:

	9 0 8 3 5 4 2 1 6 7

We pick our pivot (the middle element, don't forget the rounding of course), the brackets show the index points.

	[9] 0 8 3 (5) 4 2 1 6 [7]

We start from index 0 and index arraySize - 1, we compare the values and swap if needed. So here we have 9 and 7, **9 > 5 < 7** so we increase the index by 1 for the right side, because 7 is in it's correct spot.

	[9] 0 8 3 (5) 4 2 1 [6] 7

Again **9 > 5 < 6**, so we increment the right side index

	[9] 0 8 3 (5) 4 2 [1] 6 7

We now see that **9 > 5 > 1**, which means we should swap 1 and 9. We can also increment the left and the right index.

	1 [0] 8 3 (5) 4 [2] 9 6 7

**0 < 5 > 2**, increment left side.

	1 0 [8] 3 (5) 4 [2] 9 6 7

**8 > 5 < 2**, swap

	1 0 2 [3] (5) [4] 8 9 6 7

**3 < 5 > 4**, increment the left index. This will now become our pivot! so this is the last step.

	1 0 2 3 [(5)] [4] 8 9 6 7

**5 > 4**, swap

	1 0 2 3 4 (5) 8 9 6 7

We now have 2 sub arrays, a left one and a right one, run this method recursively on these 2 sub arrays.

On the end we will have our sorted array:

	0 1 2 3 4 5 6 7 8 9

For the implementation check paragraph `§6.4`.

## 1.6.2. Advantages and Disadvantages

**Advantages**
- Fast overall

**Disadvantages**
- Not stable
- $$O(lg(n))$$ extra space
- $$\Theta(n^2))$$ performance in the worst case
- Not adaptive

## 1.6.3. Performance
|Worst Case|Average Case|Best Case|
|-|-|-|
|O(n<sup>2</sup>|O(n log n)|O(n log n)|

Note that the performance goes towards $$O(n)$$ using a three-way partition and equal keys.

## 1.6.4. Implementation
QuickSort has 2 main steps, the partition step and the recursion step.

In the partition step we will put every element smaller than the pivot at the left, and every element larger than the pivot at the right.

Then we will recursively call our QuickSort method till we got a sorted array.

### 1.6.4.1 C++ Code

	void quick_sort(vector<T> &v, int leftIdx, int rightIdx) const {
        // Set indexes that we can move
        int i = leftIdx;
        int j = rightIdx;

        // Find pivot
        int pivot = v[(leftIdx + rightIdx) / 2];

        // Swap container
        int tmp;

        // PARTITION
        while (i <= j) {
            // Move indexes till we got a swap point.
            while (v[i] < pivot)
                i++;

            while (v[j] > pivot)
                j--;

            // Swap
            if (i <= j) {
                tmp = v[i];
                v[i] = v[j];
                v[j] = tmp;

                // We swapped so move the indexes
                i++;
                j--;
            }
        }

        // RECURSION as long as we are not at the end
        if (leftIdx < j)
            quick_sort(v, leftIdx, j);

        if (rightIdx > i) {
            quick_sort(v, i, rightIdx);
        }
    }


## 1.6.5. Benchmark
|&nbsp;| 100 | 1.000 | 10.000 | 100.000 | 1.000.000
|-|-|-|-|-|-|
|Random Elements|8e-06|0.000105|0.001301|0.015583|0.179599
|Ascending Elements|3e-06|2.6e-05|0.000329|0.004379|0.043418
|Descending Elements|3e-06|2.7e-05|0.000354|0.004304|0.046504

## 1.6.6. Conclusion
QuickSort is fun to implement and is really fast when we do not hit the worst case scenario, because we are able to prevent hitting this scenario this is a commonly used sorting algorithm. It is so common that the STL library has implemented this as `qsort`.

There is also a very famous variant on QuickSort called Three Way Pivot QuickSort, this algorithm is faster since 2009 and is also implemented in Java 7.
