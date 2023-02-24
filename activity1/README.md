# Activities

## Task 1

- Refer to the following link. Discuss how Merge-sort works:
  https://opendsa-server.cs.vt.edu/OpenDSA/AV/Sorting/mergesortAV.html

  // Merge-sort is a sorting algorithm that works by dividing an array into smaller subarrays, sorting each subarray and then merging the sorted halves together. This operation lends itself to a simple recursive sort method known as mergesort, which involves splitting the list in half, sorting the halves and then merging them back together.

- Merge-sort Practice. Refer to the following link. Merge the two sub-arrays into the larger array.
  https://opendsa-server.cs.vt.edu/OpenDSA/Exercises/Sorting/MergesortMergePRO.html

 

## Task 2

- Refer to the following link. Discuss how Quick-sort works:  
  https://opendsa-server.cs.vt.edu/OpenDSA/AV/Sorting/quicksortAV.html
- Quick-sort Practice. Refer to the following link. Partition the array using quicksort.
  https://opendsa-server.cs.vt.edu/OpenDSA/Exercises/Sorting/QuicksortPartitPRO.html

// Select a pivot element: The pivot element is selected from the array and is used as a reference point to divide the array into two sub-arrays. The pivot element can be chosen randomly or it can be the first or the last element of the array.

Partition the array: The elements in the array are rearranged such that all elements that are less than the pivot element are placed to its left, and all elements greater than the pivot are placed to its right.

Recursively sort the sub-arrays: The two sub-arrays created in the previous step are then sorted recursively using the same QuickSort algorithm. This is done until the sub-arrays are reduced to their individual elements, at which point they are sorted.

Combine the sub-arrays and the pivot element: After the sub-arrays are sorted, they are combined along with the pivot element to produce the final sorted array.

## Task 3

- The following snippet is from `./src/quicksort.cpp` lines 32-43. Discuss in groups how the code works:

```cpp
void quickSort(int arr[], int low, int high)
{
    if (low < high)
    {
        //partition the array
        int pivot = partition(arr, low, high);

        //sort the sub arrays independently
        quickSort(arr, low, pivot - 1);
        quickSort(arr, pivot + 1, high);
    }
}
```
// This code implements the quicksort algorithm, which is a common sorting algorithm that works by partitioning an array around a pivot value and recursively sorting the resulting sub-arrays.

The quickSort function takes an integer array arr, and two integer values low and high, which represent the indices of the sub-array to be sorted. The if statement on line 3 checks whether the sub-array has more than one element, since an array with only one element is already sorted.

If the sub-array has more than one element, the partition function (not shown in the provided code) is called on line 6 to partition the array around a pivot value, which is typically chosen to be the last element in the array.

After the array is partitioned, the quickSort function is called recursively on line 9 and 10 with the sub-arrays to the left and right of the pivot, respectively. This continues until the sub-arrays have been reduced to single elements and the sorting is complete.

- The following snippet is from `./src/quicksort.cpp` line 27. Discuss in groups how ìt works:

```cpp
swap(&arr[i + 1], &arr[high]);
```
// This line of code swaps two elements in an integer array arr.

The swap function (not shown in the provided code) takes two integer pointers as input, representing the memory addresses of the two elements to be swapped.

In this specific case, arr is an integer array, and i and high are integer variables representing indices in the array. The line of code swaps the element at i + 1 with the element at high.

This line of code is used in the quicksort algorithm to partition the array around a pivot value. The pivot value is typically chosen to be the last element in the array, and the partition function (not shown in the provided code) moves all elements less than the pivot to the left of it and all elements greater than the pivot to the right of it.

At the end of the partitioning process, the pivot element is in its final sorted position, and this line of code swaps it with the element immediately to its right, so that the pivot element is now between the two sub-arrays that will be recursively sorted by the quicksort algorithm.

## Task 4: Individual (at home)

1. Merge-sort has better worst case performance than quicksort. So why Quick-sort is considered better than Merge-sort? Refer to the following article
   https://www.geeksforgeeks.org/quicksort-better-mergesort/

// Quicksort and merge-sort are both popular sorting algorithms, and each has its own advantages and disadvantages. While merge-sort has a better worst-case performance than quicksort, quicksort is often considered better for several reasons:

