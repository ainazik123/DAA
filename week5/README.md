Sort an Array (LeetCode 912)

Problem:Sort an array of integers in ascending order.

Algorithm:Merge Sort

Approach:

Divide the array into two halves.

Recursively sort both halves.

Merge the two sorted halves into one sorted array.

Copy the sorted elements back into the original array.

Example:

Input: [5, 2, 3, 1]

Output: [1, 2, 3, 5]

Complexity Analysis:

Time Complexity: O(n log n)

Space Complexity: O(n)

Possible Improvement:

Merge Sort already provides O(n log n) time complexity.The implementation can be improved by reusing a temporary array instead of creating a new array during each merge operation.

