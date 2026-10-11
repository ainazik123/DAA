83.Remove Duplicates from Sorted List

Problem

The task is to remove duplicate values from a sorted linked list so that each value appears only once.

Example:

Input:1 -> 1 -> 2 -> 3 -> 3

Output:1 -> 2 -> 3

Approach

I used an iterative approach with a pointer called current.Because the list is sorted,duplicate values are next to each other.

I compare the current node with the next node.If their values r equal,I skip the next node by changing current.next to current.next.next.If their values r different,I move the pointer forward.

Step-by-step tracing

Input:1 -> 1 -> 2 -> 3 -> 3

The first two values r 1 and 1.They r equal,so I remove the second node.

List:1 -> 2 -> 3 -> 3

The values 1 n 2 r different,so I move forward.

The values 2 n 3 are different,so I move forward.

The values 3 n 3 are equal,so I skip the last duplicate.

List:1 -> 2 -> 3

The final result is 1 -> 2 -> 3.

Challenges n testing

One challenge was deciding when to move the pointer.If I moved it forward after removing a duplicate,I could skip checking consecutive duplicate values.

I would test an empty list, a single-node list,a list containing only equal values,n a list without duplicates.

3. Time Complexity

Time Complexity: O(n)

Here,n is the number of nodes.The algorithm traverses the list from beginning to end, checking each node a constant number of times.Therefore,the running time grows linearly with the list size.

Space Complexity:O(1)

The algorithm uses only one additional pointer and modifies the existing links.

Reflection/Improvement

The current approach is efficient because the list is already sorted.A set-based solution would require additional memory without improving the linear time complexity.

The current solution achieves O(n) time n O(1) auxiliary space.