1.*Cache Efficiency*: Quick-sort has better cache efficiency than merge-sort, which can be important in real-world scenarios. In quick-sort, the memory accesses are sequential, which means that elements that are stored together in memory are accessed together. This improves cache utilization, since elements that are cached once are more likely to be used again. Merge-sort, on the other hand, requires additional memory to perform the merging step, which can cause cache misses.

2.*Space Complexity*: Quicksort has a lower space complexity than merge-sort, which makes it more memory-efficient for large datasets. Quicksort sorts the array in place, so it does not require additional memory for temporary arrays like merge-sort does.

3.*Practical Performance*: In practice, quicksort often outperforms merge-sort, especially for small to medium-sized arrays. This is because quicksort has a smaller constant factor than merge-sort, which means that it can perform more operations per unit time. In addition, quick-sort has good average-case performance, which makes it a good choice for most applications.

4.*Tail Recursion Optimization*: Quicksort can be optimized using tail recursion, which reduces the amount of stack space required for recursive calls. This optimization is not possible with merge-sort, which means that quick-sort can be used for very large datasets without the risk of stack overflow.

In summary, while merge-sort has better worst-case performance than quicksort, quicksort is often considered better for its cache efficiency, space complexity, practical performance, and tail recursion optimization. However, the choice between the two algorithms ultimately depends on the specific requirements of the application and the characteristics of the dataset being sorted.



2. Refer to the following article. Analyze the complexity of the Merge-sort algorithm.
   https://www.softwaretestinghelp.com/merge-sort/

//The Merge-sort algorithm is a divide-and-conquer algorithm that works by recursively dividing an array into two halves, sorting each half, and merging the sorted halves into a single sorted array.

The time complexity of Merge-sort can be analyzed as follows:

1.Divide Step: In the divide step, the array is divided into two halves of roughly equal size. This step takes constant time, so the time complexity is O(1).

2.Conquer Step: In the conquer step, each half of the array is recursively sorted using Merge-sort. Since each half is roughly half the size of the original array, the conquer step takes approximately T(n/2) time, where T(n) is the time taken to sort an array of size n.

3.Merge Step: In the merge step, the two sorted halves are merged into a single sorted array. The time taken to merge two sorted arrays of size n/2 is O(n), since each element in the arrays needs to be compared once. Since the size of the array doubles in each recursive call to Merge-sort, the total time taken for all merge steps is O(n log n).

The total time complexity of Merge-sort can be expressed using a recurrence relation:

T(n) = 2T(n/2) + O(n)

This recurrence relation can be solved using the Master theorem, which gives a time complexity of O(n log n) for Merge-sort.

In addition to its O(n log n) time complexity, Merge-sort has a space complexity of O(n), since it requires temporary arrays to be created during the merge step. However, this space requirement can be reduced to O(1) using an iterative bottom-up merge-sort algorithm.


3. Refer to the following article. Analyze the complexity of the Quick-sort algorithm.
   https://www.softwaretestinghelp.com/quick-sort/

 //The Quick-sort algorithm is a divide-and-conquer algorithm that works by selecting a pivot element from the array, partitioning the array into two sub-arrays based on the pivot, and recursively sorting each sub-array.

The time complexity of Quick-sort can be analyzed as follows:

1.Partition Step: In the partition step, the array is partitioned into two sub-arrays based on the pivot element. This step takes O(n) time, where n is the size of the array.

2.Recursive Calls: In the recursive calls, each sub-array is recursively sorted using Quick-sort. The time taken for the recursive calls depends on the size of the sub-arrays. In the best case, the pivot element divides the array into two sub-arrays of equal size, and each recursive call processes half of the array. In the worst case, the pivot element is either the smallest or largest element in the array, and one sub-array is of size n-1 and the other is of size 0. In the average case, the time taken for the recursive calls is O(n log n).

3.Best Case: The best-case time complexity of Quick-sort is O(n log n), when the pivot element divides the array into two sub-arrays of equal size.

4.Worst Case: The worst-case time complexity of Quick-sort is O(n^2), when the pivot element is the smallest or largest element in the array, and one sub-array is of size n-1 and the other is of size 0.

5.Average Case: The average-case time complexity of Quick-sort is O(n log n), when the pivot element divides the array into two sub-arrays of roughly equal size.

Quick-sort is an efficient sorting algorithm in practice, due to its good average-case performance and small constant factors. However, its worst-case performance can be a problem in certain scenarios, and it may be necessary to use a modified version of Quick-sort or a different algorithm altogether in these cases.  
