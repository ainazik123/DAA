Sort List (LeetCode 148)

Problem:Sort a linked list in ascending order.

Algorithm: Merge Sort

Approach:

Find the middle of the linked list using slow and fast pointers.

Split the list into two separate halves.

Recursively sort both halves.

Merge the sorted halves into one sorted linked list.

Example:

Input: [4, 2, 1, 3]

Output: [1, 2, 3, 4]

Complexity Analysis:

Time Complexity: O(n log n)

Space Complexity: O(log n) auxiliary space for the recursion stack.

Possible Improvement:

The algorithm can be implemented iteratively to avoid recursion and reduce stack memory usage to O(1).This would make the implementation more memory-efficient.

