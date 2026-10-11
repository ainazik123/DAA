160.Intersection of Two Linked Lists

Problem

The task is to find the node where two singly linked lists intersect.An intersection means that both lists share the exact same node in memory,not simply nodes with equal values.

If the lists do not intersect,the method must return `null`.

For example:

List A:4 -> 1 -> 8 -> 4 -> 5

List B:5 -> 6 -> 1 -> 8 -> 4 -> 5

If both lists share the same node containing `8`,the answer is that node.

Approach

I used two pointers,`a` and `b`.Pointer `a` starts at the head of list A,and pointer `b` starts at the head of list B.

Both pointers move one node at a time.When a pointer reaches the end of its list,it starts again from the head of the other list.

This makes both pointers travel the same total distance.If the lists intersect,they eventually reach the same node.If they dont intersect,both pointers eventually become `null`.

The loop continues while `a != b`.This compares node references rather than their values.

Step-by-step tracing

Consider two lists that share the same node containing `8`:

List A:4 -> 1 -> 8 -> 4 -> 5

List B:5 -> 6 -> 1 -> 8 -> 4 -> 5

1. Pointer `a` starts at the first node of A, and pointer `b` starts at the first node of B.
2. Both pointers move forward one node at a time.
3. Pointer `a` reaches the end of list A and switches to the head of B.
4. Pointer `b` reaches the end of list B and switches to the head of A.
5. After switching lists, the pointers align at the shared part.
6. Both pointers reach the same node containing `8`.The condition `a != b` becomes false, and the algorithm returns that node.

Final result: the shared node with value `8`.

Challenges and testing

A key challenge is understanding that equal values dont necessarily mean that two lists intersect.For example,two separate nodes can both contain `8` without being the same node.

I would test lists that intersect at the first node,intersect near the end,have different lengths,or dont intersect at all.An empty list should also be tested.

3. Time Complexity:O(n + m)

Here,`n` and `m` r the lengths of the two lists.Each pointer traverses both lists at most once before the pointers meet or both become `null`.Therefore,the total work is proportional to the sum of the list lengths.

Space Complexity:O(1)

Only two pointers r used.No additional arrays,sets,or lists r created.

Reflection/Improvement

The two-pointer approach is already efficient for this problem.A simpler alternative would be to store every node from one list in a set and then check the other list,but that would require O(n) additional space.

The current approach achieves O(n + m) time and O(1) auxiliary space,so it is preferable when constant extra space is important.
