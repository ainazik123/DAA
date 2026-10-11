203.Remove Linked List Elements

Problem

The task is to remove every node from a singly linked list whose value equals a given integer `val`.The remaining nodes must keep their original order.

For example:

Input:1 -> 2 -> 6 -> 3 -> 4 -> 5 -> 6

Target value:`6`

Output:1 -> 2 -> 3 -> 4 -> 5

Approach

I used an iterative approach with a pointer called `current`.

First,I remove matching nodes from the beginning of the list.This is necessary because the head itself may contain the target value.

After handling the beginning,I use `current` to examine the remaining nodes.Instead of comparing `current` with its next node for equality,I check whether `current.next.val` equals the target value.

- If the next node contains `val`,I skip it by setting `current.next = current.next.next`.
- Otherwise,I move `current` to the next node.

When the loop finishes,I return the updated head.

Step-by-step tracing

Input:1 -> 2 -> 6 -> 3 -> 4 -> 5 -> 6

Target value: `6`

1. The head contains `1`, so it is not removed.
2. `current` points to `1`. The next value is `2`, so I move forward.
3. `current` points to `2`. The next value is `6`, so I remove that node.
   List: `1 -> 2 -> 3 -> 4 -> 5 -> 6`
4. The next values are `3`, `4`, and `5`. None equals `6`, so I continue moving forward.
5. The final node contains `6`. I skip it, leaving the list `1 -> 2 -> 3 -> 4 -> 5`.
6. There are no more nodes to check, so the algorithm stops.

Final output:1 -> 2 -> 3 -> 4 -> 5

Challenges and testing

One important challenge is handling target values at the beginning of the list.If I only checked the next node,I could leave unwanted values in the head position.

I would test an empty list,a list where every node matches the target,a list where no node matches,and a list with several consecutive matching nodes at the beginning or middle.

Time Complexity:O(n)

Here,`n` is the number of nodes in the list.Each node is checked or removed in constant time, and the algorithm processes the list from beginning to end.Therefore,the running time is linear.

Space Complexity:O(1)

The solution modifies the existing links and uses only a constant number of pointers.It doesnt create a new list.

Reflection/Improvement

The current solution is already optimal in time because every node may need to be examined at least once.

Another implementation could use a dummy head node.This would simplify the code by allowing the same removal logic to handle the original head and all later nodes.However,it would not improve the O(n) time complexity.The current solution already uses O(1) auxiliary space.
